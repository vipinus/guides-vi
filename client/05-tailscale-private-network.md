# 05 · Mạng riêng (Tailscale): cài đặt, đăng nhập vào máy chủ điều khiển của trang này, chọn điểm thoát

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/tailscale-mesh?utm_source=github&utm_content=client-05

Mục Mạng riêng dùng Tailscale (một công cụ kết nối mạng xây trên WireGuard). LeoTun tự vận hành máy chủ điều khiển, và bạn đăng nhập bằng **tài khoản của trang này**, không liên quan gì tới tài khoản Tailscale chính thức. Đăng nhập một lần là luôn trực tuyến; khu vực lối ra đổi được trong menu bất cứ lúc nào. Nó khác VPN ở đâu và hợp với ai, xem [Hướng dẫn về mạng 03](../network/03-private-network-vs-vpn.md).

## Cài đặt

| Nền tảng | Lấy ở đâu |
|---|---|
| Windows / macOS / Linux / Android | Khu tải xuống trên [trang Mạng riêng của website](https://www.leotun.com/vi/mesh?utm_source=github&utm_content=client-05) (trang này phát trực tiếp, không phải vào trang chính thức) |
| iPhone / iPad | App Store; cần Apple ID ngoài khu vực Trung Quốc (xem [Hướng dẫn ứng dụng 06](06-ios-app-store.md)) |

## Đăng nhập

1. **Đăng xuất tài khoản chính thức trước** (nếu từng đăng nhập): trên điện thoại, chạm ảnh đại diện → Log Out; trên máy tính, chạy `tailscale logout`. Chưa đăng xuất hẳn thì tùy chọn cần dùng ở bước sau sẽ không hiện ra.
2. **Trỏ việc đăng nhập tới trang này**:
   - Điện thoại: ở màn hình chưa đăng nhập, chạm "⋯" góc trên bên phải → Use custom server (một số phiên bản gọi là Use an alternate server — dùng máy chủ khác), nhập địa chỉ ghi trên trang Mạng riêng của website rồi chạm Log in.
   - Windows / Linux: sao chép lệnh `tailscale up --login-server=…` trên trang website rồi chạy trong PowerShell / terminal.
   - macOS: **đừng bấm Log in**. Trong cửa sổ Tailscale, bấm mũi tên ở dòng tài khoản → Account Settings… → Accounts → mũi tên nhỏ cạnh "Add Account…" → Add Account Using Alternate Server, dán địa chỉ vào rồi bấm Add Account….
3. Trình duyệt tự mở trang đăng nhập của trang này; xác nhận bằng tài khoản của trang này. Quay lại ứng dụng là đã trực tuyến.

## Chọn lối ra

- Điện thoại: menu → Exit Node (điểm thoát), chọn một khu vực; có hiệu lực ngay.
- Máy tính: biểu tượng ở khay hệ thống / thanh menu → menu con Exit Node; hoặc `tailscale set --exit-node=<region-name>` (`tailscale exit-node list` cho biết có những lối ra nào).
- Không muốn dùng lối ra thì chọn None (trên dòng lệnh, để trống phần sau dấu bằng). Mỗi lúc chỉ dùng được một lối ra.

## Hết hạn và số thiết bị

- Hiệu lực đăng nhập của thiết bị đi theo ngày hết hạn của tài khoản; hết hạn thì thiết bị ngoại tuyến trong vài phút; gia hạn xong chỉ cần đăng nhập lại một lần. Không phải cài lại.
- Số thiết bị trực tuyến cùng lúc tùy theo gói (Cá nhân 2, Gia đình 4, Doanh nghiệp 8), hạn mức dùng chung với các cách kết nối khác; khi vượt giới hạn của gói, bạn có thể tạm nâng hạng tài khoản (thời gian còn lại được quy đổi ngang giá theo giá gói) rồi dùng xong đổi lại.

## Hai trường hợp nên dùng cách khác

- Trên cùng thiết bị đang chạy một VPN khác (AnyConnect của công ty, phần mềm mạng mesh khác): chúng giành nhau DNS và tuyến đường. Đây là nguyên nhân của việc xem video Trung Quốc bị báo bản quyền và mạng nội bộ công ty không mở được.
- Trên mạng trường học / công ty hạn chế UDP: WireGuard chạy trên UDP nên chỉ đi qua được relay (máy chủ chuyển tiếp của Tailscale), rất chậm; hãy chuyển sang AnyConnect.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=client-05) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=client-05) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
