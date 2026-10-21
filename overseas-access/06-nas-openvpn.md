# 06 · Cho NAS Synology hoặc QNAP đi qua đường truyền thế nào

NAS là thiết bị trong nhà cần đường truyền nhất mà lại ít được để ý nhất: trình tải xuống cần tới tài nguyên nước ngoài, Docker cần kéo image, Cloud Sync cần đồng bộ ổ đám mây nước ngoài, Plex cần lấy metadata. NAS không chạy được Hiddify, nhưng Synology và QNAP đều có sẵn ứng dụng OpenVPN — tải file .ovpn từ trang OpenVPN của trang này, nhập vào là kết nối, khởi động lại cũng tự kết nối lại. Bài này nói về chỗ nhập cấu hình trên Synology và QNAP, tùy chọn then chốt "Use default gateway" (dùng cổng mặc định), phải làm gì sau khi đổi mật khẩu, và vì sao "truy cập NAS từ bên ngoài" là chuyện khác, cần dùng Mạng riêng.

## Trước hết, phân biệt hai việc

Cho chính NAS đi qua đường truyền (tải xuống, kéo image, đồng bộ ổ đám mây nước ngoài): dùng OpenVPN, là nội dung của bài này.

Truy cập NAS từ bên ngoài (mở thư mục chia sẻ khi đi công tác, xem camera): dùng Mạng riêng (Tailscale), đưa NAS và điện thoại của bạn vào cùng một mạng riêng; xem "Xem camera và NAS ở nhà bên Trung Quốc khi đang ở nước ngoài". Việc này hãy để Mạng riêng lo — OpenVPN nối NAS vào đường truyền của chúng tôi, còn Mạng riêng nối bạn vào nhà mình.

## Synology

1. Đăng nhập trang này, trên trang OpenVPN bấm vào lá cờ của một khu vực để tải file .ovpn của khu vực đó.
2. Control Panel → Network → Network Interface → Create → Create VPN profile → OpenVPN (via importing a .ovpn file), rồi nhập email và mật khẩu tài khoản của trang này.
3. "Use default gateway" (dùng cổng mặc định): đánh dấu thì toàn bộ lưu lượng đi ra của NAS đều qua đường truyền (tải xuống, Docker và Cloud Sync đều được hưởng); không đánh dấu thì chỉ dựng đường hầm, lưu lượng đi ra vẫn ra tại chỗ. Trong đại đa số trường hợp nên đánh dấu.
4. Đánh dấu "Reconnect when the VPN connection is lost" (kết nối lại khi mất kết nối VPN) để NAS khởi động lại hay đường truyền chập chờn thì tự khôi phục. Kết nối, rồi thử kéo một lần trong một gói ứng dụng.

## QNAP

1. Tải file .ovpn theo cách tương tự.
2. QVPN Service → VPN Client → Add → OpenVPN, nhập file, điền tài khoản và mật khẩu.
3. Trong phần cài đặt kết nối, đánh dấu "Use VPN as the default gateway of the NAS" (dùng VPN làm cổng mặc định của NAS) và tự động kết nối lại, rồi kết nối.

## Lưu lượng nào đi qua, lưu lượng nào không

- Đi qua: tác vụ BT và HTTP trong Download Station / Download Station, kéo image Docker, Cloud Sync đồng bộ Google Drive / Dropbox / OneDrive, lấy metadata của Plex và Emby, cập nhật từ Package Center.
- Không đi qua: lưu lượng khi bạn truy cập NAS trong mạng LAN — nó vốn nằm trong LAN nên không bị ảnh hưởng.
- Bạn ở Trung Quốc và muốn trang Trung Quốc kết nối thẳng: NAS không có script chia luồng, OpenVPN kết nối xong thì toàn bộ lưu lượng đi ra của NAS đều qua đường truyền. Nếu nguồn tải ở Trung Quốc chậm, hãy dùng địa chỉ mirror trong Trung Quốc cho tác vụ tải, hoặc chỉ kết nối đường truyền khi cần.

## Những điều cần biết

- File cấu hình gắn với tài khoản của bạn, đổi mật khẩu thì ô mật khẩu trên NAS hết tác dụng: tải lại file .ovpn để thay, hoặc chỉ sửa mật khẩu trong VPN profile.
- Tài khoản hết hạn thì NAS bị ngắt; gia hạn xong nó tự kết nối lại, không phải thay cấu hình.
- NAS tính là một thiết bị, dùng chung hạn mức trực tuyến cùng lúc với các thiết bị khác (Cá nhân 2 thiết bị, Gia đình 4 thiết bị, Doanh nghiệp 8 thiết bị).
- Đường truyền chạy trên UDP; NAS dùng băng thông rộng gia đình hầu như không bao giờ gặp chuyện UDP bị hạn chế.

## Câu hỏi thường gặp

**Đánh dấu "Use default gateway" rồi thì trong LAN có còn vào NAS được không?** Được. Lưu lượng trong LAN không đi qua cổng mặc định; thư mục chia sẻ, phát Plex và trang quản trị đều không bị ảnh hưởng.

**NAS đi qua đường truyền xong thì Plex phát từ xa chậm hơn?** Plex phát từ xa dùng lưu lượng đi ra của NAS, nên khi đã đánh dấu cổng mặc định thì nó đi vòng qua đường truyền. Muốn phát từ xa thì truy cập NAS qua Mạng riêng trực tiếp hơn; hoặc chỉ kết nối OpenVPN khi cần tải.

**Có thể chỉ cho Download Station đi qua đường truyền không?** Synology và QNAP không có chia luồng theo từng ứng dụng. Muốn kiểm soát chi tiết thì chạy trong Docker một container tải xuống có kèm OpenVPN (ví dụ qbittorrent + gluetun) và chỉ cho container đó đi qua đường truyền.

**NAS chạy hệ thống Linux (TrueNAS, Unraid) thì sao?** Làm theo cách của Linux: gói openvpn cộng file cấu hình đặt trong /etc/openvpn/client/; xem "Cho máy chủ Linux và công cụ dòng lệnh đi qua đường truyền thế nào".

## Đọc thêm

- [Trang OpenVPN: tải ứng dụng và file cấu hình](https://www.leotun.com/vi/openvpn?utm_source=github&utm_content=overseas-access-06)
- [Cách dùng OpenVPN và khi nào nên chọn nó](https://www.leotun.com/vi/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-06)
- [Xem camera và NAS ở nhà bên Trung Quốc khi đang ở nước ngoài](https://www.leotun.com/vi/guides/home-camera?utm_source=github&utm_content=overseas-access-06)
- [Cho máy chủ Linux và công cụ dòng lệnh đi qua đường truyền thế nào](https://www.leotun.com/vi/guides/linux-server?utm_source=github&utm_content=overseas-access-06)

Bản trên website của bài này (có cả tiếng Việt): https://www.leotun.com/vi/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-06

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=overseas-access-06) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=overseas-access-06) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
