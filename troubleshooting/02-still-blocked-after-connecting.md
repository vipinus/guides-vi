# 02 · Đã kết nối về Trung Quốc mà vẫn không xem được thì làm sao

Kiểm tra lần lượt theo thứ tự, mỗi bước mất khoảng một phút.

1. **Xác nhận IP lối ra đã thật sự đổi.** Mở trong trình duyệt một trang web cho biết IP của bạn ở đâu, xem có phải Trung Quốc đại lục không. Nếu không phải thì VPN chưa có tác dụng; hãy kết nối lại.
2. **Rò rỉ IPv6 và DNS.** IP lối ra đúng rồi mà trang web vẫn coi bạn là ở nước ngoài thì nhiều khả năng IPv6 hoặc DNS cục bộ của thiết bị đang đi vòng qua VPN. Đây là trường hợp hay gặp nhất và có bài riêng: [03 · IPv6 và DNS là chỗ bị lọt](03-ipv6-and-dns-leak.md).
3. **Bộ nhớ đệm của ứng dụng.** Ứng dụng video và nhạc lưu lại kết quả kiểm tra khu vực. Thoát hẳn ứng dụng rồi mở lại; vẫn không được thì xóa dữ liệu của ứng dụng.
4. **Phiên bản ứng dụng.** Nếu bạn cài bản quốc tế (iQIYI, WeTV) thì kho nội dung khác hẳn. Hãy chuyển sang bản dành cho Trung Quốc đại lục.
5. **Nơi đăng ký tài khoản.** Một số ít nền tảng giới hạn nội dung theo khu vực đăng ký tài khoản, bất kể IP hiện tại của bạn. Khi đó chỉ còn cách dùng tài khoản khác.
6. **Khu vực và ngôn ngữ hệ thống.** Có ứng dụng đọc khu vực của hệ thống. Đổi khu vực hệ thống sang Trung Quốc rồi thử lại.
7. **Khu vực điểm vào.** Một số nội dung còn khác nhau giữa IP của các tỉnh. Đổi sang điểm vào khác rồi thử lại.

## Vẫn không được

Báo cho bộ phận hỗ trợ bốn điều: trang web hoặc ứng dụng bạn muốn vào, nguyên văn thông báo lỗi, IP lối ra hiện tại của bạn ở đâu, và cách kết nối bạn đang dùng. Có đủ bốn điều này là xác định được vấn đề ngay một lần.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=troubleshooting-02) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=troubleshooting-02) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
