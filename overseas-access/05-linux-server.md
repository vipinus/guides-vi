# 05 · Cho máy chủ Linux và công cụ dòng lệnh đi qua đường truyền thế nào

Trên Linux có hai đường để đi qua đường truyền; chọn theo nhu cầu. Muốn cả máy đi qua (kéo image Docker, chạy dịch vụ cần mạng nước ngoài, chạy không người trông), dùng OpenVPN: một file cấu hình đặt trong /etc/openvpn/client/ và tự chạy khi khởi động. Muốn chỉ vài lệnh đi qua (git, pip, npm, curl), dùng Web Proxy: điền địa chỉ proxy vào biến môi trường http_proxy, phần lưu lượng còn lại không bị đụng tới. Trên Linux bản desktop còn có thể nhập vào NetworkManager. Bài này trình bày cả ba, kèm cách viết file mật khẩu và các lệnh để kiểm tra.

## Đường thứ nhất: cả máy đi qua đường truyền (OpenVPN)

1. Cài ứng dụng: Debian / Ubuntu sudo apt install openvpn, Fedora sudo dnf install openvpn, Arch sudo pacman -S openvpn.
2. Đăng nhập trang này, trên trang OpenVPN bấm lá cờ của khu vực để tải file .ovpn. Cấu hình cấp cho Linux không gói sẵn tài khoản và mật khẩu (NetworkManager không nhận file có sẵn thông tin đăng nhập), nên hãy tạo riêng một file mật khẩu: hai dòng, dòng đầu là email của bạn trên trang này, dòng thứ hai là mật khẩu, rồi chmod 600.
3. Chép file .ovpn thành /etc/openvpn/client/<khu-vực>.conf, và thêm đường dẫn file mật khẩu vào sau auth-user-pass trong file.
4. sudo systemctl enable --now openvpn-client@<khu-vực>. Xem trạng thái bằng systemctl status openvpn-client@<khu-vực>, và kiểm tra curl -s https://ipinfo.io/country hiện đúng khu vực bạn đã chọn.
5. Muốn đổi khu vực thì tải cấu hình khác và bật unit khác; mỗi lúc chỉ chạy một cái.

## Đường thứ hai: chỉ công cụ dòng lệnh đi qua đường truyền (Web Proxy)

Địa chỉ proxy có trên trang Proxy của trang này, cùng với tài khoản và mật khẩu của bạn, có thể điền thẳng vào biến môi trường: export https_proxy=https://username:password@proxy-address export http_proxy=$https_proxy. Ký tự đặc biệt trong mật khẩu phải được mã hóa URL. Sau đó curl, wget, git, pip và npm trong terminal này đều đi qua đường truyền, các chương trình khác không bị ảnh hưởng.

Tiến trình nền của Docker không đọc biến môi trường của shell; hãy ghi vào Environment= trong /etc/systemd/system/docker.service.d/proxy.conf rồi khởi động lại docker. Với apt, ghi Acquire::https::Proxy trong /etc/apt/apt.conf.d/proxy.conf.

Với đường này, về thiết kế không có kết nối nào để mà rớt; không cần root và không đổi bảng định tuyến. Nó hợp với máy chủ công ty và những lúc bạn chỉ muốn kéo dữ liệu nhanh hơn; nó chỉ có tác dụng với chương trình tuân theo biến proxy, lưu lượng còn lại không bị đụng tới.

## Đường thứ ba: NetworkManager trên Linux bản desktop

1. Cài network-manager-openvpn-gnome (trên trang OpenVPN của trang này có nút bấm một lần để mở trung tâm phần mềm).
2. Cài đặt → Mạng → VPN → "+" → Nhập từ tập tin (Import from file), chọn file .ovpn, nhập email và mật khẩu của trang này rồi lưu.
3. Bật tắt VPN từ thanh trên cùng hoặc khay hệ thống. Muốn tự kết nối khi khởi động thì trong cài đặt của kết nối có dây/không dây, đánh dấu "Tự động kết nối VPN" (Automatically connect to VPN).

## Kiểm tra và xử lý sự cố

- Kiểm tra lối ra: quốc gia trong curl -s https://ipinfo.io là khu vực bạn đã chọn.
- Kiểm tra DNS: trong resolvectl status, DNS của giao diện VPN phải là DNS do đường truyền đẩy xuống; nếu bị lọt, thêm dhcp-option DNS vào cấu hình hoặc dùng script update-systemd-resolved.
- AUTH_FAILED: file mật khẩu sai hoặc tài khoản đã hết hạn; nếu đã đổi mật khẩu thì cập nhật file mật khẩu.
- TLS handshake timeout: UDP tới máy chủ không đi qua được; đổi khu vực hoặc đổi mạng. Trên máy chủ đám mây, nhóm bảo mật (security group) phải cho phép UDP đi ra.
- Máy chủ đặt ở Trung Quốc và muốn nguồn Trung Quốc kết nối thẳng: khi OpenVPN đã kết nối thì mọi lưu lượng đi ra đều qua đường truyền. Hãy đổi nguồn apt / pip / npm sang mirror Trung Quốc, hoặc dùng đường thứ hai để chỉ những lệnh cụ thể đi qua.

## Những điều cần biết

- Một máy Linux tính là một thiết bị và dùng chung hạn mức trực tuyến cùng lúc với các thiết bị khác của bạn (Cá nhân 2 thiết bị, Gia đình 4 thiết bị, Doanh nghiệp 8 thiết bị); Web Proxy ở đường thứ hai được tính theo kết nối và cũng nằm trong đó.
- File cấu hình và file mật khẩu tương đương tài khoản của bạn; đừng commit vào kho git hay đóng vào image.
- Đổi mật khẩu thì cấu hình cũ mất hiệu lực ngay; đây là cơ chế thu hồi có chủ ý. Chỉ cần cập nhật file mật khẩu.
- Khi chạy đường truyền trên máy chủ đám mây, hãy tuân theo điều khoản sử dụng của nhà cung cấp; đường truyền chỉ ghi lại thời lượng kết nối và tổng lưu lượng.

## Câu hỏi thường gặp

**Sao cấu hình cho Linux không gói sẵn tài khoản và mật khẩu?** Khi nhập cấu hình, NetworkManager không nhận file có sẵn thông tin đăng nhập và báo nhập thất bại, nên bản cấp cho Linux để bạn tự điền; với cách dùng systemd thì ghi vào file mật khẩu.

**Có thể chỉ cho Docker đi qua đường truyền không?** Được: đặt biến proxy riêng cho tiến trình nền Docker (đường thứ hai); hoặc chạy một container có OpenVPN bên trong (gluetun) để chỉ những container nhất định đi qua đường truyền.

**Còn Mạng riêng (Tailscale) trên Linux thì sao?** Script chính thức cài bằng một dòng lệnh, và tailscale up --login-server=<máy chủ điều khiển của trang này> để đăng nhập. Nó hợp khi bạn cần truy cập máy này từ bên ngoài, hoặc muốn thiết lập một lần rồi luôn trực tuyến; nếu chỉ để kéo dữ liệu nhanh hơn thì OpenVPN hoặc proxy đơn giản hơn.

**OpenWrt trên router có giống vậy không?** Trên OpenWrt, cài luci-app-openvpn và tải file .ovpn lên là cả mạng LAN đi qua đường truyền; router có firmware của trang này thì không cần, chỉ việc đăng nhập tài khoản.

## Đọc thêm

- [Trang OpenVPN: tải ứng dụng và file cấu hình](https://www.leotun.com/vi/openvpn?utm_source=github&utm_content=overseas-access-05)
- [Cách dùng OpenVPN và khi nào nên chọn nó](https://www.leotun.com/vi/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-05)
- [Cho NAS Synology hoặc QNAP đi qua đường truyền thế nào](https://www.leotun.com/vi/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-05)
- [Web Proxy là gì và khi nào nên dùng](https://www.leotun.com/vi/guides/web-proxy?utm_source=github&utm_content=overseas-access-05)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/linux-server?utm_source=github&utm_content=overseas-access-05

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=overseas-access-05) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=overseas-access-05) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, hiệu lực lâu dài
