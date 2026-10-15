# 01 · Cisco AnyConnect: cài đặt, kết nối và cập nhật trên mọi nền tảng

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/anyconnect-china?utm_source=github&utm_content=client-01

AnyConnect là ứng dụng VPN doanh nghiệp của Cisco. Tên chính thức bây giờ là **Cisco Secure Client**, cách dùng vẫn y như cũ. Bạn không cần file chứng chỉ hay nhập hồ sơ cấu hình: nhập địa chỉ, tài khoản và mật khẩu là kết nối được. Có dùng được ở Trung Quốc không và không kết nối được thì chuyển sang cách nào, xem [Truy cập dịch vụ nước ngoài từ Trung Quốc, bài 02](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/02-anyconnect-in-china.md) (bằng tiếng Trung).

## Cài đặt

| Nền tảng | Cài gì | Tải ở đâu |
|---|---|---|
| Windows 10 trở lên | Cisco Secure Client 5.x | [Trang Cisco trên website](https://www.leotun.com/vi/anyconnect?utm_source=github&utm_content=client-01) |
| Windows 7 / 8 | AnyConnect 4.9 (bản cuối cùng còn hỗ trợ, không còn cập nhật) | Như trên |
| macOS | Cisco Secure Client 5.x | Như trên |
| iOS | Cisco Secure Client | App Store; nếu cửa hàng không có thì cài OpenConnect mã nguồn mở, dùng cùng giao thức |
| Android | Cisco Secure Client | Google Play, hoặc file APK trên trang website |
| Linux | Bộ cài trên trang website, hoặc openconnect từ kho phần mềm của bản phân phối | Như trên |

Trên Windows còn có OpenConnect-GUI mã nguồn mở, dùng cùng tài khoản được.

## Kết nối trong bốn bước

1. Mở ứng dụng, nhập địa chỉ máy chủ vào ô địa chỉ. Người dùng LeoTun có thể **bấm vào lá cờ của khu vực** trên website để sao chép địa chỉ khu vực đó.
2. Nhập tài khoản (email bạn dùng để đăng ký) và mật khẩu.
3. Khi thấy "Connected" (đã kết nối), mở một trang hiển thị IP để chắc chắn điểm ra nằm ở khu vực bạn đã chọn.
4. Muốn đổi khu vực thì dùng địa chỉ khác. Ứng dụng nhớ các địa chỉ bạn đã dùng, lần sau chọn lại trong danh sách thả xuống là được.

## Cập nhật

Không cần gỡ trước: cài bản mới đè lên bản cũ, các địa chỉ đã lưu vẫn còn. Trên điện thoại thì cập nhật qua kho ứng dụng. Sau khi nâng cấp hệ điều hành lớn, hãy cập nhật ứng dụng trước rồi mới tìm lỗi kết nối.

## Các thông báo thường gặp

| Thông báo | Ý nghĩa |
|---|---|
| Login failed | Sai tài khoản hoặc mật khẩu, hoặc tài khoản đã hết hạn |
| Untrusted server certificate | Nhiều khả năng đồng hồ hệ thống bị sai, hoặc mạng hiện tại đang chặn bắt kết nối mã hóa; thử mạng khác |
| Connection attempt has failed | Địa chỉ này tạm thời không tới được; đổi khu vực |

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=client-01) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=client-01) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
