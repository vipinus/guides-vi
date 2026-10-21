# 07 · Xem camera ở nhà bên Trung Quốc khi đang ở nước ngoài

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/home-camera?utm_source=github&utm_content=china-access-07

## Ba trường hợp, mỗi trường hợp một cách xử lý

| Hệ thống camera ở nhà bạn thuộc loại nào | Ở nước ngoài xem thẳng được không | Cách xử lý |
|---|---|---|
| Ứng dụng của hãng có lưu trữ đám mây (EZVIZ, Xiaomi, TP-Link, Imou, v.v.) | Phần lớn là được; ở vài khu vực bị hạn chế hoặc cực chậm | Chuyển sang IP Trung Quốc và dùng bản ứng dụng dành cho Trung Quốc |
| Đầu ghi hình mạng (NVR) chỉ xem được trong mạng LAN ở nhà | Không, không có cổng vào từ Internet | Cho một thiết bị ở nhà vào mạng riêng, rồi thiết bị ở nước ngoài đi vào mạng LAN ở nhà qua mạng riêng đó |
| Ứng dụng của hãng, nhưng bản trên kho ứng dụng nước ngoài là hệ thống riêng với máy chủ riêng | Tài khoản không khớp | Cài bản ứng dụng dành cho Trung Quốc và dùng tài khoản Trung Quốc |

## Trường hợp một: đám mây của hãng

Camera đẩy hình lên máy chủ của hãng, ứng dụng kéo hình về từ máy chủ. Đường từ mạng nước ngoài tới máy chủ của hãng Trung Quốc kém, biểu hiện là tải chậm và hình bị đứt. Chuyển sang IP Trung Quốc rồi thì bạn đi đường trong nội địa Trung Quốc, cải thiện rõ rệt.

Lưu ý ứng dụng cùng tên trên kho ứng dụng nước ngoài thường kết nối tới máy chủ ở nước ngoài, tài khoản không dùng lẫn được. Hãy cài bản ứng dụng dành cho Trung Quốc; vướng khu vực của kho ứng dụng thì xem [hướng dẫn cài đặt và khắc phục sự cố](../client/06-ios-app-store.md).

## Trường hợp hai: đầu ghi chỉ có trong mạng LAN

Đây là trường hợp phổ biến nhất và cũng khó nhất. NVR không có IP công cộng, còn băng thông rộng gia đình ở Trung Quốc thì phần lớn không mở cổng được. Cách làm được là dùng **mạng riêng**:

1. Để lại ở nhà một thiết bị luôn bật; máy tính, NAS, Raspberry Pi hay router được hỗ trợ đều được. Cài ứng dụng mạng riêng lên đó, đưa nó vào mạng riêng của bạn, và bật "chia sẻ mạng LAN".
2. Điện thoại hoặc máy tính ở nước ngoài cũng vào cùng mạng riêng đó.
3. Từ đó thiết bị ở nước ngoài truy cập thẳng NVR bằng địa chỉ LAN ở nhà, y như bạn đang ở nhà.

"Mạng riêng" của LeoTun chính là loại mạng riêng này. Một tài khoản cài trên bao nhiêu thiết bị cũng được, số thiết bị trực tuyến cùng lúc theo gói: Cá nhân 2 thiết bị, Gia đình 4 thiết bị, Doanh nghiệp 8 thiết bị. Một thiết bị ở nhà cộng vài thiết bị ở nước ngoài thì vừa khít gói Gia đình.

## Trường hợp ba: tài khoản không khớp

Thiết bị mua ở Trung Quốc được ràng buộc với tài khoản Trung Quốc, ứng dụng từ kho ứng dụng nước ngoài không đăng nhập vào được. Cách duy nhất là cài bản ứng dụng dành cho Trung Quốc. Đừng ràng buộc lại thiết bị, vì như vậy tài khoản của người nhà sẽ bị đá ra.

## Lưu ý về quyền riêng tư

Hình ảnh từ camera ở nhà chỉ nên đi lại giữa thiết bị của bạn và nhà bạn. Cách dùng mạng riêng ưu tiên kết nối trực tiếp giữa hai đầu, chỉ khi không nối thẳng được mới chuyển tiếp qua máy trung gian, và hình ảnh không được lưu trên máy chủ nào; còn cách dùng đám mây của hãng thì đi qua hãng. Dù cách nào cũng đừng dùng "công cụ xuyên mạng nội bộ" không rõ nguồn gốc, vì như thế chẳng khác gì giao camera nhà mình cho người khác.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=china-access-07) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=china-access-07) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
