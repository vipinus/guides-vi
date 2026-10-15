# 04 · OpenVPN: tải hồ sơ .ovpn, nhập và kết nối; dùng được trên router, NAS và Linux

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/openvpn-setup?utm_source=github&utm_content=client-04

OpenVPN là giao thức mã nguồn mở lâu đời, gần như mọi hệ điều hành, firmware router và NAS đều có sẵn ứng dụng cho nó. File hồ sơ của LeoTun đã gói sẵn tài khoản, mật khẩu và khóa mã hóa của bạn, nhập vào là kết nối được. Dùng hằng ngày trên điện thoại và máy tính thì AnyConnect hoặc Hiddify đỡ công hơn; giá trị của OpenVPN nằm ở **những nơi chỉ chấp nhận OpenVPN**: router OpenWrt, NAS Synology / QNAP, máy chủ Linux và các thiết bị đời cũ.

## Ba bước

1. Từ bảng trên [trang OpenVPN của website](https://www.leotun.com/vi/openvpn?utm_source=github&utm_content=client-04), cài ứng dụng cho hệ điều hành của bạn (nền tảng nào cũng có OpenVPN Connect chính thức; trên Windows còn dùng được OpenVPN GUI, trên macOS dùng được Tunnelblick).
2. Đăng nhập xong, **bấm vào lá cờ của khu vực** để tải file .ovpn của khu vực đó. Mỗi khu vực một file.
3. Mở file trong ứng dụng và kết nối.

| Nền tảng | Lưu ý |
|---|---|
| Windows / macOS / Android / iOS | Hồ sơ đã có sẵn tài khoản và mật khẩu; nhập vào là kết nối |
| Linux | Cài đặt VPN của hệ thống → nhập từ file, lần kết nối đầu nhập email và mật khẩu website; dòng lệnh `openvpn --config file`; muốn tự chạy khi khởi động thì đặt vào `/etc/openvpn/client/` |
| Router OpenWrt | Cài luci-app-openvpn, tải file .ovpn lên rồi bật; nếu đã cài sẵn firmware của trang này thì không cần |
| NAS Synology | Control Panel → Network → Network Interface → Create → VPN → OpenVPN (nhập file .ovpn); muốn lưu lượng ra ngoài của NAS đi qua đường truyền thì đánh dấu "Use default gateway on remote network" (dùng cổng mặc định của mạng từ xa) |
| NAS QNAP | QVPN → VPN Client → Add → OpenVPN, rồi nhập file |

## Người dùng ở Trung Quốc: vào thẳng các trang web Trung Quốc

Khi đã kết nối, lưu lượng tới các trang Trung Quốc sẽ phải đi đường vòng. Website có "công cụ đi thẳng cho Trung Quốc": nhấp đúp để chạy, IP Trung Quốc sẽ kết nối trực tiếp còn mọi thứ khác đi qua đường truyền. Dùng được cho cả Cisco lẫn OpenVPN. Người dùng ở nước ngoài thì đừng dùng.

## Không kết nối được thì kiểm tra theo thứ tự này

| Từ khóa trong log / triệu chứng | Nguyên nhân | Cách xử lý |
|---|---|---|
| AUTH_FAILED | Sai tài khoản hoặc mật khẩu, hoặc đã hết hạn | Đăng nhập website kiểm tra ngày hết hạn; nếu đã đổi mật khẩu thì tải lại hồ sơ |
| UDP hết thời gian chờ trước, rồi kết nối được bằng TCP | Mạng hiện tại hạn chế UDP nên tự lùi về TCP | Vẫn dùng được nhưng chậm hơn; quá chậm thì đổi mạng hoặc chuyển sang AnyConnect |
| Cả UDP lẫn TCP đều báo TLS handshake failed / key negotiation failed | Đường mạng tới máy chủ bị đứt | Đổi khu vực hoặc đổi mạng |
| Báo lỗi khi nhập | Ứng dụng quá cũ (trước OpenVPN 2.5) | Cập nhật ứng dụng |
| Đang kết nối thì đột ngột rớt | Tài khoản hết hạn và máy chủ ngắt kết nối | Gia hạn rồi kết nối lại; không cần thay hồ sơ |

## UDP hay TCP

Cả hai đều có, bạn không phải chọn. Trong hồ sơ UDP đứng trước nên ứng dụng thử UDP trước; nếu UDP bị hạn chế hoặc không kết nối được, sau vài giây nó tự chuyển sang TCP. UDP có độ trễ thấp hơn và nhanh hơn; TCP chỉ là phương án dự phòng và chậm thấy rõ khi đi xuyên biên giới. Với các mạng hạn chế UDP thường xuyên (một số mạng trường học và công ty), chúng tôi khuyên dùng thẳng AnyConnect.

> Hồ sơ tải trước ngày 15/9/2026 chỉ có UDP; muốn tự động chuyển thì tải lại.

## Bảo mật

File hồ sơ chứa tài khoản và mật khẩu của bạn, nên nó tương đương chính tài khoản, đừng đưa cho người khác; nếu bị lộ, hãy đổi mật khẩu trên website và file cũ mất hiệu lực ngay lập tức. Bản thân bước bắt tay cũng được mã hóa: không có khóa trong hồ sơ thì thậm chí không bắt đầu bắt tay được, và các công cụ quét không nhìn thấy máy chủ.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=client-04) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=client-04) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
