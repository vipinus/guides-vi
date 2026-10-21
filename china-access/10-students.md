# 10 · Du học sinh nên thiết lập VPN về Trung Quốc thế nào

Thứ du học sinh cần không phải "một đường truyền về Trung Quốc lúc nào cũng bật", mà là lấy được IP Trung Quốc một cách chắc chắn trong vài tình huống cụ thể: xem phim bộ và nghe nhạc, đăng nhập ngân hàng trực tuyến và ứng dụng dịch vụ công, săn vé, và thỉnh thoảng kiểm tra thiết bị từ xa giúp người nhà ở Trung Quốc. Mỗi tình huống đòi hỏi đường truyền một kiểu, còn mạng trường học lại có giới hạn riêng. Bài này đi qua từng tình huống: cần gì, thiết lập thế nào, khi nào ngắt kết nối, và cuối bài là danh sách việc làm trong mười phút trước khi vào học kỳ.

## Phim bộ, nhạc, livestream: chỉ cần IP Trung Quốc, nhưng phải chặn IPv6

Tencent Video, iQIYI, anime trên Bilibili, NetEase Cloud Music và QQ Music đều xét khu vực theo IP nguồn, kết nối đường truyền về Trung Quốc là đủ. Cái bẫy du học sinh hay mắc nhất là mạng trường và ký túc xá thường có IPv6: thiết bị ưu tiên IPv6, mà IPv6 không đi qua đường truyền, nên trang video vẫn thấy địa chỉ nước ngoài và báo "giới hạn bản quyền".

Cách xử lý là dùng đường truyền hoặc ứng dụng chặn IPv6 bên trong đường hầm, hoặc tắt IPv6 trên thiết bị. Cả ba cách kết nối của LeoTun đều đã chặn IPv6 từ phía đường truyền, không phải sửa gì trên thiết bị; cách dò lỗi chi tiết xem "Ở nước ngoài bị Tencent Video báo giới hạn bản quyền thì làm sao".

Chất lượng hình phụ thuộc băng thông qua biên giới. 8 đến 11 giờ tối giờ Bắc Kinh là giờ cao điểm, tương ứng khoảng sáng đến trưa ở châu Âu và Bắc Mỹ; nếu khung giờ đó 1080p cứ quay vòng thì hãy đổi sang lối ra Trung Quốc khác.

## Ngân hàng trực tuyến, Alipay, ứng dụng dịch vụ công: đăng nhập qua đường truyền về Trung Quốc, xong việc thì ngắt

Các ứng dụng ngân hàng, Alipay, CHSI (trang thông tin học vấn Trung Quốc) và Nền tảng dịch vụ chính phủ quốc gia đối xử với IP nước ngoài khác nhau: có nơi từ chối đăng nhập thẳng, có nơi bắt thêm mấy bước xác minh, có nơi cho đăng nhập nhưng chuyển tiền thì kích hoạt kiểm soát rủi ro. Điểm chung là chúng đều ghi lại IP đăng nhập của bạn, và nhảy qua nhảy lại giữa nước ngoài và Trung Quốc là dễ bị đánh dấu nhất.

Cách làm: khi cần làm những việc này, kết nối đường truyền về Trung Quốc trước rồi mới mở ứng dụng; xong việc thì thoát ứng dụng rồi mới ngắt đường truyền. Đừng vừa dùng một ứng dụng vừa liên tục chuyển qua lại giữa đường truyền về Trung Quốc và mạng tại chỗ.

Mã xác minh qua điện thoại mãi không tới thì không liên quan đến đường truyền; đó là chuyện chuyển vùng quốc tế của số điện thoại Trung Quốc khi ở nước ngoài. Trước khi xuất cảnh, hãy bật chuyển vùng quốc tế cho số đó hoặc đổi sang gói cước nhận được mã khi ở nước ngoài.

## 12306, săn vé concert: kết nối từ sớm, đừng đổi lúc thanh toán

12306 (hệ thống bán vé tàu Trung Quốc) đôi khi bắt xác minh thêm với IP nước ngoài, mà lúc săn vé thì thêm một bước xác minh là mất vé. Vài phút trước giờ mở bán, kết nối đường truyền về Trung Quốc, đăng nhập và chọn sẵn thông tin hành khách, đến giờ là bấm gửi ngay. Khi thanh toán chuyển sang Alipay hay ngân hàng trực tuyến, giữ nguyên đường truyền.

Các nền tảng bán vé như Damai và Maoyan cũng theo đúng lý đó.

## Ba giới hạn của mạng trường và ký túc xá

- IPv6: xem phần trên; dùng đường truyền có chặn IPv6.
- UDP bị hạn chế hoặc bóp tốc độ: khá nhiều mạng trường bóp, thậm chí chặn lưu lượng UDP. Giao thức hysteria2 mà Hiddify dùng chạy trên UDP, trên những mạng này lại kém ổn định hơn AnyConnect chạy trên TLS; một tài khoản dùng được cả hai, UDP không chạy thì chuyển sang AnyConnect.
- Trang đăng nhập mạng (captive portal): bắt Wi‑Fi trường xong thì xác thực trên trình duyệt trước, rồi mới bật đường truyền. Nếu ứng dụng đặt "tự kết nối khi khởi động", nó sẽ thử kết nối trước khi xác thực và thất bại; đợi thêm chút hoặc kết nối lại bằng tay.

## Về Trung Quốc nghỉ lễ: dùng cùng tài khoản theo chiều ngược lại

Về tới Trung Quốc, bạn cần Google, email của trường và các cơ sở dữ liệu bài báo; chỉ cần đổi khu vực của đường truyền từ Trung Quốc sang Nhật Bản, Mỹ hoặc một khu vực nước ngoài gần đó, không cần đổi tài khoản. 24 khu vực của LeoTun đều nằm trong cùng một tài khoản; truy cập Trung Quốc từ nước ngoài và truy cập dịch vụ nước ngoài từ Trung Quốc là hai chiều của cùng một việc.

Khi kết nối từ trong Trung Quốc, địa chỉ AnyConnect và Hiddify tự thay đổi để đối phó việc bị chặn, địa chỉ đã lưu trong ứng dụng không cần sửa; không kết nối được thì đổi khu vực hoặc đổi giao thức.

## Danh sách mười phút trước khi vào học kỳ

1. Cài ứng dụng (AnyConnect hoặc Hiddify) trên điện thoại và trên máy tính, mỗi máy đăng nhập hoặc quét mã QR để nhập.
2. Bắt Wi‑Fi ký túc xá, kết nối đường truyền về Trung Quốc, mở một trang kiểm tra IPv6 để xác nhận IPv6 không dùng được hoặc hiện địa chỉ đại lục.
3. Mở Tencent Video, phát một tập bất kỳ để xác nhận không bị báo giới hạn bản quyền.
4. Đăng nhập ứng dụng ngân hàng một lần để xác nhận vào được, rồi thoát ứng dụng và ngắt đường truyền.
5. Ghi lại cách liên hệ bộ phận hỗ trợ của bên cung cấp đường truyền; có sự cố thì đọc hướng dẫn khắc phục sự cố trước rồi hãy hỏi.

## Câu hỏi thường gặp

**Dùng VPN về Trung Quốc có ảnh hưởng tài khoản mạng trường của du học sinh không?** Không. Đường truyền chỉ đưa lưu lượng của bạn tới lối ra ở Trung Quốc, mạng trường chỉ thấy một kết nối đã mã hóa. Quy định sử dụng của đa số trường chỉ cấm tải nội dung vi phạm bản quyền và tấn công mạng, việc cá nhân truy cập dịch vụ của nước mình không nằm trong đó; chưa chắc thì xem quy định sử dụng mạng (acceptable use policy) của trường.

**Một tài khoản dùng chung với bạn cùng phòng được không?** Tùy gói, một tài khoản cho 2 (Cá nhân), 4 (Gia đình) hoặc 8 (Doanh nghiệp) thiết bị trực tuyến cùng lúc, dùng chung với người nhà hay bạn cùng phòng nằm trong phạm vi quy định cho phép. Nhưng với những việc như ngân hàng trực tuyến thì mỗi người nên dùng tài khoản riêng cho an toàn, tránh nhiều người liên tục chuyển đổi trên cùng đường truyền mà kích hoạt kiểm soát rủi ro.

**Sao ở ký túc xá Hiddify chậm mà AnyConnect lại bình thường?** Nhiều khả năng mạng trường hạn chế UDP. Giao thức hysteria2 của Hiddify dựa trên UDP, bị bóp thì biểu hiện là chậm hoặc rớt; AnyConnect chạy trên TLS, giống như vào một trang web HTTPS, nên không bị ảnh hưởng.

**Chơi game máy chủ Trung Quốc qua đường truyền về Trung Quốc được không?** Đăng nhập được, nhưng độ trễ phụ thuộc khoảng cách thực tế từ bạn tới lối ra ở Trung Quốc. Phần độ trễ đó là cố định; game theo lượt và MOBA thì chấp nhận được, game bắn súng thì sẽ thấy rõ.

**Tốt nghiệp về Trung Quốc rồi thì tài khoản còn dùng được không?** Được. Cùng tài khoản đó, ở trong Trung Quốc chọn khu vực nước ngoài là vào được Google, GitHub, email của trường và các cơ sở dữ liệu bài báo.

## Đọc thêm

- [Ở nước ngoài bị Tencent Video báo giới hạn bản quyền thì làm sao](https://www.leotun.com/vi/guides/overseas-video?utm_source=github&utm_content=china-access-10)
- [Cách chọn VPN có IP Trung Quốc](https://www.leotun.com/vi/guides/choose-china-vpn?utm_source=github&utm_content=china-access-10)
- [Tải ứng dụng AnyConnect](https://www.leotun.com/vi/anyconnect?utm_source=github&utm_content=china-access-10)
- [Ứng dụng Hiddify và cách nhập link subscription](https://www.leotun.com/vi/singbox?utm_source=github&utm_content=china-access-10)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/students?utm_source=github&utm_content=china-access-10

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=china-access-10) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=china-access-10) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
