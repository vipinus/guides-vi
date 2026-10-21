# 03 · Chia luồng trên router là gì

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/router-firmware?utm_source=github&utm_content=router-03

## Nói gọn trong một câu

Cài VPN lên router, thì mọi thiết bị trong nhà cứ bắt Wi-Fi là tự đi qua VPN. Những thiết bị không cài được ứng dụng như đầu thu TV, máy chơi game, máy in cũng dùng được.

## Chia luồng giải quyết vấn đề gì

Nếu toàn bộ lưu lượng đều đi qua VPN, bạn sẽ gặp hai vấn đề: trang web tại chỗ trở nên chậm (vì phải đi đường vòng), và thiết bị trong nhà không truy cập được (máy in, NAS và trang quản trị router đều ở mạng nội bộ, nhưng lưu lượng lại bị gửi ra ngoài).

Chia luồng hoạt động bằng cách đưa cho router một danh sách: tên miền có trong danh sách thì đi qua VPN, còn lại kết nối thẳng. Chiều nào đi qua VPN tùy vào bạn đang ở đâu và muốn vào phía nào, và được quyết định tự động theo khu vực bạn chọn:

- **Ở nước ngoài, chọn khu vực Trung Quốc (truy cập Trung Quốc)**: trang web và ứng dụng Trung Quốc đi qua VPN, còn lại kết nối thẳng.
- **Ở Trung Quốc, chọn khu vực nước ngoài (truy cập dịch vụ nước ngoài)**: mặc định chỉ trang web và dịch vụ bị chặn mới đi qua VPN; trang Trung Quốc, và cả trang nước ngoài vốn mở được bình thường từ Trung Quốc (trang của công ty nước ngoài, bản tải của Apple và Microsoft, nền tảng game…), đều kết nối thẳng không đi vòng, nhanh như khi không có router.

## Ba chế độ

| Chế độ | Lưu lượng đi đâu | Khi nào dùng |
|---|---|---|
| Global (toàn cục) | Tất cả đi qua VPN | Tạm thời, khi dò lỗi |
| Split routing (chia luồng) | Tên miền trong danh sách đi qua VPN, còn lại kết nối thẳng | Hằng ngày |
| Direct (trực tiếp) | Không gì đi qua VPN | Khi tạm thời không cần |

## Truy cập dịch vụ nước ngoài từ Trung Quốc: chỉ trang bị chặn

Từ ngày 14 tháng 10 năm 2026, chia luồng theo chiều truy cập dịch vụ nước ngoài từ Trung Quốc mặc định chỉ đưa trang web và dịch vụ bị chặn đi qua VPN. Nó dựa trên một danh sách trang bị chặn tự cập nhật mỗi ngày, cộng thêm các dịch vụ như Telegram kết nối tới địa chỉ cố định mà không tra tên trang. Trang web vốn mở được bình thường từ Trung Quốc, dù là trang Trung Quốc hay nước ngoài, đều kết nối thẳng.

Công tắc nằm trong trang quản trị router, mục "VPN settings", phần chia luồng thông minh: ô "Blocked sites only" (chỉ cho trang bị chặn đi qua VPN), mặc định được đánh dấu. Bỏ đánh dấu để quay về cách cũ: trang Trung Quốc kết nối thẳng, còn lại đi qua VPN.

Firmware cài trước tháng 10 năm 2026 chưa hiện ô này; mặc định mới đã được áp dụng cho các router đó qua cập nhật tự động. Muốn đổi thì liên hệ bộ phận hỗ trợ, họ có thể làm từ xa.

Chiều truy cập Trung Quốc từ nước ngoài không thay đổi.

## Những chỗ dễ vấp

- **Có trang không mở được khi chia luồng**: trước hết xem nó có trong danh sách không. Trang không có trong danh sách sẽ kết nối thẳng, và nếu vốn dĩ trang đó đã không mở được thì chia luồng cũng không giúp gì. Tạm chuyển sang "Global" để kiểm chứng.
- **Ở Trung Quốc, có trang nước ngoài không mở được**: bỏ đánh dấu "Blocked sites only" trong phần chia luồng thông minh (hoặc tạm chuyển sang "Global") rồi thử lại. Nếu mở được thì trang đó bị chặn nhưng chưa có trong danh sách; hãy gửi địa chỉ cho bộ phận hỗ trợ.
- **Trang bị chặn không mở được, còn lại đều bình thường**: nhiều khả năng thiết bị đang bật DNS mã hóa (trên Android là "DNS riêng tư", trong trình duyệt là "DNS bảo mật"), nên router không thấy được thiết bị đang tra tên trang nào. Hãy tắt cài đặt đó.
- **Kết nối xong thì không vào được máy in hay NAS**: tức là địa chỉ mạng nội bộ cũng bị gửi ra ngoài. Kiểm tra quy tắc chia luồng có loại trừ các dải riêng như 192.168.x.x không.
- **Hiệu năng router** là mức trần. CPU của router cũ chạy hết công suất khi gặp lưu lượng mã hóa, biểu hiện là cả nhà cùng chậm. Khi đó vấn đề không nằm ở đường truyền VPN.

## Một tài khoản, một router

Phần lớn các dịch vụ ràng buộc router với tài khoản (theo địa chỉ MAC). Một tài khoản ràng buộc một router, đổi router thì phải hủy ràng buộc trước. Nhờ vậy tài khoản chỉ thuộc về riêng bạn.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-03) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-03) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
