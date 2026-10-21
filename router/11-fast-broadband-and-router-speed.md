# 11 · Băng thông rộng 1 Gbps hay 2 Gbps cắm router: tốc độ do đâu quyết định

Băng thông rộng gia đình ngày càng nhanh, nên câu hỏi này được hỏi rất nhiều: mạng nhà tôi 1 Gbps, thậm chí 2 Gbps, vậy qua router VPN thì tôi được bao nhiêu?

## Trả lời ngắn gọn

Với lưu lượng đi qua đường hầm, tốc độ do chặng ra khỏi Trung Quốc quyết định. **Điểm nghẽn không phải mạng nhà bạn, mà là chặng ra khỏi Trung Quốc.** Chúng tôi cam kết xem YouTube mượt. Tốc độ cụ thể tùy vào các yếu tố bên dưới.

Lưu lượng tới dịch vụ Trung Quốc không đi qua đường hầm và vẫn chạy hết tốc độ băng thông rộng của bạn. Xem [10 · NAS, máy in và camera có bị ảnh hưởng không?](10-nas-printer-camera-behind-router.md)

## Bốn yếu tố quyết định tốc độ

**1. Chặng qua biên giới**
Băng thông quốc tế là của chung mọi người, không liên quan gói cước nhà bạn nhanh đến đâu. 8 đến 11 giờ tối giờ Bắc Kinh là giờ cao điểm toàn quốc; khung giờ đó hãy chọn khu vực đang đèn xanh. Vẫn chậm thì nguyên nhân thường nằm ở băng thông rộng tại chỗ (mạng dùng chung của khu chung cư, hoặc nhà mạng và khu vực không hợp nhau; xem điểm tiếp theo). Xem [Vì sao lúc nhanh lúc chậm](../network/06-why-sometimes-fast-sometimes-slow.md).

**2. Nhà mạng của bạn và khu vực bạn chọn**
Mỗi nhà mạng ra khỏi Trung Quốc bằng một đường khác nhau, chọn đúng khu vực quan trọng hơn mọi thứ khác:
- China Unicom ở miền Bắc: thử Nhật Bản và Hàn Quốc trước
- China Telecom ở miền Nam: thử Đông Nam Á trước
- Nhà mạng khác: thử các khu vực trung chuyển qua Trung Quốc trước

**3. Bản thân router**
Lưu lượng phải được mã hóa trước khi vào đường hầm, và đó là việc của bộ xử lý trong router. Các mẫu chênh nhau nhiều:
- GL-MT300N-V2 (mini): cổng 100 Mbps. Đủ xem 1080p trên điện thoại hoặc laptop, không xứng với mạng tốc độ cao
- GL-MT3000 (di động): đủ cho gia đình nhỏ. Router đầu tiên hợp với đa số người
- GL-MT6000 (để bàn): cổng 2.5G. Cho nhiều thiết bị, 4K và máy chơi game

Mạng nhanh và nhà đông người dùng thì chọn MT3000 hoặc MT6000, đừng chọn mẫu mini.

**4. Vài mét cuối cùng trong nhà**
TV và máy tính để bàn thì cắm dây được chỗ nào hay chỗ đó. Wi-Fi trong chung cư đông đúc bị nhiễu nặng, và rất nhiều trường hợp "đường truyền chậm" hóa ra nằm ngay trong nhà.

## Thấy chậm thì thử lần lượt

1. Đổi khu vực. Thử hai ba khu vực, tìm cái giữ được tốc độ vào giờ này.
2. Bật "Automatically pick the fastest line" (tự chọn đường nhanh nhất) trên trang quản trị. Nó chọn đường có độ trễ và mất gói thấp nhất, và tự đổi khi tình hình thay đổi. Lưu ý khi đó quốc gia lối ra có thể khác khu vực bạn đã chọn.
3. Cắm dây mạng cho thiết bị bạn dùng xem video.
4. Xem có phải chỉ riêng trang này không. Nếu cùng lúc đó trang khác vẫn nhanh thì trang chậm là do phía bên kia.

## Biết trước khi mua thế nào

Đăng ký và nhận 4 giờ dùng thử miễn phí, không cần thẻ tín dụng. Kết nối vào khung giờ bạn hay dùng nhất, chẳng hạn buổi tối, và xem một video YouTube chất lượng HD. Những gì bạn thấy trên điện thoại hay laptop gần với những gì router sẽ cho bạn. Sau đó hãy quyết định chuyện router.

## Câu hỏi thường gặp

**Sao không nói luôn là bao nhiêu Mbps?** Vì con số khác nhau với mỗi người và mỗi giờ. Chúng tôi cam kết xem YouTube mượt, kể cả giờ cao điểm buổi tối, với điều kiện băng thông rộng của bạn tốt: China Unicom ở miền Bắc hoặc China Telecom ở miền Nam Trung Quốc. Ngoại lệ là băng thông rộng dùng chung của khu chung cư (loại mạng do ban quản lý khu dân cư chia lại). Nhận 4 giờ dùng thử miễn phí và tự thử một lần là cách đo chính xác nhất.

**Trang đo tốc độ báo con số thấp mà video vẫn xem mượt?** Chuyện bình thường. Máy chủ đo tốc độ cũng có lúc bận lúc rảnh, hai lần đo cách nhau một phút có thể chênh gấp đôi. Hãy đánh giá bằng chính việc bạn muốn làm.

**Router đắt hơn có nhanh hơn không?** Chỉ khi router là điểm nghẽn, chẳng hạn mẫu mini trên mạng tốc độ cao. Khi điểm nghẽn là chặng qua biên giới thì đổi router chẳng ích gì, đổi khu vực mới có tác dụng.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=router-11) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=router-11) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
