# 04 · Chúng tôi khác các VPN khác ở chỗ nào

VPN trên thị trường đại khái chia làm ba loại: các thương hiệu quốc tế lớn phục vụ người dùng khắp thế giới, các nhà cung cấp proxy quen thuộc trong cộng đồng nói tiếng Trung (tiếng Trung gọi là “jichang”, chuyên bán lại subscription proxy), và đủ loại phần mềm miễn phí. LeoTun tự vận hành máy chủ từ năm 2006 và chỉ làm một việc: giữ kết nối ổn định theo cả hai chiều cho người dùng ở Trung Quốc đại lục và người gốc Hoa ở nước ngoài. Bài này đặt chúng tôi cạnh từng loại sản phẩm, so sánh từng mục: loại nào hợp với ai, và chúng tôi làm thế nào, để bạn thấy rõ trước khi trả tiền.

## Định vị của chúng tôi trong một câu

Chúng tôi là dịch vụ **tối ưu riêng cho môi trường mạng ở Trung Quốc đại lục**, không phải đại lý bán lại đường truyền quốc tế. Chất lượng cổng ra quốc tế của China Telecom, China Unicom và China Mobile chênh nhau rất nhiều; chúng tôi tinh chỉnh riêng cho từng nhà mạng và gợi ý khu vực khác nhau cho từng nhà mạng. Chúng tôi có điểm tiếp nhận ngay trong Trung Quốc, để người dùng có băng thông rộng chỉ ở mức tạm cũng có điểm vào ổn định. Khi môi trường mạng ở Trung Quốc thay đổi, chúng tôi liên tục điều chỉnh cổng và giao thức, chứ không cài một lần rồi bỏ đó.

Chiều ngược lại, khi người ở nước ngoài cần dùng dịch vụ ở Trung Quốc, chỉ cần chọn khu vực Trung Quốc bằng chính tài khoản đó: trang web Trung Quốc đi ra bằng IP Trung Quốc, còn trang ở ngoài Trung Quốc vẫn đi ra ở nước ngoài. Truy cập Trung Quốc từ nước ngoài và truy cập dịch vụ nước ngoài từ Trung Quốc là hai chiều của cùng một việc.

## So với các thương hiệu quốc tế lớn

- Điểm mạnh của họ: hàng chục quốc gia, hàng nghìn máy chủ, ứng dụng hoàn thiện, cam kết không lưu nhật ký có kiểm toán độc lập. Nếu bạn ở châu Âu, châu Mỹ và chỉ muốn mã hóa khi dùng Wi‑Fi công cộng hay xem dịch vụ streaming của nước khác, đó là lựa chọn tốt.
- Điểm yếu của họ: sản phẩm không được thiết kế cho mạng Trung Quốc. Giao thức độc quyền có dấu hiệu cố định, một khi bị nhận diện ở Trung Quốc thì cả ứng dụng ngừng hoạt động; họ không có điểm tiếp nhận trong Trung Quốc, nên với nhu cầu xem video Trung Quốc từ nước ngoài thì hoặc không có tính năng này, hoặc dùng IP Hồng Kông, Đài Loan — mà Tencent Video và iQIYI chặn y như thường.
- Cách chúng tôi làm: chỉ dùng giao thức chuẩn (AnyConnect, OpenVPN, Hiddify, Tailscale, Web Proxy HTTPS), ứng dụng lấy từ chính hãng hoặc cộng đồng mã nguồn mở. Thứ có thể bị chặn chỉ là một địa chỉ cụ thể, đổi địa chỉ là xong; ứng dụng không bị đánh sập.
- Những gì chúng tôi chấp nhận đánh đổi: 24 khu vực, mỗi khu vực có nhiều máy phía sau, khi kết nối tự chọn máy rảnh nhất; ứng dụng là bản chính thức của hãng và cộng đồng mã nguồn mở, thiết lập bằng quét mã QR hoặc nhập một chạm; không có báo cáo kiểm toán của bên thứ ba; những gì chúng tôi ghi lại và không ghi lại đều viết rõ trên trang Giới thiệu — chúng tôi dựa vào việc nói rõ ràng chứ không dựa vào con dấu chứng nhận.

## So với các nhà cung cấp proxy

- Điểm mạnh của nhà cung cấp proxy: rẻ, nhiều node, dán link subscription là dùng được ngay, người thích vọc ứng dụng thì được thoải mái tùy chỉnh.
- Điểm yếu của nhà cung cấp proxy: phần lớn là cá nhân hoặc nhóm nhỏ thuê máy ở nước ngoài để bán lại lưu lượng, không có điểm tiếp nhận riêng trong Trung Quốc, chất lượng lối ra lên xuống theo đường truyền đi thuê; ôm tiền biến mất, đổi tên, đóng cửa là chuyện thường gặp, trả tiền một năm chưa chắc đã dùng đủ một năm; ứng dụng gần như để người dùng tự mày mò, có sự cố thì không ai chịu trách nhiệm.
- Cách chúng tôi làm: máy là của chúng tôi, lối ra ở Trung Quốc là máy đăng ký tên thật của chính chúng tôi tại các nhà cung cấp đám mây ở đại lục; một tài khoản có sáu cách kết nối, giải pháp router cho cả nhà và nhóm hỗ trợ 24 giờ là những thứ nhà cung cấp proxy không có; chúng tôi hoạt động từ 2006 đến nay, tài khoản, thời hạn và giá không thay đổi trước và sau khi đổi tên.
- Giá của chúng tôi: gói Cá nhân 5 đô la mỗi tháng, gói Gia đình 10 đô la, gói Doanh nghiệp 20 đô la, đã bao gồm máy riêng, sáu cách kết nối và nhóm hỗ trợ 24 giờ; bạn chỉ chọn khu vực, phía sau mỗi khu vực hệ thống tự chọn máy rảnh nhất, không cần tự đo tốc độ chọn node.

## So với phần mềm miễn phí

- Điểm mạnh của hàng miễn phí: không tốn tiền, thỉnh thoảng tra cứu gì đó thì đủ dùng.
- Điểm yếu của hàng miễn phí: băng thông lối ra ở đại lục tính tiền theo lưu lượng, nên dịch vụ miễn phí chỉ sống được bằng cách nhồi nhiều người dùng, bóp tốc độ hoặc bán dữ liệu; loại tiện ích trình duyệt chỉ đưa yêu cầu web qua proxy, video, ứng dụng và DNS hệ thống đều không đi qua; file cài không rõ nguồn gốc tự nó đã là rủi ro, xem "Cách nhận biết phần mềm VPN rủi ro".
- Cách chúng tôi làm: dùng thử miễn phí 4 giờ không cần thẻ tín dụng, để bạn kiểm hàng; trả theo ngày (bằng điểm) cho người thỉnh thoảng mới dùng; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân) — nguồn thời gian miễn phí lâu dài.
- Cách chúng tôi sắp xếp: thời gian miễn phí đến từ 4 giờ dùng thử và thưởng mời bạn; dùng lâu dài thì trả theo tháng, theo năm hoặc theo ngày.

## Sáu cách kết nối, một tài khoản

Mạng riêng (Tailscale): đăng nhập một lần là trực tuyến mãi, đổi khu vực ngay trong menu. Cisco AnyConnect: tương thích tốt nhất, có sẵn trong hệ thống hoặc dùng ứng dụng chính thức. OpenVPN: dành cho router, NAS và Linux. Web Proxy: chỉ trình duyệt đi qua, theo thiết kế không có kết nối nào để rớt. Hiddify: chịu mất gói tốt, tốc độ tốt nhất. Router: cả nhà cùng vào mạng, cho TV, đầu thu và thiết bị của ông bà.

Mỗi kiểu mạng có một cách hợp nhất, nên bạn được cả sáu: cùng một tài khoản, đổi lúc nào cũng được — mạng trường hạn chế UDP thì chuyển từ Hiddify sang AnyConnect, băng thông rộng chập chờn thì chuyển sang Web Proxy. Chọn thế nào, xem "Mỗi cách kết nối hợp với tình huống nào".

## Quy định tài khoản

- Tài khoản có ba gói Cá nhân, Gia đình và Doanh nghiệp, lần lượt cho 2, 4 và 8 thiết bị trực tuyến cùng lúc; khu vực, lưu lượng và cách kết nối ở cả ba gói đều như nhau. Cài trên bao nhiêu thiết bị cũng được, chỉ giới hạn số kết nối cùng lúc. Khi số thiết bị trực tuyến cùng lúc vượt giới hạn của gói, bạn có thể tạm nâng hạng tài khoản (thời gian còn lại được quy đổi ngang giá theo giá gói) rồi dùng xong đổi lại.
- Đổi qua lại giữa ba gói lúc nào cũng được, thời gian còn lại quy đổi ngang giá (Gia đình và Doanh nghiệp lần lượt bằng 2 lần và 4 lần giá Cá nhân); cả ba gói đều dùng được router, một người dùng thì gói Cá nhân là đủ.
- Hoàn tiền theo tỷ lệ thời gian đã dùng, lúc nào cũng được, xử lý thủ công; không cam kết thời gian tiền về cụ thể.
- Tốc độ: chúng tôi cam kết xem YouTube mượt, kể cả giờ cao điểm buổi tối, với điều kiện băng thông rộng của bạn tốt: China Unicom ở miền Bắc hoặc China Telecom ở miền Nam Trung Quốc. Ngoại lệ là băng thông rộng dùng chung của khu chung cư (loại mạng do ban quản lý khu dân cư chia lại). Nếu một khu vực chậm thì đổi khu vực hoặc đổi cách kết nối.
- Cấu hình Hiddify và OpenVPN gắn với tài khoản của bạn, đổi mật khẩu là thu hồi các cấu hình cũ: mất điện thoại hay lộ link thì chỉ cần đổi mật khẩu một lần là lấy lại được, sau đó nhập lại là xong.

## Cách chúng tôi làm việc

- Chúng tôi chỉ giữ thông tin cần cho việc tính phí. Không ghi lại bạn truy cập gì, không chèn quảng cáo, không bán dữ liệu.
- Mọi ứng dụng đều đến từ hãng chính thức và các tổ chức mã nguồn mở có tiếng: Cisco, OpenVPN, Hiddify và Tailscale, phản chiếu nguyên bản, không sửa đổi; cấu hình bằng quét mã QR hoặc nhập một chạm.
- Khu vực Trung Quốc chạy trên máy ở đại lục, IP lối ra đều ở Trung Quốc đại lục.

## Câu hỏi thường gặp

**Các bạn có an toàn hơn các thương hiệu quốc tế lớn không?** Độ mạnh mã hóa tương đương, đều dùng giao thức chuẩn. Khác nhau ở mô hình tin cậy: thương hiệu lớn dựa vào báo cáo kiểm toán; chúng tôi chỉ giữ thông tin cần cho tính phí, và mọi ứng dụng đều đến từ hãng chính thức và các tổ chức mã nguồn mở có tiếng.

**Sao không cung cấp hàng trăm node như nhà cung cấp proxy?** Nhiều node không có nghĩa là ổn định hơn. Phía sau mỗi khu vực của chúng tôi có nhiều máy, khi kết nối hệ thống tự chọn máy rảnh nhất, bạn không phải tự đo tốc độ chọn node; địa chỉ nào bị chặn thì được thay tự động, địa chỉ trong ứng dụng của bạn không cần sửa.

**Giá có rẻ hơn được không?** Gói Cá nhân 5 đô la mỗi tháng, mua càng lâu giảm càng nhiều (giảm 5% → giảm 10% → giảm 20%); trả theo ngày bằng điểm khoảng 0,32 đô la một ngày; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), không giới hạn số người. Đăng ký còn được dùng thử miễn phí 4 giờ.

**Làm sao kiểm chứng những gì các bạn nói?** Nhận 4 giờ dùng thử, vào giờ cao điểm buổi tối kết nối khu vực Trung Quốc xem một tập phim trên Tencent Video, kết nối khu vực nước ngoài mở YouTube, rồi kiểm tra nơi đăng ký của IP và một trang kiểm tra IPv6. Danh sách kiểm tra nằm trong "Cách chọn VPN có IP Trung Quốc".


## Đọc thêm

- [Mỗi cách kết nối hợp với tình huống nào](https://www.leotun.com/vi/guides/choose-connection?utm_source=github&utm_content=network-04)
- [Cách nhận biết phần mềm VPN rủi ro](https://www.leotun.com/vi/guides/risky-vpn-apps?utm_source=github&utm_content=network-04)
- [VPN về Trung Quốc: miễn phí hay trả phí](https://www.leotun.com/vi/guides/free-vs-paid?utm_source=github&utm_content=network-04)
- [Về chúng tôi: hệ thống được xây thế nào và chúng tôi ghi lại những gì](https://www.leotun.com/vi/about?utm_source=github&utm_content=network-04)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/why-us?utm_source=github&utm_content=network-04

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=network-04) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=network-04) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
