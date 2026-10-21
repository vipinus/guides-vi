# 05 · Cách nhận biết phần mềm VPN rủi ro

Toàn bộ lưu lượng của bạn đi qua tay ứng dụng VPN, và nó muốn xem gì cũng được. Trên thị trường có hai loại cần đặc biệt cảnh giác: một là thứ mà dân trong giới gọi là "VPN đỏ" — có nền tảng từ cơ quan quản lý, đòi danh tính thật của bạn nhân danh "tuân thủ" rồi giao nộp nhật ký; hai là các phần mềm tăng tốc miễn phí không rõ nguồn gốc, kiếm tiền từ dữ liệu của bạn, từ thiết bị của bạn, hoặc từ thứ gì đó nó cài cắm vào. Điểm chung của hai loại là "dùng vẫn bình thường"; vấn đề nằm ở chỗ bạn không nhìn thấy. Dưới đây là mười dấu hiệu bạn tự kiểm chứng được, cách xử lý nếu đã lỡ cài, và một bài tự kiểm tra ba phút.

## Vì sao phần mềm VPN rủi ro hơn ứng dụng thông thường

VPN hoạt động ở cấp hệ thống: nó nhận lưu lượng của mọi chương trình trên thiết bị, kể cả những chương trình chạy ngầm mà bạn không biết. Ứng dụng thông thường làm lộ dữ liệu do chính nó thu thập; VPN làm lộ mọi thứ bạn làm trên thiết bị đó. Vì vậy tiêu chuẩn chọn phần mềm VPN phải khắt khe hơn nhiều so với chọn một ứng dụng thông thường.

"Tôi dùng rồi có sao đâu" không phải bằng chứng an toàn. Ghi nhật ký, báo cáo và chèn mã đều diễn ra ở phía máy chủ hoặc chạy ngầm, người dùng không cảm nhận được; khi có chuyện thì thường đã cách đó mấy tháng, và không lần ra được là do phần mềm nào.

## Mười dấu hiệu

- Nguồn gốc không rõ: bộ cài đến từ nhóm chat, ổ đĩa đám mây hay mã QR, không có trang web chính thức hay trang trên kho ứng dụng. Ứng dụng đàng hoàng thì hoặc từ kho ứng dụng, hoặc từ trang chính thức của nhà phát triển, hoặc từ trang phát hành kiểm tra được chữ ký.
- Đòi cài chứng chỉ gốc: trong lúc cài nó bảo bạn "tin cậy chứng chỉ" hay "cài hồ sơ cấu hình" và yêu cầu tin cậy một CA. Chứng chỉ gốc đã cài thì nó mở được toàn bộ lưu lượng HTTPS của bạn, kể cả ngân hàng trực tuyến và email. VPN bình thường không cần bước này.
- Đòi quá nhiều quyền: một VPN mà xin danh bạ, SMS, nhật ký cuộc gọi, vị trí chính xác và quyền truy cập thư viện ảnh. VPN chỉ cần quyền dựng đường hầm; những quyền còn lại nó không cần đến.
- Bắt đăng ký thực danh: đăng ký phải có căn cước, quét khuôn mặt hoặc gắn số di động Trung Quốc đại lục. Đây là cách một VPN gọi là "tuân thủ" gắn danh tính của bạn với nhật ký lưu lượng; dịch vụ đàng hoàng chỉ cần một địa chỉ email.
- Giao thức độc quyền + ứng dụng mã nguồn đóng: bạn chỉ dùng được ứng dụng của chính nó, không hỗ trợ giao thức chuẩn nào (AnyConnect, OpenVPN, WireGuard, Hiddify), nên không thể dùng ứng dụng mã nguồn mở của bên thứ ba để kiểm chứng nó thực sự truyền gì.
- Miễn phí mà không thấy nguồn thu: không có gói trả phí, không quảng cáo, không khách doanh nghiệp, vậy mà vẫn chạy năm này qua năm khác. Băng thông lối ra ở đại lục tính tiền theo mức dùng, và dịch vụ không thu tiền thì kiểu gì cũng thu lại ở chỗ khác.
- Không công ty, không hỗ trợ, không lịch sử: không tìm ra pháp nhân vận hành, không có ai để liên hệ, tên miền đăng ký chưa tới một năm, liên tục đổi tên đổi vỏ.
- Lưu lượng chạy ngầm bất thường: thiết bị vẫn liên tục tải lên dù bạn không dùng, pin và dữ liệu hao nhanh. Có thể nó đang biến thiết bị của bạn thành lối ra cho người khác, hoặc đang đồng bộ dữ liệu của bạn đi.
- Quảng cáo nhấn mạnh "chính thức", "có đăng ký", "hợp pháp, tuân thủ" và ngầm ám chỉ mọi thứ khác là phạm pháp: đây là lời chào hàng điển hình nhất của "VPN đỏ", và cái "tuân thủ" của nó chính là ghi nhật ký và báo cáo.
- Đánh giá trên kho ứng dụng một chiều, các bình luận na ná nhau, số lượt tải chênh lệch quá xa so với số đánh giá: đó là đánh giá ảo.

## Kiểm chứng thế nào

1. Xem giao thức: trang chính thức có nói rõ dùng giao thức gì và có dùng được ứng dụng bên thứ ba không. Với dịch vụ kết nối được bằng các ứng dụng mã nguồn mở hoặc chuẩn như OpenVPN, AnyConnect, Hiddify và Tailscale, bạn có thể tự bắt gói tin và xem nó truyền gì.
2. Xem quyền: cài xong, vào cài đặt hệ thống xem nó đã xin những quyền gì, tắt hết mọi quyền trừ VPN rồi xem nó còn chạy không. Không chạy thì gỡ đi.
3. Xem chứng chỉ: iOS Cài đặt → Cài đặt chung → VPN & Quản lý thiết bị; Android Cài đặt → Bảo mật → Mã hóa và thông tin xác thực → Thông tin xác thực đáng tin cậy → Người dùng; "Trusted Root Certification Authorities" (tổ chức cấp chứng chỉ gốc đáng tin cậy) trong trình quản lý chứng chỉ của Windows. Nếu có chứng chỉ do nó cài, hãy xóa đi và gỡ ứng dụng.
4. Kiểm tra rò rỉ: kết nối xong, mở một trang kiểm tra rò rỉ DNS và một trang kiểm tra IPv6, xem cả phân giải tên miền lẫn địa chỉ có đều đi qua máy chủ của nó không; rồi mở một trang HTTPS và xem bên cấp chứng chỉ có phải CA gốc không.
5. Kiểm tra pháp nhân: trang chính thức có giới thiệu công ty hay đội ngũ không, đã hoạt động bao nhiêu năm, hỗ trợ ở đâu; quy định hoàn tiền có ghi rõ không; chính sách quyền riêng tư có nói rõ ghi lại những gì không.

## Nếu đã lỡ cài thì làm gì

1. Gỡ phần mềm, rồi kiểm tra các vị trí nói ở trên và xóa chứng chỉ, hồ sơ cấu hình mà nó đã cài.
2. Đổi mật khẩu: ngân hàng trực tuyến, email, các tài khoản hay dùng, nhất là những tài khoản bạn đã đăng nhập trong lúc dùng nó.
3. Với các tài khoản đã bật xác minh hai bước, kiểm tra lịch sử đăng nhập và gỡ mọi thiết bị lạ.
4. Nếu đã cài trên router, khôi phục cài đặt gốc rồi cài lại firmware chính thức hoặc firmware đáng tin cậy.

## Chúng tôi để bạn kiểm chứng thế nào

Mọi ứng dụng của LeoTun đều đến từ các hãng chính thức và tổ chức mã nguồn mở nổi tiếng: Cisco, OpenVPN, Hiddify và Tailscale, được sao lại nguyên vẹn không sửa đổi, và bạn có thể thay bản tải từ trang này bằng ứng dụng chính thức hay mã nguồn mở bất cứ lúc nào. Giao thức đều là giao thức chuẩn, có thể kiểm chứng bằng bắt gói tin.

Đăng ký chỉ cần một địa chỉ email, không cần số điện thoại, không cần căn cước. Chúng tôi chỉ giữ thông tin cần cho việc tính phí; không ghi lại bạn truy cập gì, không chèn quảng cáo, không bán dữ liệu.

Chúng tôi không cài chứng chỉ, không xin danh bạ hay vị trí. Nếu một ngày nào đó ứng dụng của chúng tôi đòi bạn cài chứng chỉ gốc, chắc chắn đó không phải chúng tôi.

## Câu hỏi thường gặp

**Thứ gì miễn phí cũng không dùng được sao?** Các ứng dụng của cộng đồng mã nguồn mở (OpenVPN, Hiddify, Tailscale) vốn miễn phí và đáng tin; rủi ro nằm ở "dịch vụ miễn phí", không phải "phần mềm miễn phí". Với dịch vụ miễn phí, hãy xem nó sống bằng gì.

**Có mặt trên kho ứng dụng thì an toàn chứ?** Có mặt trên kho chỉ chứng tỏ nó qua được khâu duyệt tự động của kho; không có nghĩa là phía máy chủ không ghi nhật ký. Hãy xem các mục quyền, thực danh, giao thức và pháp nhân trong mười dấu hiệu ở trên; bản thân kho không kiểm tra những điều này giúp bạn.

**Cái gọi là "VPN đỏ" là gì?** Là tên dân trong giới gọi những VPN có nền tảng từ cơ quan quản lý, bắt đăng ký thực danh nhân danh tuân thủ, và lưu nhật ký. Chúng thường tự quảng cáo là "chính thức", "hợp pháp" và dùng vẫn bình thường; vấn đề là danh tính và toàn bộ nhật ký lưu lượng của bạn bị gắn chặt với nhau.

**Làm sao biết một VPN có ghi lại nội dung của tôi không?** Từ phía người dùng thì không biết được; chỉ có thể xem nó cho bạn bao nhiêu cách để kiểm chứng: giao thức có chuẩn không, ứng dụng có mã nguồn mở không, chính sách quyền riêng tư có cụ thể không, pháp nhân vận hành có tra được không. Không có điều nào trong bốn điều đó thì cứ coi như nó có ghi.

**Firmware router có rủi ro kiểu này không?** Có; "firmware vượt tường lửa" không rõ nguồn gốc có thể chiếm quyền toàn bộ mạng gia đình. Chỉ cài OpenWrt chính thức hoặc firmware kiểm tra được mã nguồn; firmware của trang này được biên dịch từ OpenWrt, chỉ thêm các thành phần để kết nối đường truyền và quy tắc chia luồng.

## Đọc thêm

- [Chúng tôi khác các VPN khác ở chỗ nào](https://www.leotun.com/vi/guides/why-us?utm_source=github&utm_content=network-05)
- [VPN về Trung Quốc: miễn phí hay trả phí](https://www.leotun.com/vi/guides/free-vs-paid?utm_source=github&utm_content=network-05)
- [Ở nước ngoài bị Tencent Video báo giới hạn bản quyền thì làm sao](https://www.leotun.com/vi/guides/overseas-video?utm_source=github&utm_content=network-05)
- [Về chúng tôi: được xây dựng thế nào và ghi lại những gì](https://www.leotun.com/vi/about?utm_source=github&utm_content=network-05)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/risky-vpn-apps?utm_source=github&utm_content=network-05

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=network-05) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=network-05) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
