# 12 · Mất điện hay rớt mạng xong router có tự khôi phục không?

Ai từng tự dựng router VPN có lẽ đều đã gặp cảnh này: một lần mất điện, hay mạng cáp chập chờn trong chốc lát, khởi động lại xong mọi thứ trông vẫn ổn nhưng đường hầm không bao giờ tự lên lại, cho tới khi bạn vào trang quản trị cấu hình lại từ đầu.

## Trả lời ngắn

Có, router tự khôi phục. Sau khi mất điện rồi khởi động lại, mạng cáp rớt rồi có lại, hay đường hầm đứt giữa chừng, firmware đều tự kết nối lại. Không phải vào trang quản trị, không phải đăng nhập lại.

## Nó làm thế nào

Firmware chạy liên tục một trình kiểm tra, cứ khoảng nửa phút lại xem đường hầm một lần. Thấy đường hầm đứt, nó kết nối lại và khôi phục luôn chế độ chia luồng.

Trong khoảng ngắn trước khi đường hầm lên lại, các trang Trung Quốc vẫn dùng bình thường. Cả nhà không bị mất mạng chỉ vì đường hầm chưa lên.

Cài đặt của bạn cũng được nhớ: khu vực, chế độ chia luồng và công tắc "Automatically pick the fastest line" (tự chọn đường truyền nhanh nhất) đều giữ nguyên sau khi khởi động lại hay kết nối lại. Nếu bạn đã tắt chia luồng thì nó vẫn tắt.

## Từng trường hợp sẽ ra sao

| Chuyện gì xảy ra | Sau đó |
|---|---|
| Có điện lại sau khi mất điện | Router khởi động và đường hầm tự kết nối lại |
| Mạng cáp rớt rồi có lại | Đường hầm kết nối lại ngay khi đường dây có lại |
| Đường hầm đứt giữa chừng | Trình kiểm tra phát hiện và kết nối lại |
| Tài khoản hết hạn | Lưu lượng thôi đi qua đường hầm, mạng trong nhà vẫn chạy. Gia hạn xong thì tự khôi phục, không phải đăng nhập lại |
| Chúng tôi đổi địa chỉ máy chủ | Router tự cập nhật theo. Không phải cấu hình lại gì |

## Vài phút rồi vẫn chưa lên? Kiểm tra mấy điều này

1. **Bản thân mạng cáp có chạy không?** Mở một trang Trung Quốc. Nếu không được thì vấn đề nằm ở đường dây hoặc modem, không phải ở đường hầm.
2. **Tài khoản đã hết hạn chưa?** Hết hạn thì đường hầm không kết nối. Đăng nhập website để kiểm tra.
3. **Thử khu vực khác.** Đổi khu vực trong trang quản trị. Đôi khi một khu vực có trục trặc tạm thời.
4. **Khởi động lại router.** Rút điện, đợi mười giây rồi cắm lại.
5. Vẫn không được thì gửi cho bộ phận hỗ trợ ảnh chụp màn hình phần trạng thái trong trang quản trị.

## Lần khởi động đầu tiên sau khi cài firmware

Lần khởi động đầu tiên chậm hơn bình thường: firmware kiểm tra cập nhật thành phần và dò quốc gia để đặt công suất phát sóng. **Lần khởi động đầu tiên đó hãy cắm dây mạng.** Wi-Fi yếu trước khi router lên mạng được một lần là chuyện bình thường.

## Câu hỏi thường gặp

**Nơi hay mất điện có dùng được không?** Được. Mỗi lần có điện lại nó đều tự kết nối lại.

**Có cần hẹn giờ khởi động lại router không?** Không cần.

**Cập nhật thành phần có làm gián đoạn kết nối không?** Không. Bản cập nhật được kiểm tra và tải về lúc khởi động, có hiệu lực ở lần khởi động sau. Router sẽ không tự khởi động lại khi bạn đang dùng.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-12) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-12) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 20 ngày gói Cá nhân, ưu đãi áp dụng lâu dài
