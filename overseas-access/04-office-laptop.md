# 04 · Dùng máy tính công ty: không có quyền quản trị, đang chạy VPN công ty

Máy tính công ty có ba giới hạn: không được cài phần mềm chưa được duyệt, không có quyền quản trị, và thường đã kết nối sẵn VPN công ty. Ở đây VPN toàn máy hoặc không cài được, hoặc giành giật với VPN công ty. Công cụ đúng là Web Proxy — một tiện ích trình duyệt chỉ đưa yêu cầu của chính trình duyệt này qua đường truyền, còn mạng nội bộ công ty, ứng dụng email và VPN công ty đều giữ nguyên, không cần quyền quản trị. Bài này nói cách thiết lập, nó làm được gì, điều gì không nên làm, và cách sống hòa thuận với chính sách IT của công ty.

## Vì sao là Web Proxy

- Không cần cài ứng dụng: nó chỉ là tiện ích trình duyệt, mà đa số công ty cho cài tiện ích nhưng không cho cài phần mềm.
- Không cần quyền quản trị: tiện ích chạy trong không gian người dùng, không đụng tới cài đặt mạng của hệ thống.
- Chạy song song với VPN công ty: VPN công ty nắm tuyến đường của hệ thống, còn Web Proxy chỉ nằm ở tầng trình duyệt, hai bên không ảnh hưởng nhau; trang nội bộ công ty vẫn đi qua VPN công ty.
- Theo thiết kế không có kết nối nào để rớt: proxy làm việc theo từng yêu cầu, không có kết nối duy trì lâu, nên mạng công ty chập chờn bạn cũng không thấy.

## Thiết lập trong hai bước

1. Cài tiện ích ZeroOmega (bản kế tục của SwitchyOmega) vào trình duyệt; trang Proxy của trang này có link cài cho từng trình duyệt.
2. Đăng nhập trang này, trên trang Proxy bấm nút sao chép link khôi phục tiện ích, rồi dán vào "Import/Export" → "Restore from online" (khôi phục từ trực tuyến) trong tiện ích. Khu vực và địa chỉ được nhập một lượt; sau đó bấm biểu tượng tiện ích để chọn khu vực, và nhập tài khoản, mật khẩu của trang này vào hộp đăng nhập mà trình duyệt hiện ra.
3. Nên dùng một hồ sơ trình duyệt riêng (hoặc một trình duyệt khác) chỉ để đi proxy, còn trình duyệt làm việc thì để mạng tại chỗ, để hai bên không lẫn vào nhau.

## Hợp với việc gì, tình huống nào cần cách khác

- Hợp: tra cứu, mở Google, GitHub, Stack Overflow, các trang tài liệu nước ngoài, ChatGPT bản web và email trên web.
- Cần cách khác: ứng dụng video, phần mềm máy tính và công cụ dòng lệnh mặc định không dùng cài đặt proxy của trình duyệt (với dòng lệnh, bạn có thể điền địa chỉ proxy vào biến môi trường http_proxy; xem bài về Linux).
- Cần cách khác: xem trang video Trung Quốc (với người ở nước ngoài) — trang video còn kiểm tra cả IPv6 và DNS, mà Web Proxy không lo phần đó; tình huống này cần VPN toàn máy.

## Sống hòa thuận với chính sách IT

Mọi thứ trên máy tính công ty đều có thể bị công ty kiểm tra, tiện ích cũng không ngoại lệ. Hãy đọc quy định sử dụng của công ty trước: thứ đa số công ty cấm là phần mềm chưa được duyệt và việc lách chính sách bảo mật, còn tiện ích trình duyệt truy cập trang web bên ngoài thường thuộc vùng xám; chưa chắc thì hỏi bộ phận IT.

Đừng cài VPN toàn máy (Cisco, Mạng riêng, Hiddify) lên máy tính công ty để lách chính sách công ty: chúng thay đổi tuyến đường của hệ thống, kích hoạt cảnh báo của phần mềm quản lý thiết bị đầu cuối, và còn mang cả lưu lượng mạng nội bộ công ty ra ngoài. Web Proxy chỉ ảnh hưởng một trình duyệt, rủi ro thấp nhất.

Tách bạch tài khoản công việc và tài khoản cá nhân: đừng đăng nhập tài khoản công ty trên trình duyệt đi proxy, và đừng đăng nhập tài khoản cá nhân trên trình duyệt làm việc.

## Câu hỏi thường gặp

**Công ty cấm cài tiện ích thì sao?** Thì dùng điện thoại hoặc máy tính cá nhân của bạn. Đừng dùng phần mềm portable không rõ nguồn gốc để lách quy định.

**Tiện ích có thấy lưu lượng mạng nội bộ công ty của tôi không?** Không. Theo quy tắc chia luồng, tên miền nội bộ công ty kết nối thẳng, không qua proxy; ở chế độ toàn cục thì chúng chỉ được gửi tới máy chủ proxy rồi quay về, và thứ proxy thấy là tên miền, không phải nội dung. Cho chắc thì dành cho proxy một hồ sơ trình duyệt riêng.

**Đang bật VPN công ty thì proxy có còn dùng được không?** Được, hai bên không xung đột. Một số rất ít VPN công ty ép mọi lưu lượng đi qua lối ra của công ty và vô hiệu hóa cài đặt proxy; khi đó tiện ích báo không kết nối được, và cách duy nhất là tắt VPN công ty.

**Trên máy Mac của công ty có giống vậy không?** Giống; tiện ích cho Chrome, Edge và Firefox đều có bản cho Mac. Safari không có tiện ích này, hãy dùng trình duyệt khác.

## Đọc thêm

- [Trang thiết lập proxy: cài tiện ích và link khôi phục](https://www.leotun.com/vi/httpproxy?utm_source=github&utm_content=overseas-access-04)
- [Web Proxy là gì và khi nào nên dùng](https://www.leotun.com/vi/guides/web-proxy?utm_source=github&utm_content=overseas-access-04)
- [Cho máy chủ Linux và công cụ dòng lệnh đi qua đường truyền thế nào](https://www.leotun.com/vi/guides/linux-server?utm_source=github&utm_content=overseas-access-04)
- [Mỗi cách kết nối hợp với tình huống nào](https://www.leotun.com/vi/guides/choose-connection?utm_source=github&utm_content=overseas-access-04)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/office-laptop?utm_source=github&utm_content=overseas-access-04

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=overseas-access-04) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=overseas-access-04) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
