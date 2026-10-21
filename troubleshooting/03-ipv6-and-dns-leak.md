# 03 · Đã kết nối mà trang video vẫn báo bản quyền: IPv6 và DNS là chỗ bị lọt

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/overseas-video?utm_source=github&utm_content=troubleshooting-03

Bạn đã qua bước 1 của [02 · Đã kết nối về Trung Quốc mà vẫn không xem được](02-still-blocked-after-connecting.md) — IP lối ra kiểm tra đúng là Trung Quốc đại lục — vậy mà trang vẫn báo "không phát được do giới hạn bản quyền". Mười lần thì chín lần là trên thiết bị vẫn còn một đường không đi qua VPN: **IPv6** hoặc **DNS**. Trang video đoán bạn ở đâu dựa vào địa chỉ nó nhìn thấy, và chỉ cần một đường bị lọt ra ngoài thì thứ nó thấy vẫn là nước ngoài.

## Vì sao bị lọt

- Thiết bị bây giờ có cả địa chỉ IPv4 lẫn IPv6, và trình duyệt ưu tiên IPv6. Nếu VPN chỉ nhận IPv4 thì các yêu cầu IPv6 sẽ đi thẳng ra qua mạng gia đình của bạn.
- "DNS bảo mật" có sẵn trong trình duyệt, "DNS riêng tư" của Android, hay một công cụ mạng mesh khác đang chạy (Tailscale chẳng hạn) đều có thể giành việc phân giải tên miền trước VPN.

"Đã kết nối" chỉ có nghĩa là đường hầm đã được dựng lên. Nó không có nghĩa là mọi lưu lượng đều đi qua đường hầm.

## Kiểm tra trong năm bước

1. **Kiểm tra IPv6.** Kết nối xong, tìm "test ipv6" và mở một trang kiểm tra. Nếu ô IPv6 hiện địa chỉ ở nước bạn đang ở → vấn đề nằm đây, sang bước 2. Nếu cả hai ô đều là Trung Quốc đại lục, hoặc IPv6 không khả dụng → sang bước 3.
2. **Tắt IPv6, hoặc đổi sang ứng dụng có chặn IPv6.** Windows: trong thuộc tính của bộ điều hợp mạng, bỏ chọn "Giao thức Internet Phiên bản 6" (Internet Protocol Version 6). macOS: Cài đặt mạng → TCP/IP → đặt IPv6 thành "Chỉ liên kết cục bộ" (Link-local only). Điện thoại: tắt Wi‑Fi và thử một lần bằng dữ liệu di động; mạng gia đình thường có IPv6, còn dữ liệu di động của nhà mạng thì hay không có.
3. **Kiểm tra DNS.** Chrome: Cài đặt → Quyền riêng tư và bảo mật → tắt "Sử dụng DNS bảo mật"; Android: tắt "DNS riêng tư"; thoát các VPN khác, công cụ mạng mesh và tiện ích proxy.
4. **Thoát hẳn ứng dụng rồi mở lại; với bản web thì xóa dữ liệu trang.** Các nền tảng lưu kết quả kiểm tra khu vực lần trước.
5. **Đổi sang điểm vào khác rồi thử lại.** Địa chỉ của một lối ra nào đó có thể vừa bị nền tảng đánh dấu.

## LeoTun xử lý chuyện này thế nào

Từ tháng 9/2026, cả ba cách kết nối của LeoTun (Hiddify, Cisco AnyConnect, OpenVPN) đều từ chối IPv6 ngay trong đường hầm và đẩy xuống thiết lập DNS buộc phân giải bên trong đường hầm — không phải đổi cài đặt nào trên thiết bị của bạn. **Cấu hình Hiddify nhập trước tháng 9 không có quy tắc này. Hãy xóa đi và quét mã QR để nhập lại.**

Phương án router thì ngay từ đầu đã không bị lọt: cả mạng LAN đi ra qua router, nên IPv6 và DNS của các thiết bị không bao giờ ra tới bên ngoài.

## Những trường hợp vẫn bị báo

| Trường hợp | Triệu chứng | Cách xử lý |
|---|---|---|
| Lối ra không phải Trung Quốc đại lục | Tra IP thấy Hồng Kông / Đài Loan / Nhật Bản | Đổi sang điểm vào Trung Quốc; với Tencent và iQIYI, địa chỉ Hồng Kông và Đài Loan cũng tính là nước ngoài |
| Quy tắc định tuyến tự đặt cho tên miền video đi "direct" (đi thẳng) | Trang web mở được nhưng video không phát | Đổi các tên miền Trung Quốc sang đi qua node; người dùng ở nước ngoài đừng bật "đi thẳng với Trung Quốc" |
| Bạn đang dùng Web Proxy | Dùng được trong trình duyệt, không được trong ứng dụng | Xem video cần đường hầm cho cả thiết bị; Web Proxy chỉ lo trình duyệt |

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=troubleshooting-03) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=troubleshooting-03) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), hiệu lực lâu dài
