# 03 · Mạng riêng (Tailscale) khác VPN thế nào, và khi nào nên dùng

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/tailscale-mesh?utm_source=github&utm_content=network-03

Mục Mạng riêng dùng Tailscale: một công cụ kết nối mạng dựa trên WireGuard. LeoTun tự vận hành máy chủ điều khiển, bạn đăng nhập bằng tài khoản của trang này. Nó không giống các VPN "kiểu kết nối" như AnyConnect và OpenVPN.

## Ba điểm khác nhau

| | VPN kiểu kết nối (AnyConnect / OpenVPN / Hiddify) | Mạng riêng (Tailscale) |
|---|---|---|
| Kết nối | Mỗi lần dùng phải bấm kết nối, rớt thì kết nối lại | Đăng nhập một lần là luôn trực tuyến; đổi mạng tự khôi phục |
| Lối ra | Kết nối xong thì toàn bộ lưu lượng đi qua lối ra | Lối ra là tùy chọn: không chọn thì lưu lượng Internet công cộng đi ra tại chỗ, chỉ lưu lượng giữa các thiết bị trong Mạng riêng được mã hóa; chỉ khi chọn lối ra của một khu vực thì mới tương đương VPN |
| Truy cập giữa các thiết bị | Không có | Điện thoại, máy tính và NAS cùng tài khoản truy cập thẳng được lẫn nhau, không cần mở cổng hay IP công cộng |

## Khi nào nên dùng

- Có nhiều thiết bị, muốn cấu hình một lần rồi luôn trực tuyến.
- Ở nhà có NAS, máy tính hoặc camera cần truy cập từ bên ngoài: đăng nhập Mạng riêng ở cả hai đầu rồi kết nối thẳng bằng tên thiết bị, như đang cùng một mạng LAN.
- Thiết bị cần giữ kết nối thời gian dài: không có chuyện phiên hết hạn.

## Khi nào cách khác hợp hơn

- Chỉ dùng một lần, tạm thời: nhập Hiddify bằng mã QR hoặc cài AnyConnect nhanh hơn.
- Thiết bị đang chạy VPN công ty hoặc phần mềm kết nối mạng khác: hai bên sẽ giành nhau DNS và tuyến đường, triệu chứng là xem video Trung Quốc thì bị báo bản quyền và không mở được mạng nội bộ công ty. Hãy dùng cách chỉ ảnh hưởng tới trình duyệt, như Web Proxy.
- Mạng trường học / công ty hạn chế UDP: WireGuard chạy trên UDP nên chỉ còn trông vào máy chuyển tiếp, rất chậm; hãy chuyển sang AnyConnect.

## Hết hạn và số thiết bị

Hiệu lực đăng nhập của thiết bị đi theo ngày hết hạn của tài khoản; hết hạn thì thiết bị ngoại tuyến trong vài phút, gia hạn xong đăng nhập lại là được. Số thiết bị trực tuyến cùng lúc tùy theo gói (Cá nhân 2 thiết bị, Gia đình 4 thiết bị, Doanh nghiệp 8 thiết bị) và dùng chung hạn mức với các cách kết nối khác; khi số thiết bị trực tuyến cùng lúc vượt giới hạn của gói, bạn có thể tạm nâng hạng tài khoản (thời gian còn lại được quy đổi ngang giá theo giá gói) rồi dùng xong đổi lại.

Các bước cài đặt và đăng nhập xem [Hướng dẫn ứng dụng 05](../client/05-tailscale-private-network.md).

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=network-03) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=network-03) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
