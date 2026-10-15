# 09 · Chia luồng trên router hoạt động thế nào

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/router-smart-split?utm_source=github&utm_content=router-09

Router nào cũng quảng cáo "chia luồng thông minh", vậy mà có cái dùng cứ thấy trục trặc. Chia luồng là gì thì xem [03](03-router-split-routing.md); bài này chỉ nói chia luồng đúng nghĩa phải làm được gì, thiếu một phần thì bạn sẽ gặp triệu chứng gì, và router của chúng tôi làm thế nào.

## Nói gọn trong một câu

Chia luồng đúng nghĩa: mỗi trang web, **cùng với hình ảnh, video và phần đăng nhập của nó**, đi qua VPN hoặc kết nối thẳng tùy theo nơi đặt trang, và **mọi thiết bị trong nhà theo cùng một bộ quy tắc**. Chỉ làm được một phần thì bạn sẽ gặp các triệu chứng dưới đây.

## Đối chiếu triệu chứng

| Bạn thấy gì | Nguyên nhân phía sau |
|---|---|
| Bật chia luồng xong, trang web Trung Quốc lại chậm hơn | Trang Trung Quốc bị nhầm là trang nước ngoài, cả trang phải đi vòng ra nước ngoài rồi quay về |
| Trang web mở được nhưng video quay vòng mãi, hình không hiện, đăng nhập treo | Danh sách chỉ có trang chính, còn video, hình ảnh và đăng nhập của cùng trang đó đi đường khác |
| Ở nước ngoài đã bật đường truyền về Trung Quốc mà ứng dụng video vẫn báo "仅限中国大陆" (chỉ dành cho Trung Quốc đại lục) | Một phần lưu lượng không vào VPN, trang web nhìn thấy địa chỉ nước ngoài |
| Điện thoại xem được mà TV hay TV box không xem được; có máy tính nhất quyết không đi qua VPN | Thiết bị đó có cài đặt mạng riêng và đi vòng qua router |
| Ứng dụng ngân hàng, thanh toán thỉnh thoảng cảnh báo "đăng nhập từ nơi khác" | Lưu lượng của cùng một ứng dụng lúc thì ra từ Trung Quốc, lúc lại ra từ nước ngoài |
| Đang dùng thì chia luồng biến mất (khởi động lại hay kết nối lại xong thì hoặc tất cả đi VPN, hoặc không gì đi cả) | Cài đặt không được ghi nhớ |

Không triệu chứng nào trong số này **báo lỗi**. Router lúc nào cũng hiện "Đã kết nối", nên đây là loại khó tìm nguyên nhân nhất, và nhiều người rốt cuộc cho rằng đường truyền kém.

## Chia luồng đúng nghĩa phải làm được gì

- Một trang web đi một đường cùng với trang, hình ảnh, video và đăng nhập của nó, không bị tách ra
- Khi phân định "Trung Quốc hay nước ngoài", đứng đúng phía, trang Trung Quốc không phải đi vòng
- Mọi thiết bị trong nhà theo cùng quy tắc, đổi cài đặt mạng ngay trên thiết bị cũng không lách được
- Chiều chia luồng tự đổi theo khu vực đã chọn (truy cập Trung Quốc từ nước ngoài và truy cập dịch vụ nước ngoài từ Trung Quốc là hai bộ quy tắc ngược nhau)
- Danh sách tự cập nhật, không phải cài lại firmware
- Cài đặt được ghi nhớ: khởi động lại hay kết nối lại vẫn giữ nguyên; đã tắt thì không lặng lẽ tự bật lại

## Chia luồng thông minh trên router của chúng tôi

| | Cách làm |
|---|---|
| Công tắc | Mặc định bật; chọn khu vực Trung Quốc = chiều truy cập Trung Quốc từ nước ngoài, chọn khu vực nước ngoài = chiều truy cập dịch vụ nước ngoài từ Trung Quốc, tự áp dụng. Chiều từ Trung Quốc ra nước ngoài còn có ô "Blocked sites only" (chỉ trang bị chặn mới đi VPN) trong "VPN settings" (cài đặt VPN) → chia luồng thông minh, mặc định đã đánh dấu; bỏ đánh dấu = trang Trung Quốc đi thẳng, mọi thứ khác qua VPN. Firmware cài trước tháng 10/2026 chưa hiện ô này; liên hệ bộ phận hỗ trợ để họ đổi từ xa |
| Danh sách | Sắp xếp theo "cả trang web": trang đi cùng với các nguồn video, hình ảnh và đăng nhập mà nó dùng |
| Truy cập dịch vụ nước ngoài từ Trung Quốc | Mặc định chỉ trang web và dịch vụ bị chặn mới đi qua VPN (dựa trên danh sách trang bị chặn tự cập nhật mỗi ngày, cộng thêm các dịch vụ kết nối tới địa chỉ cố định như Telegram); trang Trung Quốc và trang nước ngoài vốn vào được từ Trung Quốc (trang của công ty nước ngoài, bản tải của Apple và Microsoft, nền tảng game) kết nối thẳng, không đi vòng, tốc độ như khi không có router |
| Thiết bị trong nhà | Được quản lý thống nhất; đổi cài đặt mạng ngay trên thiết bị vẫn phải theo quy tắc; không có "cửa sau" để vòng qua router |
| Cập nhật | Danh sách và quy tắc tự cập nhật khi router khởi động; danh sách trang bị chặn còn tự cập nhật mỗi ngày |
| Ghi nhớ | Giữ nguyên sau khi kết nối lại hay khởi động lại; đã tắt thì vẫn tắt |
| Mạng nội bộ | Máy in, NAS và camera vẫn truy cập thẳng như thường |

**Trường hợp duy nhất cần bạn giúp một tay**: khi điện thoại hoặc trình duyệt bật cài đặt mã hóa kiểu "DNS riêng tư" (Private DNS) hay "DNS bảo mật" (Secure DNS), thiết bị tự mã hóa việc tra tên miền và router không nhìn thấy. Nếu một thiết bị hoạt động bất thường, hoặc mọi thứ khác bình thường mà trang bị chặn không mở được, hãy tắt loại cài đặt này trước.

## Tự kiểm tra

1. Bạn ở Trung Quốc (truy cập dịch vụ nước ngoài): Baidu, Taobao và các trang nước ngoài vốn vào được từ Trung Quốc như bản tải của Apple và Microsoft có tốc độ bình thường; trang nước ngoài bị chặn mở được, video phát được.
2. Bạn ở nước ngoài (truy cập Trung Quốc): chọn bất kỳ tập phim nào trên Tencent Video hoặc iQIYI đều phát được, không có thông báo "仅限中国大陆" (chỉ dành cho Trung Quốc đại lục); trang ngân hàng và mua sắm tại chỗ vẫn dùng bình thường.
3. Thử từng thiết bị, nhất là TV và TV box; máy nào bất thường thì kiểm tra "DNS riêng tư / DNS bảo mật" trước, rồi xác nhận nó đang bắt Wi‑Fi của router này chứ không phải của modem.
4. Một trang web không mở được khi chia luồng: tạm chuyển sang "Global" (toàn bộ). Nếu ở Global mở được mà chia luồng thì không, nghĩa là trang đó chưa có trong danh sách; gửi địa chỉ cho bộ phận hỗ trợ để thêm vào, nó sẽ đến với bạn qua lần cập nhật tự động. Ở Trung Quốc bạn cũng có thể bỏ đánh dấu "Blocked sites only" trong phần chia luồng thông minh rồi thử lại; mở được thì trang đó cũng là bị chặn nhưng chưa có trong danh sách.

## Câu hỏi thường gặp

**Có phải tự bật chia luồng thông minh không?** Không. Đăng nhập tài khoản và chọn khu vực là nó đã bật.

**Truy cập Trung Quốc từ nước ngoài và truy cập dịch vụ nước ngoài từ Trung Quốc có phải thiết lập riêng không?** Không. Chiều chia luồng do khu vực đã chọn tự quyết định.

**Có ảnh hưởng tới máy in hay NAS không?** Không. Thiết bị trong mạng nhà vẫn truy cập thẳng như thường.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-09) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-09) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
