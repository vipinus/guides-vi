# 01 · Những dịch vụ nào cần IP nước ngoài, và đường truyền hoạt động thế nào

Phép thử ngược hẳn với chuyện truy cập Trung Quốc từ nước ngoài: khi dịch vụ thấy IP nguồn của bạn ở Trung Quốc đại lục, hoặc bạn hoàn toàn không tới được máy chủ của nó, thì nó không mở được, bị hạ cấp hoặc cực kỳ chậm. Bảng dưới đây xếp theo mục đích sử dụng.

| Loại | Ví dụ | Không có đường truyền thì sao | Ngoài IP còn cần gì |
|---|---|---|---|
| Công việc | Google Workspace, Slack, Zoom, Teams, Notion | Không mở được, hoặc liên tục bị ngắt | Tài khoản công ty |
| Lập trình | GitHub, npm, Docker Hub, nguồn PyPI không phải bản mirror, Stack Overflow | Chậm tới mức hết thời gian chờ | Không có |
| AI | ChatGPT, Claude, Gemini | Không mở được | Quốc gia đăng ký tài khoản, số điện thoại |
| Nghiên cứu | Google Scholar, cơ sở dữ liệu bài báo, email trường đại học | Không mở được, hoặc cực chậm | Tài khoản của trường |
| Game | Steam khu vực nước ngoài, PSN, Switch eShop, máy chủ nước ngoài | Cửa hàng không mở được, độ trễ cao | Tài khoản thuộc máy chủ khu vực đó |
| Video và nhạc | YouTube, Netflix, Disney+, Spotify | Không mở được | Tài khoản trả phí, và khu vực tài khoản phải khớp với IP |
| Mạng xã hội | X, Instagram, Telegram, Discord, WhatsApp | Không mở được | Số điện thoại |

## Một điểm cần phân biệt

**"Cần IP nước ngoài" và "cần tài khoản nước ngoài" là hai chuyện khác nhau.** Với GitHub và YouTube, đổi IP là đủ; Netflix cần tài khoản trả phí có khu vực khớp; đăng ký ChatGPT cần một số điện thoại nước ngoài nhận được mã xác minh. Đường truyền giải quyết chuyện "có mở được không"; còn tài khoản là việc của bạn.

## Đường truyền hoạt động thế nào

Lưu lượng của bạn được mã hóa và gửi tới một máy chủ ở nước ngoài trước, rồi máy chủ đó truy cập trang đích. Trang đích nhìn thấy IP của máy chủ đó. Có ba cách làm: ứng dụng, Web Proxy và router. Chọn thế nào thì xem [Cách kết nối nào hợp với tình huống nào](../network/02-choose-your-connection-method.md).

## Ba hiểu lầm thường gặp

- **Đổi DNS không giải quyết được.** Không kết nối được là do đường đi, không phải do phân giải tên miền.
- **Tốc độ phụ thuộc vào đường truyền giữa hai đầu.** Đi ra từ Trung Quốc, nút thắt nằm ở đoạn xuyên biên giới và cổng ra quốc tế của nhà mạng, nên chọn khu vực quan trọng hơn cấu hình máy chủ; xem [bài 03](03-which-region-is-fastest.md).
- **Khi dùng ứng dụng Trung Quốc, không phải mọi thứ đều phải đi qua đường truyền.** Hãy bật chia luồng: mặc định chỉ các trang bị chặn mới đi qua đường truyền, còn trang Trung Quốc và các trang nước ngoài vốn vào được từ Trung Quốc thì kết nối trực tiếp, không bên nào phải đi đường vòng; xem [Chia luồng trên router](../router/03-router-split-routing.md).

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=overseas-access-01) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=overseas-access-01) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, hiệu lực lâu dài
