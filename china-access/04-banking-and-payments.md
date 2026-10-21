# 04 · Ngân hàng trực tuyến, ứng dụng ngân hàng và thanh toán

## Hệ thống kiểm soát rủi ro của ngân hàng xét những gì

Ngân hàng không chỉ nhìn IP. Họ gộp nhiều tín hiệu lại rồi chấm điểm:

1. **Nơi đăng ký của IP**: IP nước ngoài là bị nâng mức rủi ro ngay.
2. **Thẻ SIM**: ứng dụng ngân hàng đọc thông tin SIM, thẻ của nhà mạng nước ngoài bị tính điểm trừ.
3. **Dấu vân tay thiết bị**: thiết bị mới, hoặc máy đã jailbreak hay root.
4. **Hành vi**: chuyển khoản lớn ngay lần đầu đăng nhập từ nơi mới.

Vì vậy tình huống thường gặp là: đổi sang IP Trung Quốc thì đăng nhập được, nhưng chuyển khoản vẫn bị chặn. IP chỉ giải quyết được mục đầu tiên.

## Bạn có thể làm gì

- Sau khi đổi sang IP Trung Quốc, **làm giao dịch nhỏ trước** để hệ thống kiểm soát rủi ro quen với môi trường này, rồi mới làm giao dịch lớn.
- Giữ thẻ SIM Trung Quốc và bật chuyển vùng; cả mã xác minh lẫn bước kiểm tra SIM đều dựa vào nó.
- Cài bản ứng dụng ngân hàng dành cho Trung Quốc khi có thể; vướng khu vực của kho ứng dụng thì xem [iOS không cho cài ứng dụng thì làm sao](../client/06-ios-app-store.md) ở thư mục bên cạnh.
- Nếu bị chặn thì đừng thử đi thử lại. Thất bại nhiều lần sẽ kích hoạt đóng băng tạm thời, gọi tổng đài chăm sóc khách hàng để mở khóa là nhanh nhất.

## Alipay và WeChat Pay

Cả hai dễ dãi với IP hơn ngân hàng, thường dùng được với IP nước ngoài, nhưng tài khoản liên kết thẻ nước ngoài bị giới hạn về số tiền và nơi dùng. Khi cần thanh toán bằng thẻ Trung Quốc hoặc chuyển tiền cho người bán ở Trung Quốc, đổi sang IP Trung Quốc sẽ suôn sẻ hơn nhiều.

## Điều không nên làm

Đừng làm việc ngân hàng trên Wi-Fi công cộng, dù có đi qua đường truyền hay không. Đường truyền chỉ đổi IP lối ra của bạn, không mã hóa thêm gì cho bạn từ đó đến ngân hàng; độ an toàn đến từ chính lớp mã hóa của ứng dụng ngân hàng.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=china-access-04) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=china-access-04) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
