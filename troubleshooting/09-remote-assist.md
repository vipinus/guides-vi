# 09 · Nhờ bộ phận hỗ trợ xem máy tính và router từ xa

Có những vấn đề gửi qua gửi lại cả chục lượt ảnh chụp màn hình trong nhóm vẫn không nói rõ được, nhưng bộ phận hỗ trợ nhìn thẳng vào màn hình thì hai phút là xác định xong. Bài này nói khi nào đáng nhờ hỗ trợ từ xa, trên máy tính dùng phần mềm gì, cách nhập cấu hình máy chủ của trang này, cách đưa thông tin kết nối cho bộ phận hỗ trợ một cách an toàn, trong phiên làm việc bạn nắm quyền gì, xong việc thì thu hồi quyền truy cập ra sao, và với router chạy firmware của trang này thì bạn cần làm gì.

## Khi nào đáng nhờ hỗ trợ từ xa

- Bạn đã làm hết một lượt [01 · Danh sách kiểm tra khi không kết nối được, chậm và rớt mạng](01-cannot-connect-slow-drops.md), đã hỏi kèm cách kết nối, khu vực, nguyên văn thông báo lỗi hoặc ảnh chụp màn hình và thời điểm xảy ra sự cố, mà vẫn chưa giải quyết được.
- Bạn không tự mô tả được các bước: cài đặt nằm quá sâu, bạn không đọc được ngôn ngữ của hệ thống, hoặc thông báo lỗi lóe lên quá nhanh không chụp kịp.
- Bạn đang giúp người nhà với máy tính của họ, bạn không ở bên cạnh, và nói qua điện thoại không ăn thua.

Trường hợp sau **đừng dùng hỗ trợ từ xa**; hãy trao đổi bằng chữ trong nhóm:

- Máy tính do công ty quản lý tập trung. Chính sách nhóm (group policy) thường cấm chạy loại chương trình này, và có thể vi phạm quy định của công ty.

## Dùng phần mềm gì: RustDesk

Website khuyên dùng [RustDesk](https://rustdesk.com): nó là mã nguồn mở (AGPL-3.0), nên ai cũng kiểm tra được mã; và khi nào bắt đầu, khi nào kết thúc phiên đều do chính bạn bấm quyết định. Nó hỗ trợ Windows, macOS, Linux, Android và iOS (iPhone / iPad chỉ điều khiển máy khác được, không bị điều khiển).

Tải ở [trang liên hệ](https://www.leotun.com/vi/contact#downloads), mục "Trung tâm tải xuống" → "Hỗ trợ từ xa", hoặc từ trang chính thức rustdesk.com. Đừng dùng các trang tải bên thứ ba trong kết quả tìm kiếm. Cả hai bên của phiên đều cần cài.

## Cài xong thì cấp quyền gì

| Hệ thống | Làm gì |
|---|---|
| macOS | Trong "Cài đặt hệ thống → Quyền riêng tư & Bảo mật", bật RustDesk ở cả "Ghi màn hình" lẫn "Trợ năng", rồi thoát hẳn và mở lại. Chỉ cấp một quyền thì sẽ gặp cảnh "thấy mà không điều khiển được" hoặc màn hình đen hoàn toàn. Nếu báo "bị hỏng", xem [06](06-antivirus-false-positive.md) |
| Android | Khi được hỗ trợ, chạm "Start service" (bắt đầu dịch vụ) trong RustDesk và cho phép ghi màn hình; để bộ phận hỗ trợ chạm được trên màn hình của bạn, bật thêm RustDesk trong mục "Hỗ trợ tiếp cận" của hệ thống |
| Windows / Linux | Thường cài xong là dùng được |

## Kết nối tới máy chủ riêng của chúng tôi

Hỗ trợ từ xa chạy qua máy chủ RustDesk do trang này tự vận hành, kết nối ổn định cả từ trong Trung Quốc. **Cả hai bên của phiên đều cần nhập một lần**; hai đầu chỉ tìm thấy nhau khi dùng cùng một máy chủ:

1. Đăng nhập website trước, rồi trên [trang liên hệ](https://www.leotun.com/vi/contact#downloads) vào "Trung tâm tải xuống" → "Hỗ trợ từ xa" → "Kết nối máy chủ của chúng tôi" và bấm "Sao chép".
2. Trên máy tính, mở RustDesk "Cài đặt → Mạng" (Settings → Network), bấm "Mở khóa cài đặt mạng" (Unlock network settings) trước, rồi bấm "Máy chủ ID/Relay" (ID/Relay server); trên điện thoại là "Cài đặt → Máy chủ ID/Relay".
3. Trong cửa sổ hiện ra, bấm biểu tượng bảng nhớ tạm ở góc trên bên phải (trên điện thoại chạm "Nhập" / Import). Cấu hình được điền tự động; bấm "OK".

**Đừng dán cấu hình vào các ô nhập**; làm vậy sẽ gặp lỗi "failed to lookup address". Cấu hình này chỉ dùng cho tài khoản của trang này. Đừng chuyển tiếp cho người khác.

## Đưa ID và mật khẩu dùng một lần cho bộ phận hỗ trợ

Mở RustDesk, màn hình chính hiện ID của máy này và một mật khẩu dùng một lần. Trước khi đưa, hãy chắc chắn ba điều:

1. **Bạn là người hỏi trước.** Bạn đã mô tả vấn đề trong một nhóm chính thức có trên [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=troubleshooting-09), và bộ phận hỗ trợ quyết định cần hỗ trợ từ xa, rồi mới sang bước tiếp theo. Nhân viên hỗ trợ của chúng tôi không tự tìm đến bạn, không bảo bạn cài phần mềm điều khiển từ xa, cũng không hỏi mã kết nối; ai đến hỏi thì cũng hãy xác minh trong nhóm chính thức trước.
2. **Chỉ gửi qua kênh hỗ trợ chính thức**: các liên hệ hỗ trợ trực tiếp ghi trên trang liên hệ. Mọi cuộc nhắn riêng ngoài nhóm tự xưng là "hỗ trợ LeoTun" đều không phải chúng tôi.
3. **Đừng đăng trong nhóm.** Nhóm là nơi nhiều người nhìn thấy; ID cộng mật khẩu chẳng khác gì dán chìa khóa máy tính lên cửa.

## Trong phiên làm việc

- Suốt phiên, bạn thấy được mọi thao tác trên màn hình, và có thể ngắt kết nối trong cửa sổ RustDesk bất cứ lúc nào.
- Nếu ai đó bảo bạn thu nhỏ cửa sổ, rời khỏi máy, hoặc mở ngân hàng trực tuyến hay ứng dụng thanh toán, **hãy ngắt kết nối ngay**.
- Khi cần nhập mật khẩu tài khoản, hãy tự gõ; đừng đọc nó cho bộ phận hỗ trợ.

## Xong việc thì thu hồi quyền truy cập

1. Bấm ngắt kết nối trong cửa sổ RustDesk và xác nhận bên kia đã ngoại tuyến.
2. Làm mới mật khẩu dùng một lần để mật khẩu vừa gửi đi mất hiệu lực.
3. Thoát RustDesk. Nếu không cần nữa thì cứ gỡ cài đặt, lần sau tải lại.

## Router: bạn cần làm gì

Với router chạy firmware của trang này, bạn không phải cài phần mềm điều khiển từ xa nào trên router hay máy tính, cũng không phải gửi mật khẩu quản trị router cho bộ phận hỗ trợ. Bạn chỉ cần:

- Để router cắm điện và cắm dây mạng, tài khoản vẫn đăng nhập trên router.
- Báo cho bộ phận hỗ trợ tài khoản, mẫu router và hiện tượng trong nhóm chính thức; phần còn lại do bộ phận hỗ trợ lo.
- Đừng rút điện khởi động lại liên tục trong lúc đang được xử lý, trừ khi bộ phận hỗ trợ yêu cầu.

## Câu hỏi thường gặp

**Bộ phận hỗ trợ có tự nhắn riêng và bảo tôi cài phần mềm điều khiển từ xa không?** Không. Hễ có ai tự tìm đến bạn, luôn xác minh danh tính của họ trong nhóm chính thức trước.

**Nhập cấu hình thì gặp "failed to lookup address"?** Nhiều khả năng cấu hình đã bị dán vào các ô nhập. Xóa các ô đó, quay lại cửa sổ "Máy chủ ID/Relay" và nhập bằng cách bấm biểu tượng bảng nhớ tạm góc trên bên phải.

**Trên macOS kết nối được nhưng màn hình đen, hoặc thấy mà không điều khiển được?** Quyền chưa đủ. Bật cả "Ghi màn hình" lẫn "Trợ năng", rồi thoát hẳn và mở lại.

**Kết thúc phiên rồi còn phải làm gì nữa?** Ngắt kết nối, làm mới mật khẩu dùng một lần, thoát chương trình. Làm xong ba bước này thì bên kia không bao giờ kết nối lại được nữa.

## Đọc thêm

- [Cách dùng hỗ trợ từ xa bằng RustDesk (hướng dẫn trên website)](https://www.leotun.com/vi/guides/rustdesk-certificate?utm_source=github&utm_content=troubleshooting-09)
- [Mac báo ứng dụng "bị hỏng" thì làm sao](https://www.leotun.com/vi/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-09)
- [Trang liên hệ: nhóm hỗ trợ, hỗ trợ trực tiếp và email](https://www.leotun.com/vi/contact?utm_source=github&utm_content=troubleshooting-09)
- [05 · Cách liên hệ với chúng tôi và không bao giờ mất liên lạc](05-how-to-reach-us.md)
- [01 · Danh sách kiểm tra khi không kết nối được, chậm và rớt mạng](01-cannot-connect-slow-drops.md)

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=troubleshooting-09) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=troubleshooting-09) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
