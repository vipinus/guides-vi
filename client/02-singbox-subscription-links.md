# 02 · Cách nhập link đăng ký (Hiddify, Clash, Shadowrocket)

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/singbox-subscription?utm_source=github&utm_content=client-02

"Link đăng ký" (subscription) mà nhà cung cấp proxy đưa cho bạn thực chất chỉ là một địa chỉ HTTPS, từ đó ứng dụng tải về một cấu hình đầy đủ: máy chủ, cổng và thông tin đăng nhập đều nằm sẵn trong đó, không phải gõ tay gì. Trang Hiddify của LeoTun cũng đưa bạn đúng loại này, và đưa thẳng ba định dạng, nên Hiddify, Clash và Shadowrocket mỗi bên lấy đúng phần của mình, không cần chuyển đổi gì.

## Ba nút trong cửa sổ bật lên

Đăng nhập website → trang Hiddify → bấm lá cờ của một khu vực. Một mã QR hiện ra, bên dưới có ba nút. Các nút được chia **theo loại link đăng ký**, không theo hệ điều hành, nên điện thoại và máy tính đều thấy cùng một bộ:

| Ứng dụng ghi trên nút | Dòng phụ | Bấm vào thì sao chép gì |
|---|---|---|
| Hiddify / sing-box / GUI.for.SingBox / Karing | Đăng ký sing-box | Trên điện thoại là link nhập `sing-box://import-remote-profile?url=…`, mở thẳng ứng dụng; trên máy tính là URL cấu hình `https://…` thuần, để dán. Cấu hình đã có sẵn quy tắc định tuyến và quy tắc từ chối IPv6, nên không cần bọc thêm "mẫu link đăng ký" nào |
| Clash Meta / Clash Verge / FlClash / Stash / Mihomo Party / Clash Nyanpasu / ClashX Meta / OpenClash | Đăng ký Clash | URL đăng ký định dạng Clash (YAML), dán vào danh sách đăng ký / hồ sơ của ứng dụng |
| NekoBox / Shadowrocket / v2rayN / v2rayNG / Streisand / V2Box / Loon / Egern / Husi / NekoRay / Pharos Pro / Bedlam / Furious / daed / Lumen KVN / Kitty Pro | Liên kết chia sẻ | Một dòng `hysteria2://…`, chỉ chứa node, không có quy tắc định tuyến |

- Tên ứng dụng dài quá một dòng thì sẽ chạy vòng; đó là bình thường.
- **Bấm một nút thì mã QR phía trên cũng đổi sang loại đó**, để ứng dụng tương ứng quét. Lúc cửa sổ mới mở, mã QR là loại Hiddify / sing-box, ứng dụng khác quét thẳng sẽ báo "Invalid QR code" (mã QR không hợp lệ): hãy bấm nút của ứng dụng bạn dùng trước, rồi mới quét hoặc dán.
- Cửa sổ "Nhập tất cả khu vực · tự động chọn" ở đầu trang chỉ có hai nút đầu, không có liên kết chia sẻ.

**Chuyển đổi link đăng ký** (subscription conversion): các trang web bên thứ ba đổi định dạng này sang định dạng khác. LeoTun đưa thẳng cả ba định dạng, nên **không cần chuyển đổi**; đưa một link có chứa thông tin đăng nhập của bạn cho trang chuyển đổi chẳng khác gì giao tài khoản cho bên thứ ba, nên đừng làm vậy.

## Nhóm Hiddify / sing-box: nút thứ nhất

1. Cài Hiddify (Android: trang tải xuống của website hoặc Google Play; iOS: App Store; ứng dụng máy tính dùng cho Windows / macOS / Linux). Lõi sing-box đã có sẵn bên trong.
2. Bấm lá cờ của một khu vực, mã QR hiện ra.
3. Điện thoại: chạm nút thứ nhất rồi chuyển sang Hiddify, ứng dụng sẽ đề nghị thêm từ bộ nhớ tạm; hoặc dùng "Scan QR code" (quét mã QR) trong Hiddify trên một thiết bị khác. Máy tính: bấm cùng nút đó, nó sao chép một địa chỉ https://, rồi trong Hiddify chọn "+" → "Add from clipboard" (thêm từ bộ nhớ tạm) và lưu.
4. Chạm kết nối, lần đầu thì cho phép quyền VPN. Muốn thêm khu vực thì bấm lá cờ khác; mỗi khu vực là một hồ sơ riêng.

## Nhóm Clash: nút thứ hai

Với Clash Meta (mihomo), Clash Verge, FlClash, Stash và các ứng dụng tương tự, bấm nút "Đăng ký Clash" rồi dán URL vừa sao chép vào danh sách đăng ký / hồ sơ của ứng dụng. Không cần công cụ chuyển đổi link đăng ký.

**Ứng dụng nhóm Clash không được dùng liên kết chia sẻ**: chúng không nhập được một dòng `hysteria2://` đơn lẻ thành hồ sơ.

## Các ứng dụng khác: nút thứ ba

Bấm nút "Liên kết chia sẻ", rồi dùng "Import from clipboard" (nhập từ bộ nhớ tạm) trong NekoBox / Shadowrocket / v2rayN / v2rayNG…, hoặc bấm nút xong thì quét mã QR phía trên. Liên kết chia sẻ không mang quy tắc nào, nên bạn phải tự thiết lập định tuyến và IPv6: nếu bạn ở nước ngoài và muốn xem nội dung từ Trung Quốc, hãy cho tên miền Trung Quốc đi qua node và tắt IPv6.

Các ứng dụng ghi trên nút sau v2rayN đều hỗ trợ hysteria2, nhưng liên kết chia sẻ dùng định dạng hysteria2 mở rộng mà vài ứng dụng không đọc được; nếu nhập thất bại hoặc không kết nối được, hãy chuyển sang Hiddify.

## Những ứng dụng không dùng được

| Ứng dụng | Lý do |
|---|---|
| Surge | Hỗ trợ hysteria2 nhưng chỉ đọc định dạng cấu hình riêng của nó, nên không loại nào trong ba loại dùng được |
| Quantumult X | Không hỗ trợ loại đường truyền này |
| Clash bản gốc, Clash for Windows | Lõi không có hysteria2; hãy dùng ứng dụng chạy lõi mihomo |

## Link đăng ký có hết hạn không?

- **Không hết hạn theo thời gian.** Token trong URL đăng ký gắn với tài khoản của bạn và còn dùng được chừng nào tài khoản còn hiệu lực; gia hạn hay đổi gói đều không phải nhập lại.
- **Đổi mật khẩu thì URL cũ mất hiệu lực ngay.** Đây là cách thu hồi quyền truy cập khi mất điện thoại hoặc lộ link; đổi xong thì quét mã lại.
- **Sau khi tài khoản hết hạn** URL trả về 401; gia hạn xong thì hồ sơ hiện có không phải thay.
- **Hồ sơ nhập trước tháng 9 năm 2026** thiếu quy tắc từ chối IPv6; hãy xóa đi và nhập lại.

Nếu đã nhập mà không kết nối được, xem [Khắc phục sự cố 04](../troubleshooting/04-singbox-import-not-connecting.md).

## Câu hỏi thường gặp

**Link đăng ký Hiddify và link đăng ký Clash khác nhau thế nào?** Khác định dạng (JSON và YAML), mỗi ứng dụng không nhận link đăng ký của bên kia, nhưng bản thân các node thì dùng được với cả hai. LeoTun đưa thẳng cả hai: ứng dụng nhóm Clash bấm nút "Đăng ký Clash" và không được dùng liên kết chia sẻ.

**Một hồ sơ chứa được mọi khu vực không?** Nhập từ lá cờ thì mỗi khu vực là một hồ sơ, bạn chuyển qua lại trong danh sách hồ sơ của ứng dụng; như vậy khi một khu vực đổi địa chỉ thì chỉ khu vực đó bị ảnh hưởng. Muốn nhập một lần mọi khu vực ngoài Trung Quốc và để ứng dụng tự chọn, bấm "Nhập tất cả khu vực · tự động chọn" ở đầu trang (chỉ có hai nút Đăng ký sing-box và Đăng ký Clash).

**Gửi mã QR cho người nhà được không?** Mã QR chứa thông tin tài khoản của bạn; gửi cho ai là người đó có tài khoản của bạn. Chia sẻ với người nhà thì được (số thiết bị cùng lúc theo gói: Cá nhân 2, Gia đình 4, Doanh nghiệp 8), nhưng đừng đăng ở nơi công khai; nếu bị lộ, đổi mật khẩu là nó hết tác dụng.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=client-02) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=client-02) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
