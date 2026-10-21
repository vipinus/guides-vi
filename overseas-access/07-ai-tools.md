# 07 · Dùng các công cụ AI (ChatGPT, Claude, Gemini và các dịch vụ khác)

## Bạn thấy gì

Mở các trang này từ trong Trung Quốc, triệu chứng mỗi lần một khác, nên rất dễ đoán sai:

| Triệu chứng | Nguyên nhân khả dĩ nhất |
|---|---|
| Trang hoàn toàn không mở được | Không với tới được ở tầng mạng |
| Trang mở được nhưng đăng nhập bị treo | Không với tới được dịch vụ bên thứ ba dùng để đăng nhập |
| Trò chuyện được, nhưng gửi nội dung dài là bị ngắt | Kết nối không ổn định |
| Thông báo "không khả dụng ở quốc gia của bạn" | Nhà cung cấp từ chối theo IP |
| Thông báo tài khoản bị khóa hoặc cần xác minh | Xem "Điểm quan trọng nhất" bên dưới |

## Điểm quan trọng nhất: ổn định quan trọng hơn nhanh

Các dịch vụ này đặc biệt nhạy cảm với việc **IP thay đổi liên tục**. Nếu kết nối của bạn lúc thì đi ra qua Nhật Bản, lúc lại qua Mỹ, thứ nhà cung cấp thấy là "cùng một tài khoản đi qua mấy quốc gia trong vài phút", rất dễ kích hoạt kiểm soát rủi ro — nhẹ thì bị bắt xác minh lại, nặng thì bị khóa tài khoản.

Vì vậy khi dùng công cụ AI:

- **Chọn một khu vực và dùng cố định**; đừng đổi liên tục
- Cố gắng để việc đăng ký và việc dùng hằng ngày ở **cùng một khu vực**
- Nếu đăng ký qua Mỹ thì từ đó về sau cứ dùng Mỹ

Điều này quan trọng hơn nhiều so với chuyện "khu vực nào nhanh hơn". Chậm một chút chỉ là đợi lâu hơn một chút; tài khoản có vấn đề thì phải làm lại từ đầu.

## Chọn khu vực nào

Nhật Bản và Singapore gần, độ trễ thấp, trò chuyện hằng ngày thấy mượt nhất. Nhưng có hai điều cần để ý:

- Một số dịch vụ khả dụng khác nhau theo khu vực, nên trước khi đăng ký hãy xác nhận dịch vụ mở bình thường từ khu vực đó
- Nếu tính năng bạn muốn dùng có liên quan đến thanh toán, quốc gia của phương thức thanh toán tốt nhất đừng mâu thuẫn với khu vực bạn chọn

Chưa chắc thì dùng gói dùng thử miễn phí, mở từng dịch vụ bạn định dùng để xem, rồi hãy quyết định dùng khu vực nào lâu dài.

## Chia luồng theo ứng dụng trong ứng dụng VPN rất hữu ích

Công cụ AI thường được dùng trên trình duyệt hoặc ứng dụng riêng. Hãy cho đúng cái đó vào danh sách đi qua đường truyền, còn các ứng dụng khác để dùng mạng tại chỗ. Lợi ích:

- Các ứng dụng giao đồ ăn, gọi xe và thanh toán của Trung Quốc không bị ảnh hưởng
- Khu vực của bạn không bị "đổi bị động" vì một ứng dụng khác
- Tiết kiệm dữ liệu

## Dòng lệnh và API

Nếu bạn gọi API bằng công cụ dòng lệnh hoặc code, lưu ý các chương trình đó **chưa chắc đã đọc proxy của hệ thống**. Trường hợp này xem [05 · Linux và dòng lệnh](05-linux-server.md).

## Một lời nhắc

Đừng dán bí mật công ty, dữ liệu khách hàng hay code chưa phát hành vào các dịch vụ này. Chuyện này không liên quan gì đến việc bạn dùng đường truyền nào — nội dung đã gửi đi là nằm trên máy chủ của bên kia.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=overseas-access-07) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=overseas-access-07) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
