# 08 · Cài firmware xong: những gì nó tự làm, và vài công tắc bạn nên biết

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/router-firmware?utm_source=github&utm_content=router-08

Sau khi cài firmware của trang này hoặc mua máy cài sẵn, việc duy nhất bạn phải làm là đăng nhập tài khoản trên trang quản trị. Bài này nói về những việc firmware **tự làm** và vài công tắc có thể bạn sẽ cần đụng tới; bắt đầu từ đầu thì xem [bài 01](01-plug-and-play-router.md), chia luồng xem [bài 03](03-router-split-routing.md), còn ràng buộc và thay router xem [bài 05](05-mac-binding-and-replacing.md).

## Những gì nó tự làm

| Việc gì | Hoạt động thế nào | Bạn cần làm gì |
|---|---|---|
| Cập nhật thành phần và danh sách chia luồng | Kiểm tra khi khởi động và tải bản cập nhật nếu có, **có hiệu lực từ lần khởi động sau**; danh sách trang bị chặn dùng cho chiều từ Trung Quốc ra nước ngoài cũng tự cập nhật mỗi ngày | Không cần gì; địa chỉ đường truyền thay đổi hay trang web mới thêm vào danh sách đều được nhận tự động |
| Mã quốc gia Wi‑Fi | Lên mạng xong thì nhận biết đang ở nước nào và tự đặt công suất phát, kênh sóng | Ngay sau khi cài firmware, **cắm dây mạng trước** để nó lên mạng một lần; trước khi lên mạng sóng yếu hơn là bình thường |
| Xử lý khi hết hạn | Tài khoản hết hạn thì ngừng đi qua VPN; mạng tại chỗ vẫn chạy như thường | Gia hạn xong tự hoạt động lại, không cần đăng nhập lại |
| Ràng buộc router | Lần đăng nhập đầu tiên ghi router này vào tài khoản | Hủy ràng buộc trên website trước khi đổi router |

Chỉ khi nâng cấp phiên bản lớn của cả firmware mới phải cài file sysupgrade. Mỗi năm chỉ vài lần, và website sẽ thông báo.

## Những gì có thể bạn cần đụng tới

- **Chế độ chia luồng**: Split routing (chia luồng, mặc định) / Global (toàn bộ) / Direct (đi thẳng). Nếu một trang web không mở được, hãy chuyển sang Global trước để kiểm tra: mở được ở Global nghĩa là nó chưa có trong danh sách, hãy gửi địa chỉ cho bộ phận hỗ trợ để thêm vào; ở Global cũng không mở được thì lỗi nằm ở chính trang web đó.
- **Khu vực**: chọn trên trang quản trị. Ở nước ngoài muốn xem nội dung Trung Quốc thì chọn khu vực Trung Quốc; ở Trung Quốc muốn vào dịch vụ nước ngoài thì chọn khu vực nước ngoài.
- **Blocked sites only** (chỉ trang bị chặn mới đi VPN): một ô đánh dấu trong "VPN settings" (cài đặt VPN), ở phần chia luồng thông minh, mặc định đã đánh dấu. Nó chỉ áp dụng cho chiều từ Trung Quốc ra nước ngoài (bạn ở Trung Quốc và chọn khu vực nước ngoài). Khi đánh dấu, chỉ các trang web và dịch vụ bị chặn mới đi qua VPN (dựa trên danh sách trang bị chặn tự cập nhật mỗi ngày, cộng thêm các dịch vụ kết nối tới địa chỉ cố định như Telegram); trang Trung Quốc và các trang nước ngoài vốn vào được từ Trung Quốc (trang của công ty nước ngoài, bản tải của Apple và Microsoft, nền tảng game, v.v.) kết nối thẳng, không đi vòng. Bỏ đánh dấu để quay về cách cũ: trang Trung Quốc đi thẳng, mọi thứ khác qua VPN. Nếu đang ở Trung Quốc mà một trang nước ngoài không mở được, hãy bỏ đánh dấu (hoặc tạm chuyển sang Global) rồi thử lại; mở được thì trang đó bị chặn nhưng chưa có trong danh sách, hãy gửi địa chỉ cho bộ phận hỗ trợ. Firmware cài trước tháng 10/2026 chưa hiện ô này (mặc định mới vẫn đã được áp dụng qua cập nhật tự động); muốn đổi thì liên hệ bộ phận hỗ trợ, họ làm từ xa được. Chiều từ nước ngoài về Trung Quốc không bị công tắc này ảnh hưởng.
- **Automatically select the fastest line** (tự chọn đường truyền nhanh nhất): nằm dưới mục khu vực, mặc định tắt, nên bật khi chất lượng mạng kém.

  | | Tắt (mặc định) | Bật |
  |---|---|---|
  | Dùng đường truyền nào | Luôn là khu vực bạn đã chọn | Tự chọn đường có độ trễ thấp nhất và ít mất gói trong các đường khả dụng, sau đó định kỳ đo lại và tự chuyển nếu chất lượng giảm |
  | Quốc gia lối ra | Khu vực đã chọn | Chọn khu vực Trung Quốc: chỉ chọn trong các đường ở Trung Quốc, lối ra vẫn ở Trung Quốc; chọn khu vực nước ngoài: chọn trong tất cả các đường nước ngoài, và **quốc gia lối ra có thể khác khu vực đã chọn** (ví dụ chọn Nhật Bản nhưng thực tế ra từ Singapore) |
  | Hợp với | Khi cần cố định quốc gia: xem dịch vụ phát trực tuyến của một nước cụ thể, ngân hàng và tài khoản nhạy cảm với khu vực | Mạng nhà không ổn định hoặc khu vực hay giật, khi bạn chỉ cần nhanh và không quan tâm ra từ nước nào |

  Khi bật tắt công tắc này, trang quản trị hiện "Switching automatic selection…" (đang chuyển chế độ tự chọn) và khóa trang cho tới khi chuyển xong. Trong lúc đó mạng rớt một chút, là chuyện bình thường. Mục "Current exit" (lối ra hiện tại) trên trang quản trị cho biết đường truyền nào đang thực sự được dùng.
- **Mật khẩu quản trị và mật khẩu Wi‑Fi**: giá trị xuất xưởng là mặc định công khai; hãy đổi ngay sau khi đăng nhập.

## TV, TV box và thiết bị của người lớn tuổi trong nhà

- Chỉ cần bắt Wi‑Fi của router này hoặc cắm dây là bản đại lục của ứng dụng phát được ngay; bản quốc tế (iQIYI, WeTV) có kho nội dung khác, hãy cài bản đại lục.
- Thiết bị đã kết nối mà không đi qua VPN, hoặc các trang bị chặn không mở được trong khi mọi thứ khác bình thường: nhiều khả năng nó tự đặt DNS riêng (Android "DNS riêng tư", DNS bảo mật của trình duyệt), nên router không thấy nó đang tra trang nào; hãy tắt đi.
- Muốn một thiết bị luôn kết nối thẳng (máy tính công việc cần kết nối VPN công ty): cho nó bắt Wi‑Fi của router phía trên hoặc của modem.

## Câu hỏi thường gặp

**Gói Cá nhân có dùng router được không?** Được. Cá nhân, Gia đình và Doanh nghiệp đều hỗ trợ router, không cần đổi gói.

**Router chiếm mấy suất thiết bị?** Một; các thiết bị phía sau nó không tính.

**Firmware có cửa hậu không?** Nó được biên dịch từ OpenWrt, chỉ thêm thành phần kết nối VPN và quy tắc chia luồng; VPN chỉ ghi lại thời lượng kết nối và tổng lưu lượng để tính phí.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-08) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-08) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, hiệu lực lâu dài
