# 06 · Mac báo ứng dụng "bị hỏng" thì làm sao

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-06

Nói kết luận trước: file không hỏng, và không ai sửa đổi nó cả. Khi bấm đúp Hiddify trên Mac mà hiện "bị hỏng và không thể mở" hay "không thể xác minh nhà phát triển", đó là Gatekeeper của hệ thống đang chặn; làm theo các bước bên dưới để cho phép nó.

Cài Hiddify trên Windows hiện không còn bị cảnh báo virus trong các lần thử của chúng tôi. Nếu phần mềm diệt virus bạn cài vẫn báo, cứ làm theo đúng thứ tự trong bài: kiểm chứng trước, cho phép sau.

## Vì sao bị chặn

**File tải về từ trang web bị gắn cờ cách ly (quarantine).** Gatekeeper của macOS thấy cờ này thì chặn ứng dụng. Thông báo khi thì nói "bị hỏng", khi thì nói "không thể xác minh nhà phát triển"; nguyên nhân là một.

Việc chúng tôi làm: ứng dụng máy tính là **bản sao nguyên vẹn** gói phát hành của dự án mã nguồn mở gốc. Chúng tôi không sửa, không đóng gói lại, không chèn thêm gì; chỉ đặt nó trên trang tải xuống của mình để bạn tải cho tiện.

## Tự kiểm chứng trước, đừng cho phép mù quáng

Cho phép một ứng dụng nghĩa là hệ thống thôi kiểm tra nó, nên thứ tự là kiểm chứng trước, cho phép sau.

**Tải lên VirusTotal để kiểm tra lại.** Kéo bộ cài vào [virustotal.com](https://virustotal.com/gui/home/upload). Vài engine kiểu suy đoán (heuristic) báo động trong khi các hãng lớn đều cho qua là dấu hiệu điển hình của báo nhầm. Nếu đa số engine lớn đều báo, **đừng cài** — hãy liên hệ ngay với chúng tôi.

Chỉ làm tiếp khi đã qua bước kiểm tra. Không chắc thì liên hệ bộ phận hỗ trợ trước, chúng tôi sẽ kiểm tra trang tải xuống.

## Ba cách cho phép, từ hẹp nhất tới rộng nhất

Sau khi bấm đúp, bạn có thể thấy "“Tên ứng dụng” bị hỏng và không thể mở. Bạn nên di chuyển nó vào Thùng rác" (is damaged and can't be opened), hoặc "không thể mở vì không thể xác minh nhà phát triển". Ba bước dưới đây đi từ hẹp tới rộng; **bước một được rồi thì đừng dùng bước ba**.

1. Tìm ứng dụng trong mục "Ứng dụng" (Applications) của Finder, giữ Control rồi bấm vào biểu tượng (hoặc bấm chuột phải), chọn "Mở" (Open), rồi bấm "Mở" thêm một lần trong hộp thoại hiện ra. Đây là cho phép một lần, chỉ cho riêng ứng dụng này.
2. Nếu menu chuột phải không có "Mở" dùng được, vào "Cài đặt hệ thống" (System Settings) → "Quyền riêng tư & Bảo mật" (Privacy & Security), cuộn xuống phần Bảo mật. Bạn sẽ thấy dòng "“Tên ứng dụng” đã bị chặn vì không phải từ nhà phát triển được xác định". Bấm "Vẫn mở" (Open Anyway) bên phải và nhập mật khẩu để xác nhận.
3. Nếu thông báo là "bị hỏng" thì hai bước đầu thường không có tác dụng. Mở "Terminal", chạy `sudo xattr -dr com.apple.quarantine` kèm theo đường dẫn của ứng dụng (thường là một `.app` trong `/Applications/`), bấm Return, nhập mật khẩu đăng nhập, rồi mở lại ứng dụng. Lệnh này gỡ cờ cách ly đánh dấu nguồn tải về.

Lần chạy đầu tiên, hệ thống còn hỏi mật khẩu để cho phép cài tiện ích mạng (network extension). Bạn đồng ý thì ứng dụng mới tiếp quản được lưu lượng.

Vài lời nhắc:

- Chỉ dùng lệnh `xattr` **với file mà bạn đã kiểm chứng nguồn gốc**; cách kiểm chứng xem phần trước.
- **Đừng** dùng `sudo spctl --master-disable` để tắt Gatekeeper toàn hệ thống. Làm vậy là tắt bảo vệ cho cả máy, trong khi bấm chuột phải → Mở chỉ ảnh hưởng một ứng dụng.
- Từ macOS 15, Apple đã siết cách mở bằng chuột phải, phần lớn trường hợp phải đi qua bước "Cài đặt hệ thống". Đây là thay đổi hành vi của hệ thống, không phải lỗi ở gói của chúng tôi.
- Mac do công ty cấp thường bị hồ sơ MDM quản lý, cả ba bước trên đều có thể bị khóa. Đừng cố; hãy dùng một trong ba lựa chọn bên dưới.

## Không muốn cho phép? Dùng một trong ba cách này

Ứng dụng của chúng **trên macOS bấm đúp là chạy**, không hiện thông báo nào như trên. Vẫn là tài khoản đó, không phải trả thêm:

- **Mạng riêng (ứng dụng Tailscale chính thức)**: cài xong là dùng được, hợp để bật lâu dài
- **OpenVPN Connect**: bộ cài chính chủ của OpenVPN; chỉ cần nhập cấu hình
- **Cisco Secure Client**: ứng dụng cấp doanh nghiệp, nhiều máy tính công ty đã cài sẵn

## Câu hỏi thường gặp

**Chương trình của các bạn có virus thật không?**
Không. Đó là bản sao nguyên vẹn gói phát hành chính thức của dự án mã nguồn mở gốc. Nhưng bạn không nên chỉ tin lời chúng tôi; cách tự kiểm tra đã nói ở trên: tải lên VirusTotal và xem kết quả của các engine phân bố thế nào.

**Trên Windows có còn bị báo không?**
Hiện tại, trong các lần thử của chúng tôi, trung tâm bảo mật có sẵn của Windows không còn báo khi cài Hiddify. Nếu phần mềm diệt virus bạn cài vẫn báo, hãy tải lên VirusTotal kiểm tra lại trước, qua rồi thì đặt thư mục cài Hiddify là tin cậy trong phần mềm diệt virus. Đừng tắt bảo vệ thời gian thực chỉ để cài.

**Cài trên Mac xong không mở được. Có phải tải về bị lỗi không?**
Không. Không mở được là vì Gatekeeper đang chặn. Xử lý bằng ba cách cho phép ở trên.

**Có nên cài thêm phần mềm diệt virus trên Mac không?**
Không. Thứ đang chặn bạn trên macOS là Gatekeeper có sẵn của hệ thống, không phải phần mềm diệt virus. Cài thêm phần mềm diệt virus bên thứ ba không làm thông báo này biến mất, mà còn có thể thêm chỗ chặn mới.

**Điện thoại có bị chuyện này không?**
Trên iOS, cài từ App Store thì không có chuyện này. Android thỉnh thoảng cảnh báo nguồn không xác định; chỉ cần cho phép.

---

Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=troubleshooting-06) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=troubleshooting-06) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
