# 01 · Bắt đầu với router cài sẵn

## Ba bước sau khi mở hộp

1. **Cắm nguồn và dây mạng**: nối cổng WAN của router với modem hoặc router hiện có, đợi đèn báo ổn định, khoảng một phút.
2. **Bắt Wi-Fi**: tên và mật khẩu Wi-Fi mặc định in trên thẻ hướng dẫn (mặc định khi xuất xưởng cả hai đều là tên miền của website). Kết nối xong, mở trình duyệt và vào địa chỉ quản trị `http://192.168.11.1`.
3. **Đăng nhập tài khoản**: trên trang quản trị, nhập email và mật khẩu tài khoản rồi lưu (cả ba gói Cá nhân, Gia đình và Doanh nghiệp đều dùng được router). Từ đó trở đi, mọi thiết bị bắt Wi-Fi này đều tự động đi qua VPN.

## Đổi mật khẩu mặc định

Mật khẩu quản trị và mật khẩu Wi-Fi lúc xuất xưởng là công khai, nên việc đầu tiên sau khi đăng nhập là đổi chúng: trang quản trị → System → Administration (mật khẩu quản trị); Wireless → Interfaces → Wireless Security (bảo mật Wi-Fi).

## Chế độ chia luồng

Mặc định là chia luồng: các tên miền Trung Quốc có trong danh sách đi qua VPN, mọi thứ khác kết nối thẳng. Chế độ này hợp nhất khi bạn ở nước ngoài xem video Trung Quốc, hoặc khi ông bà dùng TV. Khi bạn ở Trung Quốc và chọn khu vực nước ngoài, chiều chia luồng tự đảo lại: mặc định chỉ trang web và dịch vụ bị chặn mới đi qua VPN, còn trang Trung Quốc và trang nước ngoài vốn vào được từ Trung Quốc thì kết nối thẳng; xem [03 · Chia luồng trên router là gì](03-router-split-routing.md). Khi tạm thời cần mọi thứ đi qua VPN, chuyển sang "Global" (toàn bộ), dùng xong chuyển lại.

## Câu hỏi thường gặp

- **Đèn báo bình thường mà thiết bị kết nối vào không có mạng**: xem trạng thái tài khoản trên trang quản trị; tài khoản hết hạn hay sai mật khẩu đều hiện ở đó.
- **Muốn đổi sang router khác**: hủy ràng buộc router cũ trên website trước; xem [Ràng buộc MAC và thay router](05-mac-binding-and-replacing.md).

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-01) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-01) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
