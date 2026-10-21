# 08 · Chọn đường truyền về Trung Quốc thế nào: IP Trung Quốc từ đâu ra và hàng miễn phí hỏng ở chỗ nào

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/choose-china-vpn?utm_source=github&utm_content=china-access-08

Đường truyền về Trung Quốc chỉ làm đúng một việc: khiến các yêu cầu bạn gửi từ nước ngoài tới Tencent Video, NetEase Cloud Music hay ngân hàng trực tuyến đến nơi bằng một IP **Trung Quốc đại lục**. Vì vậy hãy xem hai điểm trước: lối ra có thật là IP đại lục không, và trên thiết bị có lưu lượng nào đi vòng qua nó không. Tốc độ, giá cả và ứng dụng đều xếp sau.

## IP Trung Quốc từ đâu ra

Nhà cung cấp phải có máy chủ riêng ở trong đại lục. Nhà cung cấp đám mây ở Trung Quốc đòi đăng ký thực danh mới cho thuê máy, và tính băng thông theo mức dùng, nên chi phí cao hơn máy ở nước ngoài rất nhiều. Đó là lý do gần như mọi dịch vụ về Trung Quốc đàng hoàng đều thu phí, và số lối ra Trung Quốc có hạn.

Một kiểu thay thế hay gặp là lấy máy ở Hồng Kông, Đài Loan hay Nhật Bản rồi gọi là "về Trung Quốc". Những địa chỉ này dùng được cho một số mục Hồng Kông, Ma Cao và Đài Loan của Bilibili, nhưng Tencent Video, iQIYI và Youku vẫn báo giới hạn bản quyền, ngân hàng trực tuyến và 12306 cũng vẫn coi bạn là ở nước ngoài. **Cách nhận biết: kết nối xong, tra xem IP được đăng ký ở đâu; chỉ khi nó hiện "Trung Quốc · tỉnh nào đó" mới tính.**

## Năm điều cần kiểm tra trước khi chọn

| Hạng mục | Kiểm tra thế nào | Không đạt thì trông ra sao |
|---|---|---|
| Khu vực lối ra | Kết nối xong, tra nơi đăng ký của IP | Địa chỉ Hồng Kông, Đài Loan, Nhật Bản hay Hàn Quốc |
| IPv6 và DNS | Tìm "test ipv6" và mở một trang kiểm tra | Mục IPv6 hiện quốc gia bạn đang ở → trang video vẫn chặn bạn, xem [Khắc phục sự cố 03](../troubleshooting/03-ipv6-and-dns-leak.md) |
| Ứng dụng | Có phải giao thức chuẩn không (AnyConnect, OpenVPN, Hiddify) | Chỉ có một ứng dụng độc quyền, bị gỡ khỏi kho là bạn hết cái để dùng |
| Băng thông | Phát 1080p trong khoảng 8–11 giờ tối giờ Bắc Kinh | Ban ngày nhanh, tối thì quay vòng mãi |
| Nhiều thiết bị và router | Mỗi tài khoản được mấy thiết bị, router có kết nối được cả nhà không | Mỗi thiết bị phải mua riêng |

## Vì sao đường truyền về Trung Quốc miễn phí hay rớt

Vấn đề không phải ở chữ "miễn phí" mà ở cơ cấu chi phí. Băng thông lối ra ở đại lục tính tiền theo mức dùng, và dịch vụ miễn phí chỉ có thể chọn một trong ba: nhồi vài nghìn người lên một máy, nên giờ cao điểm ai cũng giật; giới hạn dung lượng và thời gian, nên đang xem giữa chừng thì bật lên lời mời trả tiền; hoặc kiếm tiền cách khác, bằng cách chèn quảng cáo, thu thập lịch sử duyệt web, hay biến thiết bị của bạn thành lối ra cho người khác.

Các tiện ích trình duyệt "về Trung Quốc" miễn phí còn một điểm mù nữa: chúng chỉ proxy các yêu cầu web của trình duyệt, còn trình phát video, ứng dụng và DNS hệ thống thì không đi qua, vì vậy cảnh "trang web mở được mà video không phát" mới phổ biến đến thế.

Thỉnh thoảng tra cứu một chút thì miễn phí là đủ. Còn để theo dõi phim bộ, nghe nhạc và dùng ngân hàng trực tuyến, thời gian mà một đường truyền trả phí ổn định giúp bạn tiết kiệm đáng giá hơn tiền thuê bao nhiều. Hãy nhận gói dùng thử 4 giờ trước, thử một lần vào giờ cao điểm buổi tối, rồi hãy quyết định.

## Du học sinh, người đi lại và gia đình nên thiết lập thế nào

- **Du học sinh**: mạng ký túc xá phần lớn có IPv6, nên dùng ứng dụng có chặn IPv6; với ngân hàng trực tuyến, CHSI và 12306, chỉ kết nối đường truyền về Trung Quốc khi cần và ngắt khi xong, để giảm bị kiểm soát rủi ro tài khoản.
- **Chuyến đi ngắn**: cài ứng dụng Cisco hoặc Hiddify trên điện thoại và nhập bằng cách quét mã QR; xuống máy bay là dùng được.
- **Cả gia đình sống lâu dài ở nước ngoài**: dùng một router đã cài firmware kết nối đường truyền, TV, đầu thu và điện thoại của người lớn tuổi không phải cài gì; xem [Mở khóa web xem video Trung Quốc từ nước ngoài bằng router](../router/06-unlock-chinese-video-with-router.md).

## Tự kiểm tra trong 5 phút

1. Kết nối đường truyền về Trung Quốc; tra IP thấy một tỉnh của Trung Quốc đại lục.
2. Trang kiểm tra IPv6 báo không có IPv6, hoặc cũng là địa chỉ đại lục.
3. Mở một phim bộ bất kỳ chỉ có ở Trung Quốc trên Tencent Video; phát được.
4. Sau 8 giờ tối giờ Bắc Kinh, phát 1080p thêm một lần; không bị dừng nạp liên tục.
5. Đổi sang một lối ra Trung Quốc khác và làm lại ba bước đầu.

## Câu hỏi thường gặp

**VPN về Trung Quốc và phần mềm tăng tốc về Trung Quốc có khác nhau không?** Về bản chất thì không. "Phần mềm tăng tốc" thường là ứng dụng do hãng game hay hãng video tùy biến, chỉ phục vụ một số ứng dụng nhất định; VPN là đường hầm cho cả thiết bị.

**Dùng node Hồng Kông xem Tencent Video được không?** Không, bản quyền chỉ áp dụng cho đại lục.

**Mỗi tài khoản được mấy thiết bị?** Với LeoTun, số kết nối cùng lúc theo gói: Cá nhân 2 thiết bị, Gia đình 4 thiết bị, Doanh nghiệp 8 thiết bị. Router tính là một thiết bị, các thiết bị phía sau nó không tính riêng. Khi số thiết bị trực tuyến cùng lúc vượt giới hạn của gói, bạn có thể tạm nâng hạng tài khoản (thời gian còn lại được quy đổi ngang giá theo giá gói) rồi dùng xong đổi lại.

**Dùng Clash được không?** Được. LeoTun cung cấp link đăng ký sing-box, link đăng ký Clash và link chia sẻ hysteria2. Với Clash Meta, Clash Verge, FlClash, Stash và các ứng dụng tương tự, bấm nút "Đăng ký Clash" rồi dán URL vào danh sách đăng ký của ứng dụng; không cần công cụ chuyển đổi link đăng ký, và đừng dùng link chia sẻ. Clash bản gốc và Clash for Windows không dùng được, vì lõi của chúng không có hysteria2. Link đăng ký này mặc định đưa mọi thứ trừ mạng nội bộ đi qua node, nên xem video Trung Quốc không phải chỉnh gì; nếu bạn tự thêm quy tắc thì đừng đặt tên miền Trung Quốc là "direct" (kết nối thẳng).

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=china-access-08) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=china-access-08) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
