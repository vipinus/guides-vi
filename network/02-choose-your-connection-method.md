# 02 · Mỗi cách kết nối hợp với tình huống nào

Một tài khoản LeoTun có sáu cách kết nối: Mạng riêng (Tailscale), Cisco (AnyConnect), OpenVPN, Proxy (Web Proxy), Hiddify và Router. Mỗi cách có những tình huống hợp nhất, và bài này trả lời theo tình huống: trước hết theo thiết bị bạn dùng, rồi theo mạng bạn đang dùng, cuối cùng theo việc bạn muốn làm. Mỗi tình huống đều có gợi ý, lý do và phương án thay thế. Chỉ cần nhớ một điều: một tài khoản có sáu cách; luôn có một cách hợp với mạng của bạn.

## Theo thiết bị: bạn lên mạng bằng gì

- Một chiếc điện thoại, đi công tác và du lịch: Cisco hoặc Hiddify. Cisco nhập địa chỉ vào ứng dụng chính thức là kết nối được, ổn định nhất; Hiddify nhập bằng cách quét mã QR, nhanh hơn khi mất gói nhiều. Phương án thay thế: Mạng riêng.
- Máy tính của riêng bạn (Windows, Mac): Hiddify hoặc Mạng riêng. Hiddify nhanh và có sẵn công tắc chia luồng; Mạng riêng đăng nhập một lần là luôn trực tuyến. Phương án thay thế: Cisco.
- Máy tính công ty cấp, không có quyền quản trị: Web Proxy. Bạn chỉ cài một tiện ích trình duyệt, không cần quyền quản trị, cũng không đụng tới cài đặt mạng của công ty.
- iPhone, thiết bị cũ: Cisco. Kết nối bằng VPN có sẵn của hệ thống hoặc ứng dụng chính thức, không phải nhập cấu hình, tương thích tốt nhất.
- NAS (Synology, QNAP), máy chủ Linux: OpenVPN. Nhập một file .ovpn là tự kết nối khi khởi động; phần lớn các thiết bị này có sẵn ứng dụng.
- TV, đầu thu, máy chơi game, điện thoại của người lớn tuổi: Router. Thiết bị nào bắt Wi‑Fi là đi qua đường truyền, trên thiết bị không phải cài gì. Cả ba gói tài khoản đều dùng được.
- Nhiều thiết bị của cả gia đình hay cả văn phòng: Router, cấu hình một lần là có tác dụng cho tất cả; nếu còn muốn vào NAS ở nhà từ bên ngoài thì thêm Mạng riêng.

## Theo môi trường mạng: bạn đang dùng mạng gì

- Mạng ký túc xá hay mạng trường học, mạng công ty hạn chế UDP: Cisco. Nó chạy trên TLS, giống như mở một trang HTTPS, nên ổn định nhất trên mạng bị hạn chế; Hiddify, Mạng riêng và OpenVPN đều chạy trên UDP, sẽ chậm hoặc rớt.
- Mạng cáp hay rớt, sóng Wi‑Fi yếu: Web Proxy. Nó hoạt động theo từng yêu cầu, không giữ kết nối lâu dài, nên về thiết kế thì không có kết nối nào để rớt.
- Mạng cáp ở khu nhà cũ, dữ liệu di động, mất gói nhiều: Hiddify. Giao thức của nó được thiết kế để chịu mất gói và cho tốc độ tốt nhất trên những mạng như vậy.
- Máy tính đang kết nối VPN của công ty: Web Proxy. Hai VPN cho cả máy chạy cùng lúc sẽ giành nhau cài đặt mạng; Web Proxy chỉ lo trình duyệt nên không ảnh hưởng nhau.
- Mạng cáp China Mobile, Great Wall và nhà mạng khác, hoặc đường xuyên biên giới lúc nào cũng chập chờn: cách nào cũng được, chọn điểm vào khu vực Trung Quốc. Đây thường là lựa chọn ổn định nhất trên các mạng này.

## Theo mục đích: bạn muốn làm gì

- Bạn ở nước ngoài và muốn xem video Trung Quốc: bất kỳ cách nào cho cả thiết bị (Cisco, Hiddify, Mạng riêng, OpenVPN, Router) và chọn khu vực Trung Quốc; TV ở nhà thì dùng Router. Đừng dùng Web Proxy để xem video: nó không với tới kênh mạng riêng của thiết bị, nên trang video vẫn có thể coi bạn là ở nước ngoài.
- Game, gọi thoại và gọi video: Hiddify, Mạng riêng hoặc Router, chọn khu vực có độ trễ thấp nhất. Web Proxy chỉ lo trình duyệt; game và ứng dụng gọi điện không đi qua nó.
- Làm việc văn phòng và tra cứu, chỉ dùng trình duyệt: Web Proxy là đỡ phiền nhất; nếu cần vào hệ thống nội bộ của công ty, trước hết hãy xem VPN công ty có chạy song song với của chúng tôi được không, không được thì dùng Web Proxy.
- Máy chủ, script, dòng lệnh: OpenVPN; trên máy Linux để bàn cũng có thể dùng Mạng riêng hoặc Hiddify.
- Vào NAS hay camera ở nhà từ bên ngoài: Mạng riêng. Các thiết bị cùng tài khoản truy cập được lẫn nhau, không phải mở cổng trên router.

## Tra nhanh sáu cách: hợp nhất với / không hợp với

- Mạng riêng (Tailscale) — hợp nhất với: nhiều thiết bị, đăng nhập một lần rồi quên, vào thiết bị ở nhà từ bên ngoài. Không hợp với: mạng hạn chế UDP (chỉ còn dựa vào relay của Tailscale, chậm), chạy cùng một VPN khác.
- Cisco AnyConnect — hợp nhất với: mạng bị hạn chế, máy tính công ty, iPhone, thiết bị cũ; tương thích tốt nhất. Không hợp với: người ở trong Trung Quốc không muốn mọi lưu lượng đi qua đường truyền (phải chạy thêm một script chia luồng riêng).
- OpenVPN — hợp nhất với: NAS, máy chủ Linux, router OpenWrt; nhập một file là tự kết nối khi khởi động. Không hợp với: dùng hằng ngày trên điện thoại và máy tính, vì kém tiện hơn Cisco và Hiddify; mạng hạn chế UDP.
- Web Proxy — hợp nhất với: không có quyền quản trị, đang kết nối VPN công ty, mạng cáp hay rớt. Không hợp với: ứng dụng video, game, gọi điện; nó chỉ lo trình duyệt.
- Hiddify — hợp nhất với: người cần tốc độ, mạng mất gói nhiều; nhập bằng quét mã QR, cùng một ứng dụng trên năm nền tảng, có sẵn chia luồng. Không hợp với: mạng hạn chế UDP.
- Router — hợp nhất với: cả gia đình, văn phòng, thiết bị không cài được ứng dụng; firmware có sẵn chia luồng và tự cập nhật. Không hợp với: người chỉ có một thiết bị và hay ra ngoài (ra ngoài vẫn phải cài ứng dụng).

## Chọn khu vực theo mạng cáp của bạn

Cùng một cách kết nối, tốc độ giữa các khu vực có thể chênh nhau vài lần; nguyên nhân nằm ở tuyến đi ra quốc tế từ nhà mạng của bạn tới khu vực đó, không phải ở máy chủ. China Unicom ở miền Bắc: thử Nhật Bản và Hàn Quốc trước. China Telecom ở miền Nam: thử Đông Nam Á (Singapore, Malaysia, Thái Lan, Philippines, Indonesia) hoặc Úc trước. Mạng cáp khác (China Mobile, Great Wall…): thử điểm vào khu vực Trung Quốc trước.

Đèn đỏ, vàng, xanh trong danh sách khu vực cho biết mức tải hiện tại của từng khu vực; trong mấy điểm vào Nhật Bản, hãy chọn cái đang đèn xanh. Từ 8 đến 11 giờ tối là giờ cao điểm cả nước; trong khung giờ này hãy chọn khu vực đèn xanh hoặc đổi cách kết nối. Vẫn chậm thì nguyên nhân thường nằm ở mạng cáp tại chỗ (mạng cáp chung của khu dân cư, hoặc nhà mạng và khu vực không hợp nhau).

## Chia luồng: trong Trung Quốc kết nối thẳng, nước ngoài đi qua đường truyền

Chỉ người đang ở Trung Quốc đại lục mới cần chia luồng; người ở nước ngoài dùng chế độ toàn cục, bật chia luồng lên còn khiến một số trang phải đi đường vòng. Với Hiddify bạn chuyển sang chia luồng tự động (Auto split routing) trong ứng dụng, với Web Proxy bạn chuyển sang "Split routing" (chia luồng) trong tiện ích, router chia luồng cho mọi thiết bị trong mạng và firmware bật sẵn chế độ này; với Cisco và OpenVPN, kết nối xong thì mọi lưu lượng đều đi qua đường truyền, và có script chia luồng ở mục "Cisco"; Mạng riêng đưa cả thiết bị đi qua đường truyền.

Nếu có trang không mở được khi chia luồng, trước hết tạm chuyển sang "Global" (toàn cục) để kiểm tra: mở được ở chế độ toàn cục thì trang đó không có trong danh sách; toàn cục cũng không mở được thì vấn đề nằm ở chính trang đó.

## Không được thì đổi thế nào

1. Đổi khu vực trước. Khu vực khác kết nối được thì máy chủ kia chỉ tạm thời không vào được.
2. Rồi đổi mạng. Mạng cáp không được thì chuyển sang dữ liệu di động, và ngược lại; nhiễu trên các nhà mạng khác nhau không xảy ra cùng lúc.
3. Rồi đổi cách kết nối. Các cách chạy trên UDP (Hiddify, Mạng riêng, OpenVPN) không được thì chuyển sang Cisco, chạy trên TLS; các cách cho cả thiết bị hay rớt thì chuyển sang Web Proxy. Việc chặn các giao thức khác nhau độc lập với nhau.
4. Vẫn không được thì xem hướng dẫn khắc phục sự cố, hoặc hỏi trong nhóm hỗ trợ, kèm cách kết nối, khu vực, nguyên văn thông báo lỗi và thời điểm.

## Câu hỏi thường gặp

**Sáu cách thì cách nào nhanh nhất?** Trên mạng mất gói nhiều, Hiddify nhanh nhất; trên mạng sạch thì chênh lệch không đáng kể, nút thắt là khu vực và khung giờ chứ không phải cách kết nối.

**Chơi game và gọi thoại thì dùng cách nào?** Hiddify, Mạng riêng hoặc Router, chọn khu vực có độ trễ thấp nhất. Web Proxy chỉ lo trình duyệt; game và ứng dụng gọi điện không đi qua nó.

**Sáu cách dùng cùng lúc được không?** Trên các thiết bị khác nhau thì được; mọi cách trong cùng một tài khoản dùng chung hạn mức trực tuyến cùng lúc (Cá nhân 2 thiết bị, Gia đình 4 thiết bị, Doanh nghiệp 8 thiết bị). Đừng chạy cùng lúc hai cách cho cả thiết bị trên cùng một máy (ví dụ Mạng riêng và Cisco), vì chúng sẽ giành nhau cài đặt mạng.

**Có phải chọn giữa router và ứng dụng không?** Không. Ở nhà dùng router, ra ngoài bật ứng dụng trên điện thoại; mỗi bên tính là một thiết bị.

**Linux thì dùng cách nào?** Mạng riêng, OpenVPN và Hiddify đều có ứng dụng Linux; Cisco trên Linux dùng OpenConnect mã nguồn mở; OpenVPN trên Linux phải nhập tài khoản và mật khẩu ở lần kết nối đầu tiên. Với máy chủ và NAS, OpenVPN là đỡ phiền nhất.

## Đọc thêm

- [Chúng tôi khác các VPN khác ở chỗ nào](https://www.leotun.com/vi/guides/why-us?utm_source=github&utm_content=network-02)
- [Mạng riêng (Tailscale) là gì](https://www.leotun.com/vi/guides/tailscale-mesh?utm_source=github&utm_content=network-02)
- [Dùng OpenVPN thế nào và khi nào nên chọn](https://www.leotun.com/vi/guides/openvpn-setup?utm_source=github&utm_content=network-02)
- [Web Proxy là gì và khi nào nên dùng](https://www.leotun.com/vi/guides/web-proxy?utm_source=github&utm_content=network-02)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/choose-connection?utm_source=github&utm_content=network-02

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=network-02) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=network-02) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
