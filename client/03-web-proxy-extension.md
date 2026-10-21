# 03 · Web Proxy: thiết lập tiện ích ZeroOmega trong hai bước

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/web-proxy?utm_source=github&utm_content=client-03

Web Proxy chỉ đưa **trình duyệt này** đi qua đường truyền; các chương trình khác trên máy vẫn để nguyên. Không phải cài ứng dụng, không cần quyền quản trị, và cũng không có trạng thái "đã kết nối", nên về thiết kế thì không có kết nối nào để rớt. Cách này hợp với máy tính công ty, máy đang chạy VPN của công ty, hoặc khi bạn chỉ muốn một trình duyệt dùng đường truyền. Khi nào dùng nó, khi nào bắt buộc phải dùng VPN, xem [Hướng dẫn về mạng 02](../network/02-choose-your-connection-method.md).

## Hai bước

1. **Cài tiện ích**: cài ZeroOmega (bản kế thừa của SwitchyOmega) trên Chrome / Edge / Firefox. [Trang Proxy trên website](https://www.leotun.com/vi/httpproxy?utm_source=github&utm_content=client-03) có link cài cho từng trình duyệt.
2. **Nhập cấu hình**: đăng nhập website, trên trang Proxy bấm vào lá cờ của khu vực bạn muốn (hoặc bấm "Sao chép liên kết nhập cho tất cả khu vực" để nhập tất cả một lần); thao tác này sao chép link cấu hình. Mở mục "Import/Export" (Nhập/Xuất) của tiện ích, dán vào ô "Restore from online" (Khôi phục từ trực tuyến) rồi bấm "Restore" (Khôi phục). Khu vực, địa chỉ và cách mã hóa được nhập một lượt, không phải gõ tay gì cả.

Sau đó bấm biểu tượng tiện ích, chọn một khu vực, rồi nhập tài khoản và mật khẩu website vào hộp đăng nhập mà trình duyệt hiện ra. Muốn đổi khu vực thì bấm khu vực khác trong menu của biểu tượng; muốn quay lại kết nối thẳng tại chỗ thì chuyển sang "Direct" (Trực tiếp).

## Những trường hợp sau hãy dùng cách cho cả máy

- Ứng dụng video, nhạc và trình phát: phần lớn không dùng proxy của trình duyệt, nên sẽ gặp cảnh "trang web mở được mà video không phát".
- Ứng dụng điện thoại, game và phần mềm máy tính. Phần cài đặt proxy trong các phần mềm như Dropbox chỉ nhận HTTP / SOCKS5 không mã hóa, trong khi thực tế proxy phải được mã hóa, nên Web Proxy của trang này không điền vào đó được. Hãy dùng Hiddify để tiếp quản cả máy; xem [10](10-app-proxy.md).
- Xem Tencent Video hay iQIYI từ nước ngoài: trang video còn kiểm tra IPv6 và DNS, mà Web Proxy không bao được; hãy dùng VPN cho cả máy.

## Câu hỏi thường gặp

| Biểu hiện | Nguyên nhân |
|---|---|
| Hộp đăng nhập cứ hiện ra mãi | Tài khoản đã hết hạn hoặc sai mật khẩu |
| Có trang không mở được, trang khác thì bình thường | Quy tắc "auto switch" (tự chuyển) trong tiện ích đã cho các trang đó đi thẳng; thử chế độ proxy toàn cục một lần |
| Ở Trung Quốc chỉ mở được trang HTTPS | HTTP thường bị sửa đổi trên đường đi, chỉ kết nối mã hóa mới qua được; ngày nay gần như mọi trang đều là HTTPS |
| Chậm | Đổi khu vực; proxy và VPN dùng chung một bộ máy chủ |

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=client-03) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=client-03) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
