# 06 · Mở khóa web xem video Trung Quốc từ nước ngoài bằng router

## Vì sao dùng router thay vì cài ứng dụng trên từng thiết bị

- TV, đầu thu, máy chiếu và máy chơi game không cài được ứng dụng, nên router là cách duy nhất.
- Nhà đông người, cài cho từng thiết bị của từng người là không thực tế; cài router một lần, thiết bị nào bắt Wi-Fi là có tác dụng ngay.
- Chia luồng làm trên router, nên các trang web tại chỗ và thiết bị trong nhà vẫn kết nối thẳng; chỉ tên miền video Trung Quốc mới đi qua đường truyền về Trung Quốc, tốc độ không bị ảnh hưởng.

## Bạn cần gì

| Thứ cần có | Ghi chú |
|---|---|
| Một router được hỗ trợ | Loại cài sẵn thì cắm là dùng; tự cài firmware thì xem [Cách cài firmware](02-flash-firmware-yourself.md) |
| Một tài khoản | Cả ba gói Cá nhân, Gia đình và Doanh nghiệp đều dùng được tính năng Router. Đăng ký xong hãy nhận gói dùng thử miễn phí trước để chạy thử toàn bộ quy trình: tài khoản mới ở gói Cá nhân, được dùng thử 4 giờ |
| Mạng phía trên | Modem hoặc router sẵn có trong nhà; router mới đặt phía sau nó |

## Xong trong năm bước

1. Nối cổng WAN của router mới vào mạng phía trên, cắm điện và đợi một phút.
2. Cho điện thoại bắt Wi-Fi của router mới, mở địa chỉ quản trị `http://192.168.11.1` và đăng nhập tài khoản.
3. Chọn chế độ **Split routing** (chia luồng). Tên miền video Trung Quốc có sẵn trong danh sách và sẽ tự đi qua đường truyền về Trung Quốc.
4. Chuyển TV và đầu thu sang Wi-Fi này, hoặc cắm dây vào cổng LAN của router mới.
5. Mở iQIYI, Tencent Video hoặc Yangshipin (CCTV); phát bình thường là xong.

## Danh sách là công khai

Các tên miền video trong danh sách chia luồng được duy trì trong một kho công khai: <https://github.com/vipinus/openwrt-2026-video-domains>. Nền tảng nào không phát được, bạn có thể xem tên miền của nó có trong danh sách chưa, chưa có thì gửi bổ sung.

## Chất lượng hình và băng thông

1080p cần ổn định 5 Mbps, 4K cần từ 25 Mbps trở lên. Nếu giờ cao điểm buổi tối bị giật, hãy chọn khu vực đèn xanh; vẫn giật thì nguyên nhân thường nằm ở mạng cáp tại chỗ. Khu vực điểm vào nên chọn nơi gần bạn và có tuyến tốt về Trung Quốc đại lục; thử vài cái, lấy chuyện có giật hay không làm thước đo.

## Câu hỏi thường gặp

- **Điện thoại xem được mà TV thì không**: TV vẫn đang bắt Wi-Fi cũ, hoặc ứng dụng trên TV là bản quốc tế.
- **Có nền tảng xem được, có nền tảng không**: tên miền của nền tảng đó chưa có trong danh sách chia luồng. Tạm chuyển sang "Global" (toàn cục) để kiểm chứng, rồi gửi lên kho danh sách.
- **Router cũ làm cả nhà chậm đi**: CPU không theo kịp lưu lượng mã hóa; hãy đổi sang mẫu mạnh hơn, xem [Bắt đầu với router cài sẵn](01-plug-and-play-router.md).

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-06) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-06) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
