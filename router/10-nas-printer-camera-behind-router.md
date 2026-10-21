# 10 · NAS, máy in và camera sau router có bị ảnh hưởng không?

Lắp router VPN vào rồi, điều đầu tiên người ta lo thường là các thiết bị khác trong nhà: NAS, máy in, camera có còn chạy bình thường không, và NAS có kéo hết lưu lượng của nó qua VPN không?

## Trả lời ngắn

Không. Chia luồng được bật sẵn: **lưu lượng giữa các thiết bị trong nhà và lưu lượng tới các dịch vụ ở Trung Quốc không bao giờ đi vào đường hầm. Chỉ những trang cần VPN mới đi qua nó.**

## Ba loại lưu lượng, ba đường đi

| Lưu lượng | Đường đi | Ví dụ |
|---|---|---|
| Giữa các thiết bị trong nhà | Ở lại mạng nội bộ, không chạm vào đường hầm | Chép file vào NAS, truyền hình ảnh lên TV, in tài liệu |
| Tới dịch vụ ở Trung Quốc | Đi thẳng, bằng đường mạng của chính bạn | NAS đồng bộ lên ổ đám mây Trung Quốc, camera tải lên đám mây Trung Quốc, tải về từ nguồn trong nước |
| Tới các trang bị chặn | Qua đường hầm | YouTube, tìm kiếm, công cụ AI |

Vì vậy chép file vào NAS trong nhà vẫn chạy hết tốc độ mạng nội bộ, còn việc sao lưu lên đám mây Trung Quốc dùng trọn đường mạng của bạn mà không đụng tới VPN.

Khi bạn ở nước ngoài và dùng tuyến về Trung Quốc, chiều sẽ ngược lại: các trang Trung Quốc có trong danh sách đi qua đường hầm, còn lại đi thẳng. Xem [03 · Chia luồng là gì](03-router-split-routing.md).

## Ba tình huống thường gặp

**Truy cập NAS từ bên ngoài (lấy file từ xa, sao lưu ảnh điện thoại)**
Có hai cách:
- Dùng Mạng riêng (Tailscale): đăng nhập NAS và điện thoại vào cùng một tài khoản, rồi từ đâu cũng gọi NAS bằng tên thiết bị. Không cần IP công cộng, không cần mở cổng (port forwarding). Xem [Mạng riêng và VPN khác nhau thế nào](../network/03-private-network-vs-vpn.md).
- Cứ làm như trước đây (truy cập từ xa của hãng, mở cổng). Router không chặn chuyện đó.

**NAS đang chạy tải xuống**
Tải từ nguồn Trung Quốc thì đi thẳng, không bị ảnh hưởng. Tải từ các trang nước ngoài vốn vào được từ Trung Quốc (như bản tải của Apple, Microsoft) mặc định cũng đi thẳng; chỉ tải từ các trang bị chặn mới qua đường hầm và chạy theo tốc độ đường hầm. Nếu không muốn việc tải xuống dùng đường hầm, cắm NAS vào router phía trên hoặc modem, khi đó nó đi vòng qua hẳn router này.

**Laptop công ty cần VPN của công ty**
Cho nó bắt Wi-Fi của router phía trên hoặc của modem, tách khỏi router này. Hai VPN chồng lên nhau thường làm hỏng việc truy cập mạng công ty.

## Khi có một thiết bị không chịu nghe lời

- Thiết bị đang bật "DNS riêng tư" (Private DNS) hoặc "DNS bảo mật" (Secure DNS). Khi đó nó tự phân giải tên miền, đi vòng qua router, và chia luồng không nhìn thấy được. Hãy tắt cài đặt đó.
- Kiểm tra xem nó đang bắt Wi-Fi nào. Nếu đang bắt Wi-Fi của modem thì nó chưa từng đi qua router này.

## Câu hỏi thường gặp

**NAS có chiếm một suất thiết bị trong tài khoản không?** Không. Router chiếm một suất, mọi thứ phía sau nó không tính riêng.

**Cả nhà cùng dùng thì có hết dữ liệu không?** Tài khoản không giới hạn dữ liệu, và lưu lượng trong nước vốn không đi vào đường hầm.

**Có giữ một thiết bị luôn không đi VPN được không?** Được, cắm nó vào router phía trên hoặc modem. Trang quản trị cũng có thể chuyển cả router sang chế độ "Direct" (đi thẳng), nhưng như vậy sẽ áp dụng cho mọi người cùng lúc.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-10) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-10) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, hiệu lực lâu dài
