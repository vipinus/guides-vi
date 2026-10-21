# 12 · Thiết lập khi đi công tác và du lịch

Chuyến đi ngắn ra nước ngoài hay chuyến công tác tới Trung Quốc thì không cần router, cũng không cần tìm hiểu giao thức: cài ứng dụng Cisco (Cisco Secure Client) trên điện thoại, kết nối thử một lần trước khi đi, xuống máy bay là dùng được ngay. Hai chiều thực ra là một: ở nước ngoài cần Google, email công ty và bản đồ thì chọn một khu vực nước ngoài gần đó; khi ở Trung Quốc muốn xem video Trung Quốc hay đăng nhập ngân hàng trực tuyến thì chọn khu vực Trung Quốc. Bài này nói về mười phút chuẩn bị trước khi đi, hai cái bẫy thường gặp của mạng khách sạn và sân bay, và cách dùng ngân hàng trực tuyến cùng ứng dụng thanh toán.

## Mười phút trước khi đi

1. Cài Cisco Secure Client trên điện thoại (App Store / Google Play, hoặc bộ cài trên trang Cisco của trang này), đăng nhập trang này rồi bấm một lá cờ để sao chép địa chỉ của khu vực đó và nhập vào, sau đó kết nối thử một lần bằng tài khoản và mật khẩu của trang này để chắc là chạy được.
2. Sao chép thêm địa chỉ của hai khu vực nữa và lưu trong ứng dụng: một khu vực gần nơi bạn đến và một khu vực dự phòng. Mạng ở đó sẽ khác, và khu vực tốt nhất thường không giống ở nhà.
3. Ghi lại bốn tên miền (leotun.com → 7d24hrs.com → 7x24btc.com → anyfq.com) và lối vào ít nhất một nhóm hỗ trợ, để nếu có trục trặc ở nơi bạn không rành mạng thì vẫn tìm được người giúp.
4. Cài thêm một cái trên laptop, hoặc dùng tiện ích Web Proxy; máy tính công ty không cài được ứng dụng thì cách này vẫn dùng được.

## Sau khi tới nơi

- Nếu đã đổi sang SIM địa phương hoặc bật chuyển vùng, ứng dụng cứ thế kết nối, không phải cấu hình lại; nếu bản thân dữ liệu chuyển vùng đã đi ra nước ngoài thì kết nối đường truyền chỉ để cố định khu vực lối ra.
- Ở nước ngoài, cần Google, Gmail, email công ty và bản đồ: chọn một khu vực nước ngoài gần đó để có tốc độ tốt nhất.
- Khi ở Trung Quốc, muốn xem Tencent Video và iQIYI, nghe NetEase Cloud Music hay đăng nhập ngân hàng trực tuyến: chọn khu vực Trung Quốc. Trang Trung Quốc đi ra bằng IP Trung Quốc còn trang nước ngoài vẫn ra ở nước ngoài, nên ở Trung Quốc mà kết nối khu vực Trung Quốc vẫn không cản bạn tiếp tục dùng Gmail.
- Nếu từ trong Trung Quốc không kết nối được khu vực nước ngoài: đổi khu vực, chuyển sang dữ liệu di động, vẫn không được thì chuyển sang Hiddify hoặc OpenVPN; việc chặn ba giao thức này độc lập với nhau.

## Hai cái bẫy của mạng khách sạn, sân bay và quán cà phê

- Trang đăng nhập (captive portal): bắt Wi‑Fi xong hãy hoàn tất xác thực trong trình duyệt trước, rồi mới bật đường truyền. Ứng dụng đặt tự động kết nối sẽ thử trước khi xác thực và thất bại; đợi một lát hoặc kết nối lại thủ công.
- Hạn chế UDP: không ít mạng khách sạn và sân bay bóp hoặc chặn UDP. Cisco chạy trên TLS nên không bị ảnh hưởng, đó cũng là lý do Cisco được khuyên dùng hàng đầu khi đi lại; nếu bạn đang dùng Hiddify hay Mạng riêng mà chậm hoặc rớt thì chuyển sang Cisco.

## Ngân hàng trực tuyến, thanh toán, 12306

Các ứng dụng này ghi lại IP đăng nhập, và nhảy qua nhảy lại giữa nước ngoài và Trung Quốc là thứ dễ kích hoạt kiểm soát rủi ro nhất. Khi cần làm việc gì, hãy kết nối khu vực Trung Quốc trước rồi mới mở ứng dụng; xong việc thì thoát ứng dụng rồi mới ngắt kết nối. Trong chuyến đi, đừng dùng cùng một ngân hàng trực tuyến trong khi liên tục chuyển qua lại giữa hai loại mạng.

Mã xác minh qua SMS không tới thì không liên quan tới đường truyền; đó là chuyện chuyển vùng của số điện thoại. Trước khi đi, hãy bật chuyển vùng cho số Trung Quốc của bạn hoặc đổi sang gói cước nhận được mã khi ở nước ngoài.

## Câu hỏi thường gặp

**Chuyến đi chỉ vài ngày. Có cần mua một tháng không?** Không. Nhận gói dùng thử miễn phí 4 giờ, hoặc nạp điểm và trả theo ngày: gói Cá nhân tốn 1 điểm mỗi ngày, khoảng 0,32 đô la Mỹ một ngày, rất hợp cho vài ngày.

**Điện thoại và laptop kết nối cùng lúc được không?** Được. Tùy gói, một tài khoản có 2 / 4 / 8 thiết bị trực tuyến cùng lúc (Cá nhân / Gia đình / Doanh nghiệp), gói Cá nhân vừa đúng một điện thoại cộng một laptop.

**Sao đi lại lại khuyên dùng Cisco chứ không phải Hiddify?** Ở mạng lạ, điều đáng lo nhất là UDP bị hạn chế. Cisco chạy trên TLS, giống như vào một trang HTTPS, nên đi qua được hầu như mọi nơi; Hiddify nhanh hơn ở mạng mất gói nhiều, nhưng không chạy khi UDP bị hạn chế. Cài cả hai, cái này không được thì chuyển cái kia là chắc ăn nhất.

**Ở nước ngoài dùng khu vực Trung Quốc có làm trang tại chỗ chậm đi không?** Trang tại chỗ mượt nhất khi kết nối thẳng: xem xong nội dung Trung Quốc thì ngắt kết nối, hoặc chỉ kết nối khi cần.

## Đọc thêm

- [Tải và thiết lập Cisco AnyConnect](https://www.leotun.com/vi/anyconnect?utm_source=github&utm_content=china-access-12)
- [Du học sinh nên thiết lập VPN về Trung Quốc thế nào](https://www.leotun.com/vi/guides/students?utm_source=github&utm_content=china-access-12)
- [Cách liên hệ với chúng tôi và không bao giờ mất liên lạc](https://www.leotun.com/vi/guides/stay-in-touch?utm_source=github&utm_content=china-access-12)
- [VPN về Trung Quốc: miễn phí hay trả phí](https://www.leotun.com/vi/guides/free-vs-paid?utm_source=github&utm_content=china-access-12)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/travel?utm_source=github&utm_content=china-access-12

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=china-access-12) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=china-access-12) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
