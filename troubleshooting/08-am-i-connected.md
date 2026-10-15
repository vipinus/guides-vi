# 08 · Làm sao biết mình đã thật sự kết nối, và đang ra từ khu vực nào

Ứng dụng báo "Đã kết nối" không có nghĩa là các trang web bạn vào đều thấy địa chỉ của VPN. Cách kiểm tra dễ nhất nằm ngay trên thanh trên cùng của trang này: ô "Mạng hiện tại" cho biết **bạn trong mắt trang này lúc này** — bạn đang đi ra từ quốc gia nào, tỉnh/bang nào và mạng nào. Bài này nói cách đọc ô đó, cách so sánh trước và sau khi kết nối, cách biết từng cách trong sáu cách kết nối đã kết nối chưa, đèn đỏ, vàng, xanh trong danh sách khu vực nghĩa là gì, và vài điều bạn tự kiểm tra được khi "đã kết nối mà vẫn hiện tại chỗ".

## "Mạng hiện tại" trên thanh trên cùng cho biết gì

| Vị trí | Nội dung |
|---|---|
| Đầu | Lá cờ của quốc gia nơi có lối ra; thay bằng biểu tượng Wi‑Fi khi không xác định được quốc gia |
| Giữa | Tên tỉnh/bang, hiển thị theo ngôn ngữ giao diện (Mỹ, Canada, Úc… dùng chữ viết tắt thông dụng như CA, ON, NSW); Hồng Kông, Ma Cao và Singapore hiện thẳng tên vùng |
| Cuối | Tên mạng: ba nhà mạng lớn của Trung Quốc, mạng giáo dục… trên giao diện tiếng Trung hiện tên ngắn như 电信 (China Telecom), 移动 (China Mobile), 联通 (China Unicom) và 教育网 (mạng giáo dục); các mạng khác hiện tên thương hiệu tiếng Anh (ví dụ Comcast, Bell) |

- **Khi không tra được tỉnh/bang, chỉ hiện "lá cờ · tên mạng".** Không lấy tên quốc gia để lấp chỗ; lá cờ đã cho biết quốc gia.
- Trên máy tính, rê chuột lên ô này sẽ hiện ra tên tổ chức đầy đủ, tỉnh/bang, mã quốc gia và **IP lối ra**. IP này chỉ hiện cho riêng bạn, và là thông tin hữu ích nhất khi bạn liên hệ hỗ trợ.
- Chrome / Edge trên Windows không có font cờ, nên lá cờ hiện thành hai chữ cái (ví dụ JP, US). Ý nghĩa như nhau.
- Trên máy tính, ô này chỉ hiện trên thanh trên cùng sau khi đăng nhập; trên điện thoại thì không cần đăng nhập vẫn hiện.

## So sánh trước và sau khi kết nối là thấy ngay

1. **Khi tắt VPN**, mở trang này và nhìn: lẽ ra phải là nhà mạng của mạng cáp ở nhà hoặc dữ liệu di động của bạn, lá cờ là quốc gia bạn đang ở.
2. **Kết nối VPN** rồi quay lại trình duyệt: lá cờ đổi sang khu vực bạn đã chọn, tên mạng thường đổi thành tên trung tâm dữ liệu hay nhà cung cấp đám mây chứ không còn là nhà mạng ở nhà bạn.
3. Nếu hai lần giống nhau, tức là trình duyệt này không đi qua VPN khi vào trang này. Xem phần "Đã kết nối mà vẫn hiện tại chỗ" bên dưới.

**Không cần bấm làm mới trang liên tục.** Ô này tự kiểm tra lại khi bạn quay lại cửa sổ trình duyệt, kiểm tra thêm vài lần trong vài giây sau khi phát hiện mạng thay đổi, và cứ mười tới hai mươi giây lại cập nhật khi trang đang mở. Nếu vừa kết nối xong mà vẫn thấy giá trị cũ, đợi mười tới hai mươi giây hoặc chuyển cửa sổ; vẫn chưa đổi thì làm mới thủ công.

**Khi bạn ở Trung Quốc và chọn một "điểm vào Trung Quốc"**, thanh trên cùng hiện một quốc gia nước ngoài là bình thường: điểm vào Trung Quốc dùng chia luồng, nên trang Trung Quốc đi ra từ trong Trung Quốc còn trang nước ngoài đi ra ở phía nước ngoài. Trang này đặt ở nước ngoài, nên đương nhiên thứ hiện ra là đầu ở nước ngoài.

## Cách biết từng cách kết nối đã kết nối chưa

| Cách kết nối | Xem gì trong ứng dụng | Thanh trên cùng của trang này có đổi không |
|---|---|---|
| Cisco (AnyConnect) | Ứng dụng hiện "Connected" (Đã kết nối) | Có. Cisco kết nối xong thì mọi lưu lượng đều đi qua VPN |
| Hiddify | Ứng dụng hiện đã kết nối | Ở chế độ toàn cục thì đổi; ở chế độ định tuyến tự động thì tùy danh sách |
| OpenVPN | Ứng dụng hiện đã kết nối | Có. Mặc định mọi lưu lượng đi qua VPN |
| Mạng riêng (Tailscale) | Ứng dụng đang trực tuyến, **và** đã chọn một khu vực làm Exit Node (điểm thoát) | Chỉ đổi khi đã chọn lối ra; chọn None thì các thiết bị chỉ truy cập được lẫn nhau, lưu lượng không đi qua VPN |
| Proxy (Web Proxy) | Không có trạng thái "đã kết nối"; xem đang chọn chế độ khu vực nào ở biểu tượng tiện ích | Chỉ trình duyệt có cài tiện ích mới đổi; quy tắc "auto switch" (tự chuyển) có thể khiến trang này đi thẳng |
| Router | Trong trang quản trị, trạng thái tài khoản bình thường và có hiện ngày hết hạn | Xem từ một thiết bị đang bắt Wi‑Fi của router này; ở chế độ chia luồng thì tùy danh sách |

Chia luồng nghĩa là các trang có trong danh sách đi qua VPN, còn lại đi thẳng. Nếu đang bật chia luồng mà thanh trên cùng hiện tại chỗ, chưa chắc là bạn chưa kết nối: **tạm chuyển sang "toàn cục" rồi xem lại**. Nếu nó đổi thì VPN đang chạy, chỉ là trang này không có trong danh sách.

## Đèn đỏ, vàng, xanh trong danh sách khu vực

Trên các trang Cisco, Hiddify, Proxy và OpenVPN, dưới lá cờ của mỗi khu vực có một chiếc đèn nhỏ, và đèn tương tự cũng hiện trước tên lối ra trong ứng dụng Mạng riêng. Nó được tự động xếp hạng theo băng thông thời gian thực trung bình của các máy chủ trong khu vực đó, khoảng mỗi phút cập nhật một lần:

| Đèn | Ý nghĩa |
|---|---|
| Xanh (sáng đứng) | Rảnh |
| Vàng (nhấp nháy) | Đang dùng |
| Đỏ (nhấp nháy) | Bận |
| Không có đèn | Lúc này chưa lấy được dữ liệu; không có nghĩa là máy chủ ngừng hoạt động |

Trên máy tính, rê chuột lên đèn để xem mức tải trung bình của khu vực.

**Thấy đèn đỏ thì làm gì:**

- Đỏ không có nghĩa là hỏng, chỉ là lúc đó đông người. Nếu bạn đã kết nối và tốc độ đủ dùng thì cứ để nguyên.
- Thấy chậm thì chuyển sang khu vực đèn xanh. Với Cisco, bấm lá cờ khác trên trang web để sao chép địa chỉ mới; với Hiddify, nhập cấu hình của khu vực khác; với Mạng riêng, đổi trong Exit Node; với Proxy, bấm khu vực khác ở biểu tượng tiện ích.
- Mỗi khu vực có nhiều máy phía sau, và lúc kết nối sẽ tự chọn máy rảnh nhất. Không cần tự chọn máy.
- Từ 8 đến 11 giờ tối là giờ cao điểm. Trong khung giờ này hãy chọn khu vực đèn xanh hoặc đổi cách kết nối; vẫn chậm thì nguyên nhân thường nằm ở mạng cáp tại chỗ (mạng cáp chung của khu dân cư, hoặc nhà mạng và khu vực không hợp nhau). Chọn khu vực theo nhà mạng thế nào, xem phần Đọc thêm.

## Đã kết nối mà vẫn hiện tại chỗ

Xếp theo mức độ hay gặp:

1. **Quy tắc định tuyến cho trang này đi thẳng.** Định tuyến tự động của Hiddify, "auto switch" của tiện ích Proxy và chế độ chia luồng của router đều có thể giữ trang này ở ngoài VPN. Tạm chuyển sang toàn cục để kiểm chứng; người dùng Proxy cũng có thể thêm trang này vào quy tắc.
2. **Web Proxy chỉ bao trình duyệt đó.** Xem từ trình duyệt khác hay ứng dụng trên điện thoại thì đương nhiên vẫn hiện tại chỗ.
3. **Mạng riêng chưa chọn lối ra.** Trực tuyến ≠ đi qua VPN; khi Exit Node là None thì các thiết bị chỉ truy cập được lẫn nhau.
4. **Bạn đang xem nhầm thiết bị.** Với phương án Router, bạn phải xem từ thiết bị đang bắt Wi‑Fi của router đó, không phải điện thoại bắt Wi‑Fi của modem hay đang dùng dữ liệu di động.
5. **Đang bật cùng lúc một VPN hay công cụ mạng mesh khác.** VPN công ty hay phần mềm tăng tốc của nhà cung cấp khác sẽ giành tuyến đường. Chỉ giữ lại một cái.
6. **Chưa kịp làm mới.** Đợi mười tới hai mươi giây, chuyển cửa sổ, hoặc làm mới thủ công một lần.

## Thanh trên cùng chỉ kiểm tra IP; IPv6 và DNS phải kiểm tra riêng

Thanh trên cùng xem địa chỉ IPv4 của kết nối mà trang này nhận được. Nó hiện đúng thì chỉ có nghĩa là trình duyệt này đã đi qua VPN khi vào trang này:

- **Không nhìn thấy IPv6 và DNS từ đây.** Khi trình duyệt vào trang này bằng IPv6, ô này đơn giản là không hiện; nó sẽ không lấy một mạng sai để giả làm mạng thật. Nếu trang video vẫn báo giới hạn bản quyền, nhiều khả năng IPv6 hoặc DNS đang đi vòng qua VPN; xem [03 · IPv6 và DNS là chỗ bị lọt](03-ipv6-and-dns-leak.md).
- **Ứng dụng lưu lại kết quả kiểm tra khu vực.** Thanh trên cùng lần nào cũng tra mới nên không bị bộ nhớ đệm ảnh hưởng; nhưng ứng dụng video và nhạc thì nhớ khu vực lần trước. Thoát hẳn rồi mở lại; xem [02 · Đã kết nối về Trung Quốc mà vẫn không xem được](02-still-blocked-after-connecting.md).

## Câu hỏi thường gặp

**Ô "Mạng hiện tại" trên thanh trên cùng biến mất?** Trên máy tính, hãy đăng nhập trước. Đăng nhập rồi vẫn không hiện thì nhiều khả năng kết nối này đi qua IPv6 hoặc tạm thời chưa tra được; đợi mười tới hai mươi giây hoặc làm mới. Nó thà không hiện gì còn hơn hiện sai.

**Cùng khu vực mà hai lần kết nối ra IP khác nhau?** Bình thường. Mỗi khu vực có nhiều máy phía sau, mỗi lần kết nối chọn máy rảnh nhất lúc đó. Kết nối đã thiết lập thì không bị chuyển sang chỗ khác giữa chừng.

**Tỉnh hiện ra không như tôi nghĩ?** Thanh trên cùng hiện tỉnh/bang nơi đặt IP lối ra và chỉ chính xác tới mức đó. Lá cờ khớp là lối ra đang ở đúng quốc gia hay khu vực bạn đã chọn.

**Liên hệ hỗ trợ thì nên báo gì?** Rê chuột lên ô đó trên thanh trên cùng và gửi những gì hiện ra (có cả IP lối ra), kèm cách kết nối, khu vực bạn đã chọn và thời điểm xảy ra sự cố.

## Đọc thêm

- [Xử lý khi không kết nối được, chậm và rớt mạng](https://www.leotun.com/vi/guides/connect-issues?utm_source=github&utm_content=troubleshooting-08)
- [Ở trong Trung Quốc khu vực nào nhanh nhất](https://www.leotun.com/vi/guides/pick-region?utm_source=github&utm_content=troubleshooting-08)
- [Mỗi cách kết nối hợp với tình huống nào](https://www.leotun.com/vi/guides/choose-connection?utm_source=github&utm_content=troubleshooting-08)
- [Web Proxy là gì và khi nào nên dùng](https://www.leotun.com/vi/guides/web-proxy?utm_source=github&utm_content=troubleshooting-08)
- [Firmware router làm được những gì](https://www.leotun.com/vi/guides/router-firmware?utm_source=github&utm_content=troubleshooting-08)
- [Ở nước ngoài bị Tencent Video báo giới hạn bản quyền thì làm sao](https://www.leotun.com/vi/guides/overseas-video?utm_source=github&utm_content=troubleshooting-08)

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=troubleshooting-08) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=troubleshooting-08) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
