# 08 · Thiết lập nhiều thiết bị một lần, đổi điện thoại không phải làm lại từ đầu

Với người có nhiều thiết bị, phiền nhất là phải cấu hình từng cái, đổi điện thoại lại làm lại từ đầu, và ra ngoài thì máy nào cũng phải bấm kết nối. Mạng riêng gỡ bỏ hết những chuyện đó: mỗi thiết bị đăng nhập tài khoản của trang này một lần rồi luôn trực tuyến, khởi động lại hay đổi Wi‑Fi cũng không phải làm gì; mỗi thiết bị tự chọn khu vực lối ra, laptop dùng Nhật Bản còn điện thoại dùng khu vực Trung Quốc mà không ảnh hưởng nhau; các thiết bị cùng tài khoản truy cập được lẫn nhau, nên laptop đang ở ngoài vẫn mở thẳng được thư mục chia sẻ trên NAS ở nhà. Điện thoại mới chỉ cần đăng nhập. Bài này giải thích cách đưa toàn bộ thiết bị trong nhà vào, cách tính hạn mức, và xử lý khi hết hạn hay đổi thiết bị.

## Việc mỗi thiết bị chỉ làm một lần

1. Cài ứng dụng Tailscale (Android, Windows, macOS và Linux lấy ở khu tải xuống trên trang Mạng riêng của trang này; iPhone / iPad lấy từ App Store, cần Apple ID ngoài khu vực Trung Quốc).
2. Nếu đã đăng nhập tài khoản Tailscale chính thức thì đăng xuất trước, rồi trỏ việc đăng nhập tới máy chủ điều khiển của trang này (điện thoại: "⋯" ở màn hình chưa đăng nhập → Use custom server; máy tính: sao chép lệnh trên trang; macOS: Account Settings → Accounts → mũi tên cạnh "Add Account…" → Add Account Using Alternate Server).
3. Xác nhận trong trình duyệt bằng tài khoản của trang này. Từ đó trở đi thiết bị đã ở trong Mạng riêng, không phải để ý nữa.
4. Chọn lối ra: mỗi thiết bị tự chọn trong menu của nó, độc lập với các máy khác. Không muốn dùng lối ra thì chọn None, chỉ giữ việc truy cập giữa các thiết bị.

## Cách tính số thiết bị cùng lúc

Một tài khoản cài trên bao nhiêu thiết bị cũng được; giới hạn chỉ tính số thiết bị trực tuyến cùng lúc: Cá nhân 2, Gia đình 4, Doanh nghiệp 8, dùng chung một hạn mức với Cisco, Hiddify và các cách khác. Khi vượt giới hạn của gói, bạn có thể tạm nâng hạng tài khoản (thời gian còn lại được quy đổi tương đương theo giá) rồi dùng xong thì đổi lại.

Một router tính là một thiết bị, các thiết bị phía sau nó không tính. Một router hoặc NAS ở nhà cộng với điện thoại và laptop mang theo người thường là đủ.

## Các thiết bị truy cập được lẫn nhau

- Mỗi thiết bị trong cùng tài khoản có một địa chỉ mạng riêng, cũng có thể gọi bằng tên thiết bị, không cần IP công cộng hay mở cổng.
- Mở thư mục chia sẻ trên NAS ở nhà từ laptop đang ở ngoài, xem đầu ghi camera ở nhà từ điện thoại, hay điều khiển máy tính ở nhà qua remote desktop — tất cả đều kết nối trực tiếp bằng địa chỉ mạng riêng.
- Router ở nhà chạy firmware của trang này có thể chia sẻ cả mạng LAN vào Mạng riêng, nên những thiết bị không chạy được ứng dụng như máy in, TV cũng truy cập được từ bên ngoài.
- Thiết bị của khách hàng khác hoàn toàn không xuất hiện trong Mạng riêng của bạn — không chỉ là bạn không nhìn thấy chúng.

## Hết hạn, đổi thiết bị, gỡ cài đặt

- Tài khoản hết hạn: mọi thiết bị ngoại tuyến trong vài phút; gia hạn xong thì đăng nhập lại một lần trên từng máy, cài đặt lối ra vẫn được giữ.
- Đổi điện thoại: đăng nhập trên máy mới theo các bước trên; nếu báo đã đạt giới hạn thì đăng xuất ở điện thoại cũ, hoặc tạm nâng hạng tài khoản rồi dùng xong đổi lại.
- Không muốn một thiết bị ở lại trong Mạng riêng: đăng xuất trong ứng dụng; muốn buộc một thiết bị ngoại tuyến thì liên hệ hỗ trợ.
- Đừng chạy thêm một VPN khác trên cùng thiết bị cùng lúc (Cisco của công ty, phần mềm mạng mesh khác); chúng sẽ giành nhau DNS và tuyến đường.

## Câu hỏi thường gặp

**Mỗi thiết bị chọn khu vực lối ra khác nhau được không?** Được, mỗi thiết bị tự chọn lối ra. Laptop dùng Nhật Bản để xem video trong khi điện thoại dùng khu vực Trung Quốc để vào ngân hàng trực tuyến, không ảnh hưởng nhau.

**Để Mạng riêng bật suốt có hao pin không?** Không chọn lối ra thì gần như không có lưu lượng; nó chỉ dùng khi liên lạc với các thiết bị trong Mạng riêng. Mức hao pin tương đương VPN của hệ thống.

**Cài trên NAS ở nhà thế nào?** Synology và QNAP có gói Tailscale, hệ thống Linux dùng script cài đặt chính thức; khi đăng nhập thì trỏ tới máy chủ điều khiển của trang này theo cách tương tự. Router chạy firmware của trang này không cần cài: đăng nhập tài khoản là đã ở trong Mạng riêng.

**Sao không cài Cisco cho mọi thiết bị?** Cũng được, nhưng với Cisco bạn phải bấm kết nối mỗi lần, rớt thì kết nối lại, đổi lối ra thì phải đổi địa chỉ; nhiều thiết bị thì Mạng riêng đỡ công hơn nhiều. Ngoại lệ là thiết bị dùng mạng trường học hạn chế UDP; máy đó hãy dùng Cisco.

## Đọc thêm

- [Trang Mạng riêng: tải xuống và các bước đăng nhập](https://www.leotun.com/vi/mesh?utm_source=github&utm_content=client-08)
- [Mạng riêng (Tailscale) là gì](https://www.leotun.com/vi/guides/tailscale-mesh?utm_source=github&utm_content=client-08)
- [Xem camera và NAS ở nhà bên Trung Quốc khi đang ở nước ngoài](https://www.leotun.com/vi/guides/home-camera?utm_source=github&utm_content=client-08)
- [Firmware router làm được những gì](https://www.leotun.com/vi/guides/router-firmware?utm_source=github&utm_content=client-08)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/multi-device?utm_source=github&utm_content=client-08

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=client-08) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=client-08) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
