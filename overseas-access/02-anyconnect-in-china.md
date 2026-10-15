# 02 · Cisco AnyConnect có dùng được ở Trung Quốc không

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/anyconnect-china?utm_source=github&utm_content=overseas-access-02

Có. AnyConnect là giao thức VPN doanh nghiệp của Cisco. Các công ty khắp thế giới dựa vào nó để làm việc từ xa, chi nhánh của công ty nước ngoài ở Trung Quốc ngày nào cũng dùng, nên cái giá của việc cấm hẳn là quá cao. **Thứ thật sự bị chặn là một địa chỉ máy chủ cụ thể, không phải giao thức.** Vì vậy "có dùng được không" phụ thuộc vào việc nhà cung cấp có đủ địa chỉ và thay đủ nhanh hay không.

## Vì sao nó chịu chặn tốt hơn ứng dụng VPN độc quyền

| | AnyConnect | Ứng dụng VPN độc quyền |
|---|---|---|
| Dấu hiệu lưu lượng | TLS chuẩn, giống như vào một trang web HTTPS | Giao thức riêng, dấu hiệu cố định |
| Khi bị nhận diện | Chỉ địa chỉ đó không kết nối được | Cả ứng dụng ngừng hoạt động |
| Ứng dụng | Do Cisco phát hành; bản thay thế mã nguồn mở OpenConnect có trên mọi nền tảng | Bị gỡ khỏi kho ứng dụng là mất |

LeoTun tự vận hành máy ở 24 khu vực. Địa chỉ nào bị đánh dấu thì được thay bằng địa chỉ mới, tên miền tự trỏ sang, địa chỉ đã lưu trong ứng dụng của bạn không cần sửa.

## Cài đặt thế nào

1. Tải file cài cho hệ điều hành của bạn ở trang Cisco trên website. Có đủ Windows 10 trở lên, macOS, iOS, Android và Linux; Windows 7/8 chỉ dùng được bản 4.9, bản cuối cùng còn hỗ trợ chúng.
2. Mở ứng dụng, nhập địa chỉ máy chủ vào ô địa chỉ — trên website, bấm vào lá cờ của một khu vực để sao chép.
3. Nhập tài khoản và mật khẩu rồi kết nối. Không cần file chứng chỉ, cũng không cần nhập cấu hình.
4. Thấy "Connected" (đã kết nối) thì kiểm tra IP lối ra của bạn.

## Không kết nối được thì làm lần lượt

1. **Đổi sang khu vực khác.** Khu vực khác kết nối được thì chỉ là máy chủ kia tạm thời không với tới được.
2. **Đổi mạng.** Băng thông rộng không được thì chuyển sang dữ liệu di động, và ngược lại; can thiệp trên các nhà mạng khác nhau không đồng bộ với nhau.
3. **Đọc báo lỗi.** `Login failed` là do tài khoản hoặc mật khẩu, hoặc đã hết hạn; `Untrusted server certificate` nhiều khả năng là giờ hệ thống sai hoặc mạng hiện tại đang chặn bắt TLS, hãy đổi mạng; chỉ `Connection attempt has failed` mới có nghĩa là không với tới được địa chỉ.
4. **Cập nhật ứng dụng.** Đặc biệt quan trọng sau khi nâng cấp hệ điều hành lớn.
5. **Đổi cách kết nối.** Cùng tài khoản có thể dùng OpenVPN hoặc Hiddify để kết nối tới cùng các máy chủ, và việc chặn ba giao thức độc lập với nhau; xem [02 · Mỗi cách kết nối hợp với tình huống nào](../network/02-choose-your-connection-method.md).

## Cập nhật Cisco AnyConnect

Cisco đã đổi tên nó thành Cisco Secure Client; cách dùng vẫn như cũ. Không cần gỡ bản cũ trước: cài bản mới đè lên là các địa chỉ đã lưu vẫn còn. Trên điện thoại thì cập nhật trong App Store / Google Play; tìm trong kho không thấy thì dùng OpenConnect mã nguồn mở, cùng giao thức, cùng tài khoản (đổi khu vực của App Store trên iOS xem [Hướng dẫn ứng dụng 06](../client/06-ios-app-store.md)).

## Câu hỏi thường gặp

**Chậm có phải là bị bóp tốc độ không?** Đổi khu vực trước: xem đèn đỏ, vàng, xanh trong danh sách khu vực trên website và chọn khu vực đèn xanh. Vẫn chậm thì nguyên nhân thường nằm ở băng thông rộng tại chỗ: mạng dùng chung của khu chung cư, hoặc nhà mạng và khu vực không hợp nhau (China Unicom miền Bắc: Nhật Bản hoặc Hàn Quốc; China Telecom miền Nam: Đông Nam Á hoặc Úc; nhà mạng khác: các điểm vào ở Trung Quốc).

**Sao cùng một địa chỉ lúc tốt lúc kém?** Địa chỉ là một tên miền, các máy phía sau được tự động thay theo tình hình bị chặn và tải. Đợi một hai phút rồi thử lại thường là được, vì bạn vừa gặp đúng lúc đang chuyển đổi.

**Kết nối lâu có tự ngắt không?** Không phải vì thời gian. Tài khoản hết hạn thì máy chủ ngắt kết nối; gia hạn rồi kết nối lại là được.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=overseas-access-02) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=overseas-access-02) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
