# 10 · Dropbox và các phần mềm khác đòi proxy HTTP / SOCKS thì làm sao

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/app-proxy?utm_source=github&utm_content=client-10

**Trước hết, thực tế là: proxy phải được mã hóa.** Proxy không mã hóa (HTTP thường, SOCKS4, SOCKS5) bị nhận diện và gây nhiễu trên mạng ở Trung Quốc; dùng một thời gian là kết nối chậm đi hoặc rớt, mà tài khoản, mật khẩu còn đi dưới dạng văn bản thô. Chỉ kết nối mã hóa mới dùng được lâu dài, nên Web Proxy của trang này mã hóa toàn bộ; **với phần mềm chỉ nhận HTTP / SOCKS5, hãy để Hiddify lo cho cả máy** (xem bên dưới).

Các phần mềm chạy riêng như Dropbox, Telegram Desktop, Steam, ứng dụng ổ đám mây và công cụ lập trình không đọc cài đặt của trình duyệt, và phần cài đặt proxy của chính chúng chỉ nhận HTTP / SOCKS5 không mã hóa. Hai bên không khớp nhau, nên điền proxy vào cũng không kết nối được. Cách giải quyết là **không điền proxy**: dùng Hiddify để cả máy tính đi qua đường truyền, và đặt proxy trong phần mềm thành "No proxy" (không dùng proxy).

## Vì sao điền proxy rồi vẫn không kết nối được

| Nguyên nhân | Giải thích |
|---|---|
| Không khớp loại | Phần mềm chỉ có HTTP, SOCKS4 và SOCKS5, không cái nào mã hóa; proxy của trang này bắt buộc mã hóa nên không điền vào được |
| Dùng proxy không mã hóa tìm trên mạng | Kết nối được một thời gian rồi bị gây nhiễu, lúc được lúc không |
| Chỉ lo được một phần lưu lượng | Ở nhiều phần mềm chỉ phần đăng nhập và đồng bộ đi qua proxy, còn cập nhật, cuộc gọi và đồng bộ mạng LAN vẫn kết nối trực tiếp; proxy HTTP hoàn toàn không chuyển tiếp lưu lượng UDP của game và cuộc gọi |
| Mỗi phần mềm phải chỉnh riêng | Đổi khu vực hay mật khẩu là phải sửa từng cái một, sót cái nào là cái đó hỏng |

## Cách khuyên dùng: để Hiddify lo cho cả máy

1. Cài Hiddify theo [09 · Cài Hiddify trên mọi nền tảng](09-hiddify-install-all-platforms.md), rồi nhập cấu hình theo [bài 02](02-singbox-subscription-links.md).
2. Kết nối ở chế độ "VPN" (mặc định). Trên Windows, lần kết nối đầu cần quyền quản trị.
3. Đặt proxy trong phần mềm về "No proxy": trong Dropbox, chọn "No proxy" hoặc "Auto-detect" ở "Preferences → Network → Proxies"; trong Telegram Desktop, chọn "Disable proxy" ở "Settings → Advanced → Connection type". Phần mềm nào khác có tùy chọn proxy thì tắt đi.
4. Kiểm tra: biểu tượng Dropbox ở khay hệ thống hiện "Up to date" và bắt đầu đồng bộ; mở một trang hiển thị IP trong trình duyệt, lối ra nằm ở khu vực bạn đã chọn.

Khi bật "định tuyến tự động", các dịch vụ nước ngoài như Dropbox đi qua đường truyền, còn WeChat, ngân hàng trực tuyến và trang web Trung Quốc vẫn kết nối trực tiếp như thường.

## Các phần mềm thường gặp

| Phần mềm | Cách đặt |
|---|---|
| Dropbox | Proxy chọn "No proxy" hoặc "Auto-detect"; để ở "Manual" với địa chỉ nào khác thì tắt Hiddify là nó mất mạng luôn |
| Telegram Desktop | Connection type chọn "Disable proxy"; MTProto / SOCKS5 có sẵn chồng thêm lên đường hầm chỉ làm chậm hơn |
| OneDrive, Google Drive, iCloud cho máy tính | Theo mạng của hệ thống; không phải chỉnh gì |
| Steam, Epic, Battle.net | Không cần proxy; tải chậm thì đổi sang khu vực gần hơn |
| Zoom, Teams, Slack, Discord | Thoại và video là UDP, chỉ cách lo cho cả máy mới chuyển được |
| VS Code, JetBrains, Cursor | Theo mạng của hệ thống; xóa proxy nào đã đặt riêng trong công cụ |

## Khi không cài được ứng dụng (máy tính công ty)

- Dùng bản web của Dropbox và ổ đám mây: mở dropbox.com trong trình duyệt có [Web Proxy](03-web-proxy-extension.md); tải lên, tải xuống được, nhưng không có đồng bộ tự động.
- Công cụ dòng lệnh (git, pip, npm, curl) nhận được proxy mã hóa: điền địa chỉ Web Proxy vào `https_proxy`; xem [Truy cập dịch vụ nước ngoài từ Trung Quốc 05 · Linux và dòng lệnh](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/05-linux-server.md) (bằng tiếng Trung).
- Các phần mềm máy tính khác chỉ nhận HTTP / SOCKS5 thì tốt nhất dùng trên máy tính hoặc điện thoại của riêng bạn; đừng vì chuyện này mà cài VPN cho cả máy trên máy tính công ty, vì nó sẽ kích hoạt cảnh báo bảo mật của công ty.

## Câu hỏi thường gặp

**Có thể cho tôi một địa chỉ proxy SOCKS5 hoặc HTTP không?** Proxy của trang này mã hóa toàn bộ; proxy không mã hóa chẳng bao lâu sẽ bắt đầu lúc được lúc không. Để Hiddify lo cho cả máy thì ổn định hơn và bao luôn mọi phần mềm một lần.

**Bật Hiddify rồi thì còn phải điền proxy trong phần mềm không?** Không. Điền vào là đi vòng hai lần: nhẹ thì chậm hơn, nặng thì không kết nối được.

**Còn Dropbox trên điện thoại thì sao?** Ứng dụng điện thoại không có cài đặt proxy. Cài Hiddify hoặc dùng Cisco (AnyConnect); kết nối xong thì mọi ứng dụng đều đi qua đường truyền.

**Không dùng Hiddify có được không?** Được. Cisco, Mạng riêng và OpenVPN cũng lo cho cả máy, và phần mềm cũng đặt là "No proxy". Ưu điểm của Hiddify là có sẵn chia luồng và tốc độ tốt hơn trên mạng mất gói nhiều.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=client-10) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=client-10) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
