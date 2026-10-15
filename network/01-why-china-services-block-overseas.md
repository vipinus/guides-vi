# 01 · Truy cập Trung Quốc từ nước ngoài hoạt động thế nào

## Bạn sẽ thấy gì

Bạn đang ở nước ngoài, mở iQIYI, Bilibili hay NetEase Cloud Music thì nhận được thông báo "Nội dung này chỉ có ở Trung Quốc đại lục"; ngân hàng trực tuyến và 12306 (trang đặt vé tàu) không vào được, hoặc mã xác minh mãi không tới.

## Chỉ có một nguyên nhân: IP của bạn được đăng ký ở đâu

Khi thiết bị lên mạng, nhà mạng cấp cho nó một địa chỉ IP công cộng. Có một cơ sở dữ liệu toàn cầu cho biết mỗi địa chỉ thuộc quốc gia nào, nhà mạng nào. Các nền tảng video và nhạc Trung Quốc chỉ mua bản quyền cho **Trung Quốc đại lục** và không được phép phát ra ngoài, nên cứ thấy IP nước ngoài là họ từ chối.

Ngân hàng và trang bán vé thì theo logic khác. Với họ, đây không phải chuyện bản quyền mà là kiểm soát rủi ro: đăng nhập từ IP nước ngoài bị coi là rủi ro cao và bị chặn luôn.

## Hướng giải quyết

Làm sao để IP mà máy chủ nhìn thấy là IP Trung Quốc đại lục. Cách làm là gửi lưu lượng của bạn tới một máy chủ đặt trong đại lục trước, rồi máy chủ đó thay bạn truy cập trang đích. Trang đích thấy IP của máy chủ đó và cho qua.

Đó chính là việc mà một "đường truyền về Trung Quốc" làm: cho lưu lượng của bạn đi ra bằng một IP Trung Quốc đại lục.

## Ba hiểu lầm thường gặp

- **Đổi DNS không giải quyết được.** DNS chỉ dịch tên miền ra địa chỉ; trang đích xem IP nguồn của bạn chứ không xem bạn dùng DNS nào.
- **Một số ít nền tảng còn xem cả khu vực của hệ thống.** Ngoài IP, vài nền tảng còn kiểm tra ngôn ngữ thiết bị và khu vực của kho ứng dụng; gặp trường hợp đó thì đổi luôn khu vực hệ thống.
- **Tốc độ phụ thuộc vào chất lượng đường truyền giữa hai đầu.** Đoạn xuyên biên giới từ nước ngoài về đại lục mới là nút thắt, nên chọn điểm vào gần bạn và có tuyến tối ưu về đại lục quan trọng hơn cấu hình của chính máy chủ.

## Đọc thêm

- [Cách kết nối nào hợp với tình huống nào](02-choose-your-connection-method.md)
- [Danh sách kiểm tra khi không kết nối được, chậm hoặc hay rớt](../troubleshooting/01-cannot-connect-slow-drops.md)

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=network-01) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=network-01) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mỗi người bạn bạn mời trả phí sẽ giúp cả hai nhận 20 ngày gói Cá nhân, ưu đãi không có hạn kết thúc
