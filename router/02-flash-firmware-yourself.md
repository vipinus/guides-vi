# 02 · Tự cài firmware: từ firmware gốc sang firmware của chúng tôi, từng bước (có video)

> Video hướng dẫn (khoảng hai phút rưỡi, thuyết minh tiếng Anh hoặc tiếng Trung): https://www.leotun.com/vi/video/router-flash?utm_source=github&utm_content=router-02
>
> Bản trên website: https://www.leotun.com/vi/guides/router-flash?utm_source=github&utm_content=router-02

Bài này dành cho người đã có sẵn router thuộc danh sách được hỗ trợ. Router của bạn vẫn đang chạy hệ thống gốc của hãng, và chúng ta sẽ đi từ lúc mở website tới lúc cả nhà lên mạng được — mỗi bước bấm vào đâu, sẽ thấy gì, và người ta hay vấp ở chỗ nào. Bản minh họa dùng GL.iNet GL-MT3000. Các dòng khác làm theo cùng các bước, chỉ có trang quản trị gốc trông khác. Nếu không muốn tự làm, mua router cài sẵn đỡ phiền hơn: xem [bài 01](01-plug-and-play-router.md). Nên chọn dòng nào thì xem [bài 07](07-which-router-to-buy.md).

## Trước khi bắt đầu

- **Kiểm tra dòng router của bạn có được hỗ trợ không.** Đăng nhập, mở mục **Router** và tìm dòng của bạn theo hãng. Phiên bản phần cứng sau tên dòng (v1, v2, v.v.) cũng phải khớp.
- **Tài khoản phải đang còn hạn.** Gói Cá nhân, Gia đình và Doanh nghiệp đều dùng được router.
- **Chuẩn bị sẵn một sợi dây mạng.** Cổng WAN của router nối vào modem hoặc router phía trên. Trong lúc cài, tốt nhất cũng nối máy tính với router bằng dây; ổn định hơn Wi-Fi.
- **Giữ lại một bản firmware gốc.** Tải firmware gốc cho dòng router của bạn từ trang của hãng, phòng khi muốn quay lại.

## Bước 1: Build firmware trên website

1. Đăng nhập và bấm **Router** trên thanh điều hướng.
2. Tìm dòng router của bạn và bấm **Firmware**, hoặc cuộn xuống phần "Build Firmware" rồi chọn dòng router trong danh sách theo hãng.
3. Bấm **Bắt đầu Build**.

Vài điều cần biết trước:

- **Mỗi lần build mất 3 đến 5 phút.** Firmware được làm riêng cho tài khoản của bạn ngay lúc đó, không phải file làm sẵn. Lúc đông người, lượt build có thể phải xếp hàng. Trang sẽ báo khi điều đó xảy ra — cứ đợi, không cần bấm lại.
- **Xong sẽ có email báo.** Mục trong "Build gần đây" chuyển thành "Hoàn tất", và hộp thư của bạn nhận được thông báo.
- **Ngôn ngữ giao diện của firmware theo ngôn ngữ website.** Nếu bạn dùng website bằng tiếng Việt thì trang quản trị router sẽ bằng tiếng Việt. Muốn ngôn ngữ khác thì đổi ngôn ngữ website trước rồi mới build.
- **Link tải có hiệu lực một ngày.** Hết hạn thì cứ build lại.

## Bước 2: Tải về và giải nén

1. Trong "Build gần đây", bấm **Tải xuống**. Bạn nhận được một file zip.
2. Mở thư mục Tải xuống và **giải nén** nó.
3. Thư mục giải nén ra có chứa file firmware.

Dùng file nào:

| Router của bạn đang chạy | Dùng file |
|---|---|
| Hệ thống gốc của GL.iNet (trường hợp trong video) | có đuôi `sysupgrade.bin` |
| Hệ thống gốc của hãng khác | có chữ `factory` trong tên |
| Đã chạy firmware của chúng tôi và đang nâng cấp | có chữ `sysupgrade` trong tên |

Nếu file zip chỉ có một file thì dùng đúng file đó.

> ⚠️ **Firmware này chỉ dành riêng cho bạn.** Nó mang thông tin tài khoản của bạn để router tự đăng nhập sau khi cài. Đừng gửi file cho ai khác hay chia sẻ công khai.

## Bước 3: Cài từ trang quản trị gốc

Lấy GL.iNet làm ví dụ:

1. Nối máy tính với router, mở trang quản trị gốc trong trình duyệt (`http://192.168.8.1` với GL.iNet) và đăng nhập bằng mật khẩu quản trị.
2. Ở menu bên trái, mở **System** → **Upgrade**.
3. Chuyển sang thẻ **Firmware Local Upgrade** (nâng cấp firmware từ máy).
4. Bấm vào vùng tải lên và chọn file firmware vừa giải nén.
5. Đợi tới khi phần kiểm tra hiện **Pass** (đạt).
6. **Tắt "Keep Settings"** (giữ cài đặt). Đây là bước người ta hay bỏ sót nhất. Hai hệ thống không dùng chung định dạng cấu hình, giữ cài đặt cũ sẽ gây đủ loại lỗi lạ.
7. Bấm **Install** (cài đặt).

Trang chuyển sang "Upgrading and rebooting…" (đang nâng cấp và khởi động lại) với một vòng tiến trình. **Mất hai đến ba phút. Trong lúc đó đừng rút điện router và đừng đóng trang.** Tiến trình chạy xong mà trang không tải tiếp là bình thường — router giờ đã chạy hệ thống khác, cả địa chỉ lẫn Wi-Fi đều đã đổi. Xem bước tiếp theo.

Hãng khác: tìm "Firmware Upgrade", "System Upgrade" hoặc "Local Upgrade" trong trang quản trị gốc, tải file lên, và cũng không giữ cài đặt.

## Bước 4: Bắt Wi-Fi mới

Cài xong, tên Wi-Fi cũ biến mất và một tên mới xuất hiện:

- **Tên Wi-Fi: `www.anyfq.com`**
- **Mật khẩu Wi-Fi: `www.anyfq.com`** (giống tên)

Máy tính và điện thoại phải **chuyển sang Wi-Fi này** mới lên mạng được hoặc mở được trang quản trị router. Máy tính nối dây với router thì không cần chuyển.

Địa chỉ trang quản trị mới là `http://192.168.11.1` (tự gõ cả phần `http://` ở đầu).

## Bước 5: Đợi nó tự kết nối

Không phải đăng nhập, không phải chọn khu vực. **Chỉ cần tài khoản còn hạn, router sẽ tự kết nối trong vòng 10 phút.** Khi đã kết nối, mọi thiết bị bắt Wi-Fi này đều tự động đi qua dịch vụ — kể cả TV, đầu thu và máy chơi game.

Muốn chắc là đã kết nối, hãy dùng một thiết bị đang bắt router mở một trang bình thường bạn không vào được, hoặc xem trạng thái trên trang quản trị.

## Hai việc nên làm sau đó

1. **Đổi mật khẩu mặc định.** Mật khẩu Wi-Fi và mật khẩu quản trị lúc xuất xưởng là mặc định công khai. Đổi cả hai trên trang quản trị.
2. **Sóng Wi-Fi yếu ngay sau khi cài là bình thường.** Router phải lên mạng một lần để biết mình đang ở khu vực nào rồi mới nâng công suất phát lên mức được phép ở đó. Cắm dây mạng và cho nó lên mạng trước.

## Thay router cũ bằng router mới

Mỗi lúc một tài khoản chỉ liên kết với một router. Nếu tài khoản của bạn đã từng dùng trên router khác:

1. Đăng nhập, mở mục **Router**, dưới tiêu đề "Build Firmware" bạn sẽ thấy dòng router **Đã liên kết**, bên cạnh là **Hủy liên kết**.
2. Bấm Hủy liên kết. Router cũ hỏng hay không có ở đó thì vẫn làm được.
3. Trên router mới không phải làm gì: nó **tự kết nối** và liên kết với tài khoản của bạn.

Nếu bạn cài router mới trước khi hủy liên kết thì cũng không sao. Router mới sẽ chờ và tự kết nối khi bạn hủy liên kết.

Quy tắc chi tiết xem [05 · Ràng buộc MAC và thay router](05-mac-binding-and-replacing.md).

## Nếu tài khoản hết hạn thì sao

Hết hạn rồi thì router ngừng đi qua dịch vụ, còn mạng nhà bạn vẫn chạy bình thường. **Gia hạn xong, router tự hoạt động lại — không cần đăng nhập lại, không cần cài lại.**

## Nó không tự kết nối — kiểm tra thế nào

Nếu sau chừng mười phút vẫn chưa được, hãy kiểm tra lần lượt:

1. **Bản thân đường mạng có chạy không?** Từ một thiết bị bắt router, mở một trang web bình thường bất kỳ. Không mở được thì lỗi nằm ở dây hoặc modem: kiểm tra dây ở cổng WAN đã cắm chặt chưa.
2. **Tài khoản có hết hạn không?** Đăng nhập website xem ngày hết hạn. Gia hạn xong thì đợi vài phút.
3. **Tài khoản có còn liên kết với router cũ không?** Trong mục Router, xem dòng router đã liên kết. Không phải router này thì bấm Hủy liên kết.
4. **Khởi động lại router một lần.** Rút điện, đợi mười giây, cắm lại và chờ hai đến ba phút.
5. **Đăng nhập thủ công.** Mở `http://192.168.11.1` và đăng nhập router với tên người dùng `root`, mật khẩu `www.anyfq.com`. Sau đó vào **Services** → **VPN**, nhập email và mật khẩu tài khoản rồi lưu.

Vẫn không được? Hỏi trong nhóm, cho chúng tôi biết dòng router và bạn đã làm tới bước nào trong danh sách trên.

## Khi nào không nên tự cài

Dòng router không có trong danh sách, phiên bản phần cứng không khớp, hoặc là router đời cũ không có chế độ khôi phục. Ba trường hợp này mua router cài sẵn đỡ phiền hơn.

## Nếu cài bị lỗi

Đa số router có chế độ khôi phục: rút điện, giữ nút reset trong lúc cắm điện lại, giữ thêm vài giây, rồi nối máy tính bằng dây và tải firmware gốc lên theo hướng dẫn của hãng. Với GL.iNet, tìm "uboot" trong tài liệu của hãng. Bản firmware gốc bạn giữ lại từ trước là để dùng vào lúc này.

## Câu hỏi thường gặp

**Cài firmware có mất bảo hành không?** Tùy hãng. Router GL.iNet vốn được xây trên hệ thống mã nguồn mở và có thể cài lại firmware gốc.

**Có quay lại firmware gốc được không?** Được. Dùng chế độ khôi phục trong phần "Nếu cài bị lỗi" để tải firmware gốc lên.

**Một file firmware dùng cho hai router được không?** Không. Firmware được build theo tài khoản, và mỗi lúc một tài khoản chỉ liên kết với một router.

**Đổi tài khoản có phải build lại không?** Không. Đăng xuất trên trang quản trị rồi đăng nhập bằng tài khoản mới.

**Sau này cập nhật có phải cài lại không?** Các bản cập nhật thường xuyên router tự nhận; bạn không phải làm gì. Chỉ khi lên phiên bản lớn mới cần build mới và cài file sysupgrade một lần, và website sẽ thông báo khi tới lúc đó.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-02) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-02) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, hiệu lực lâu dài
