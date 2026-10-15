# 09 · Cài Hiddify trên mọi nền tảng: Windows, macOS, Linux, Android, iOS

Ứng dụng dùng cho mục Hiddify của trang này là Hiddify mã nguồn mở, có sẵn lõi sing-box bên trong, nên cài xong không phải cấu hình gì thêm. Cả năm nền tảng dùng cùng một ứng dụng, nhưng trở ngại ở lần mở đầu tiên thì mỗi nơi một khác: trên Windows có thể bị phần mềm diệt virus chặn hoặc xóa, trên Mac có thể bị báo "bị hỏng" và còn phải cho phép tiện ích mở rộng mạng, trên Linux phải chạy một lệnh cấp quyền thì chế độ VPN mới chạy, còn trên iPhone thì không tìm thấy trong cửa hàng khu vực Trung Quốc. Bài này nói cho từng nền tảng: tải ở đâu, cài thế nào, lần mở đầu phải làm gì, và cuối bài là các bước ngắn nhất để nhập đăng ký và kết nối.

## Tải ở đâu

| Nền tảng | Bộ cài | Lấy ở đâu |
|---|---|---|
| Windows | Bộ cài (.exe), chỉ x64 | Khu tải xuống trên trang Hiddify |
| macOS | .dmg, một gói dùng chung cho cả chip Apple và Intel | Khu tải xuống trên trang Hiddify |
| Linux | .deb (họ Debian / Ubuntu), chỉ x64 | Khu tải xuống trên trang Hiddify |
| Android | .apk, có hai bản: ARM64 và x86-64 | Khu tải xuống trên trang Hiddify, hoặc Google Play |
| iPhone / iPad | Hiddify Proxy & VPN trên App Store | App Store; cần Apple ID ngoài khu vực Trung Quốc |

Khu tải xuống của trang Hiddify tự đề xuất gói cho hệ điều hành bạn đang dùng, gói cho các hệ khác liệt kê ở bên dưới. Cạnh mỗi dòng còn có biểu tượng "Trang chính thức" dẫn tới trang phát hành chính thức của Hiddify để bạn đối chiếu phiên bản. Ba hệ điều hành máy tính (Windows, macOS, Linux) còn có video hướng dẫn.

Bộ cài cho máy tính là bản sao nguyên vẹn từ gói phát hành chính thức của Hiddify, không sửa đổi hay đóng gói lại. Trước khi cho phép chạy, bạn có thể tự kiểm tra: tải bộ cài lên VirusTotal xem thử; cách làm xem [Khắc phục sự cố 06](../troubleshooting/06-antivirus-false-positive.md).

## Windows

1. Tải bộ cài từ khu tải xuống của trang Hiddify rồi nhấp đúp để cài. (Trong các lần thử gần đây của chúng tôi, Bảo mật Windows không báo gì; nếu phần mềm diệt virus bạn cài có báo, xem phần Câu hỏi thường gặp ở cuối [Khắc phục sự cố 06](../troubleshooting/06-antivirus-false-positive.md).)

## macOS

1. Tải file .dmg từ khu tải xuống của trang Hiddify, mở ra và kéo Hiddify vào "Ứng dụng".
2. Trong "Finder" → "Ứng dụng", giữ Control và bấm vào biểu tượng Hiddify, chọn "Mở", rồi bấm "Mở" lần nữa trong hộp thoại.
3. Nếu vẫn không mở được: "Cài đặt hệ thống" → "Quyền riêng tư & Bảo mật", bấm "Vẫn mở" trong phần "Bảo mật" và nhập mật khẩu để xác nhận.
4. Nếu bị báo "bị hỏng và không thể mở": file không hề hỏng, chỉ là Gatekeeper của hệ thống đang chặn. Mở "Terminal", chạy lệnh dưới đây, nhấn Return và nhập mật khẩu đăng nhập, rồi mở lại Hiddify:

```bash
sudo xattr -dr com.apple.quarantine /Applications/Hiddify.app
```

Lệnh này chỉ gỡ cờ cách ly đánh dấu file được tải từ mạng, và chỉ áp dụng cho đúng ứng dụng này. **Đừng** dùng `sudo spctl --master-disable` để tắt Gatekeeper cho cả máy.

Lần đầu bấm kết nối sau khi cài, hệ thống còn yêu cầu bạn cho phép một "tiện ích mở rộng mạng". Bỏ qua bước này thì biểu tượng cứ quay mãi và không bao giờ kết nối được:

- **macOS 15 Sequoia trở lên**: "Cài đặt hệ thống" → "Cài đặt chung" → "Mục đăng nhập & Tiện ích mở rộng", cuộn xuống "Tiện ích mở rộng" ở dưới cùng, đổi chế độ xem sang "Theo danh mục", bấm ⓘ cạnh "Tiện ích mở rộng mạng", bật công tắc của Hiddify, rồi nhập mật khẩu hoặc dùng vân tay khi được hỏi.
- **macOS 13 Ventura / 14 Sonoma**: mở Hiddify và bấm kết nối một lần trước, sẽ hiện thông báo "Đã chặn tiện ích mở rộng hệ thống"; sau đó vào "Cài đặt hệ thống" → "Quyền riêng tư & Bảo mật", cuộn xuống dòng "Phần mềm hệ thống từ nhà phát triển … đã bị chặn tải", bấm "Cho phép" và nhập mật khẩu.

Trên máy Mac do công ty cấp, nếu các nút này bị mờ thì chính sách quản lý thiết bị đã khóa chúng; hãy hỏi bộ phận IT, hoặc dùng ứng dụng Cisco, OpenVPN hay Mạng riêng thay thế.

## Linux

1. Tải file .deb từ khu tải xuống của trang Hiddify rồi nhấp đúp để cài bằng trung tâm phần mềm, hoặc mở terminal trong thư mục tải về và chạy (Debian, Ubuntu và các bản phái sinh):

```bash
sudo apt install ./downloaded-file-name.deb
```

2. Cài xong mà kết nối ngay sẽ báo "operation not permitted" và chế độ VPN không khởi động được, vì gói deb chính thức cài xong không có quyền này. Mở terminal, chạy lệnh dưới đây để cấp quyền cho Hiddify, rồi mở lại Hiddify:

```bash
echo /usr/share/hiddify/lib | sudo tee /etc/ld.so.conf.d/hiddify.conf && sudo ldconfig && sudo setcap cap_net_admin,cap_net_raw+ep /usr/share/hiddify/hiddify
```

3. **Mỗi lần nâng cấp Hiddify phải chạy lại**: quyền được gắn vào file chương trình, nâng cấp sẽ thay file nên quyền bị mất.

Gói deb là x64; trên thiết bị Linux ARM thì dùng OpenVPN, cùng tài khoản là được.

## Android

1. Tải file .apk từ khu tải xuống của trang Hiddify. Trang tự đề xuất kiến trúc hợp với điện thoại của bạn; đại đa số điện thoại là ARM64. Nếu dùng được Google Play thì cũng có thể cài thẳng từ cửa hàng.
2. Nếu khi cài hiện thông báo về "nguồn không xác định" hoặc cảnh báo từ phần mềm bảo mật, hãy cho phép.
3. Lần đầu bấm kết nối, hệ thống xin quyền VPN; bấm cho phép.

## iPhone / iPad

1. Tìm "Hiddify" trên App Store và cài; ứng dụng miễn phí.
2. Nếu không tìm thấy, hoặc gặp thông báo "Ứng dụng này hiện không có ở quốc gia hoặc vùng của bạn": trên iOS, hãy cài từ App Store bằng Apple ID không thuộc khu vực Trung Quốc (Hiddify có ở cửa hàng Hoa Kỳ, Hồng Kông, Đài Loan, Nhật Bản và Singapore). Chúng tôi khuyên đăng ký một Apple ID mới: trong App Store, bấm "Nhận" ở một ứng dụng miễn phí bất kỳ → "Tạo ID Apple mới", chọn khu vực như Hồng Kông hay Hoa Kỳ, phương thức thanh toán chọn "Không có". Bạn chỉ đổi tài khoản trong App Store, iCloud không bị ảnh hưởng. Các bước đầy đủ xem [06 · iOS không cho cài ứng dụng thì làm sao](06-ios-app-store.md).
3. Lần đầu bấm kết nối, hệ thống xin quyền VPN; bấm cho phép.

**Đừng** dùng Apple ID do người khác chia sẻ; họ có thể khóa thiết bị của bạn từ xa.

## Cài xong: nhập đăng ký và kết nối

1. Đăng nhập website và mở trang Hiddify.
2. Bấm lá cờ của khu vực bạn muốn, một mã QR sẽ hiện ra; hoặc bấm "Nhập tất cả khu vực · tự động chọn" ở đầu trang để nhập một lần mọi khu vực ngoài Trung Quốc và để ứng dụng tự chọn. **Khu vực Trung Quốc nhập riêng**: muốn xem video hay dùng ngân hàng trực tuyến Trung Quốc từ nước ngoài thì bấm lá cờ Trung Quốc để nhập.
3. Dưới mã QR có ba nút, chia theo loại đăng ký. Hiddify dùng nút đầu tiên (ghi Hiddify / sing-box / GUI.for.SingBox / Karing, dòng phụ là "Đăng ký sing-box"), trên điện thoại hay máy tính đều là nút đó. Điện thoại: bấm vào, rồi chuyển sang Hiddify và thêm theo hướng dẫn, hoặc dùng Hiddify trên thiết bị khác để quét mã. Máy tính: bấm vào để sao chép một địa chỉ https://, rồi trong Hiddify bấm "+" → "Add from clipboard" (thêm từ bộ nhớ tạm).
4. Bấm kết nối.

Ba nút khác nhau thế nào, cách nhập vào Clash và các ứng dụng khác, đăng ký có hết hạn không — xem [02 · Cách nhập link đăng ký (Hiddify, Clash, Shadowrocket)](02-singbox-subscription-links.md). Nhập rồi mà không kết nối được thì xem [Khắc phục sự cố 04](../troubleshooting/04-singbox-import-not-connecting.md).

## Câu hỏi thường gặp

**Các bạn có sửa bộ cài không?** Không. Bộ cài cho máy tính là bản sao nguyên vẹn từ gói phát hành chính thức của Hiddify. Mỗi dòng trên trang Hiddify đều có link tới trang phát hành chính thức để bạn tự đối chiếu phiên bản, và bạn cũng có thể tải file lên VirusTotal để kiểm tra thêm.


**Tôi đã chạy lệnh xattr trên Mac mà vẫn không kết nối được?** Nhiều khả năng "tiện ích mở rộng mạng" chưa được cho phép; làm theo phần macOS ở trên và bật công tắc của Hiddify trong Cài đặt hệ thống.

**Nâng cấp Hiddify trên Linux xong thì chế độ VPN lại không chạy?** Đúng là như vậy; nâng cấp xong hãy chạy lại lệnh cấp quyền một lần.

**Máy tính Windows hoặc Linux chạy ARM có dùng được không?** Được, bằng cách truy cập khác như OpenVPN, cùng tài khoản là dùng được; gói Hiddify cho máy tính hiện chỉ có x64.

**Không muốn mất công với các bước cho phép?** Cisco (Cisco Secure Client), OpenVPN (OpenVPN Connect) và Mạng riêng (Tailscale) đều nhấp đúp là mở; chúng không bị phần mềm diệt virus báo, Mac cũng không báo "bị hỏng", và vẫn dùng cùng một tài khoản.

## Đọc thêm

- [Trang Hiddify: tải ứng dụng và mã QR cho từng khu vực](https://www.leotun.com/vi/singbox?utm_source=github&utm_content=client-09)
- [Cách nhập link đăng ký (Hiddify, Clash, Shadowrocket)](https://www.leotun.com/vi/guides/singbox-subscription?utm_source=github&utm_content=client-09)
- [Ứng dụng bị phần mềm diệt virus báo / Mac báo bị hỏng: kiểm tra trước, rồi cho phép](https://www.leotun.com/vi/guides/antivirus-false-positive?utm_source=github&utm_content=client-09)
- [Cho phép "tiện ích mở rộng mạng" trên macOS là gì và làm thế nào](https://www.leotun.com/vi/guides/macos-network-extension?utm_source=github&utm_content=client-09)
- [iOS không cho cài ứng dụng thì làm sao](https://www.leotun.com/vi/guides/ios-app-store?utm_source=github&utm_content=client-09)

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=client-09) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=client-09) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 24 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
