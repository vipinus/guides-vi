# 04 · Hiddify nhập xong mà không kết nối được

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/singbox-subscription?utm_source=github&utm_content=troubleshooting-04

Đối chiếu lỗi của bạn với bảng dưới. Còn cách nhập ngay từ đầu thì xem [Cách nhập link đăng ký (Hiddify, Clash, Shadowrocket)](../client/02-singbox-subscription-links.md).

| Triệu chứng | Nguyên nhân | Cách xử lý |
|---|---|---|
| "Unable to fetch subscription" (không lấy được đăng ký), lỗi 401 | Tài khoản đã hết hạn, hoặc mật khẩu đã bị đổi (đổi mật khẩu làm cấu hình cũ mất hiệu lực ngay; đây là chủ ý) | Đăng nhập website kiểm tra thời hạn; sau khi gia hạn hoặc đổi mật khẩu thì quét lại mã QR |
| Nhập thành công nhưng kết nối hết thời gian chờ | Địa chỉ của khu vực đó vừa được đổi, hoặc điểm vào đó đang bị nhà mạng gây nhiễu | Bấm "Update subscription" (cập nhật đăng ký) trong ứng dụng để kéo cấu hình mới nhất; đổi sang khu vực khác — mỗi khu vực là một cấu hình riêng, không ảnh hưởng nhau |
| Đã kết nối nhưng không vào mạng được | Quy tắc định tuyến của chính ứng dụng đang đẩy lưu lượng sang "direct" (đi thẳng) | Đổi lối ra mặc định sang node đó, hoặc xóa các quy tắc bạn tự thêm |
| Quét báo "Invalid QR code" (mã QR không hợp lệ) | Lúc cửa sổ mới mở, mã QR là loại cho Hiddify / sing-box, ứng dụng khác quét thẳng sẽ báo lỗi này; hoặc bạn quét từ ảnh chụp màn hình của người khác | Bấm nút của ứng dụng bạn dùng trước để mã QR chuyển sang đúng loại, rồi mới quét hoặc dán: ứng dụng họ Clash bấm "Đăng ký Clash"; Shadowrocket / NekoBox / v2rayN v.v. bấm "Liên kết chia sẻ". Mã QR chứa thông tin đăng nhập của riêng bạn, mã của người khác sẽ không dùng được |
| Tốc độ chậm | Khu vực đang chọn tải cao, hoặc mạng tại chỗ và khu vực không hợp nhau | Xem đèn đỏ, vàng, xanh trong danh sách khu vực trên website và đổi sang khu vực đèn xanh; vẫn chậm thì đổi khu vực theo nhà mạng |
| Ứng dụng họ Clash nhập liên kết chia sẻ thất bại | Clash Meta, Clash Verge, FlClash, Stash và các ứng dụng tương tự không nhập được một dòng hysteria2:// đơn lẻ làm hồ sơ | Bấm nút "Đăng ký Clash" rồi dán URL vào danh sách đăng ký của ứng dụng; Clash bản gốc và Clash for Windows có lõi không hỗ trợ hysteria2, hãy dùng ứng dụng lõi mihomo |
| Liên kết chia sẻ nhập không được hoặc không kết nối được | Liên kết chia sẻ dùng định dạng mở rộng mà vài ứng dụng không đọc được | Chuyển sang Hiddify |

## Gia hạn, đổi gói hay đổi mật khẩu có phải nhập lại không

- **Gia hạn hoặc đổi gói (Cá nhân / Gia đình / Doanh nghiệp)**: Không. Cấu hình hiện có vẫn dùng tiếp được.
- **Đổi mật khẩu**: Cấu hình cũ mất hiệu lực ngay; hãy quét lại mã QR. Nếu mất điện thoại hoặc lộ link, hãy dùng cách này để thu hồi quyền truy cập.
- **Tài khoản hết hạn**: Cấu hình trả về lỗi 401. Gia hạn xong không cần cấu hình mới, chỉ việc kết nối lại.
- **Nhập trước tháng 9/2026**: Thiếu quy tắc chặn IPv6, nên xem video Trung Quốc từ nước ngoài sẽ gặp thông báo giới hạn bản quyền. Xóa đi rồi nhập lại; xem [bài 03](03-ipv6-and-dns-leak.md).

## Khi nào nên liên hệ hỗ trợ

Báo cho bộ phận hỗ trợ ba thứ: tên và phiên bản ứng dụng, khu vực, và nguyên văn thông báo lỗi hoặc ảnh chụp màn hình.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=troubleshooting-04) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=troubleshooting-04) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, hiệu lực lâu dài
