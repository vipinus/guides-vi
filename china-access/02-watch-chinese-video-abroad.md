# 02 · Xem video Trung Quốc khi ở nước ngoài

> Bản trên website (đầy đủ hơn): https://www.leotun.com/vi/guides/overseas-video?utm_source=github&utm_content=china-access-02

## Vì sao không xem được

Các nền tảng chỉ mua bản quyền cho Trung Quốc đại lục, IP nước ngoài bị chặn hết. Đây không phải lỗi kỹ thuật, và đổi IP là cách duy nhất.

## Khác nhau giữa các nền tảng

| Nền tảng | Bản web | Ứng dụng | Ghi chú |
|---|---|---|---|
| iQIYI | Đổi IP là được | Đổi IP là được | Bản quốc tế iQIYI là một ứng dụng khác, ít nội dung hơn; đừng cài nhầm |
| Tencent Video | Đổi IP là được | Đổi IP là được | Bản quốc tế WeTV cũng vậy |
| Youku | Đổi IP là được | Đổi IP là được | |
| Mango TV | Đổi IP là được | Đổi IP là được | |
| Bilibili | Phần lớn nội dung xem được dù không đổi IP | Như trên | Chỉ một số bộ anime và phim tài liệu bị giới hạn khu vực |
| Yangshipin / CCTV | Đổi IP là được | Như trên | Kênh trực tiếp nhạy cảm với IP nhất |

**Cái bẫy ứng dụng bản quốc tế**: tìm tên tiếng Trung của iQIYI trên kho ứng dụng nước ngoài thường sẽ ra bản quốc tế của iQIYI, kho nội dung hoàn toàn khác. Muốn xem kho nội dung Trung Quốc thì phải cài bản ứng dụng dành cho Trung Quốc; iPhone cần Apple ID khu vực Trung Quốc, Android thì cài thẳng file APK được.

## Đã kết nối mà vẫn bị báo giới hạn bản quyền

Nếu IP lối ra đã là Trung Quốc đại lục mà trang vẫn báo giới hạn bản quyền, thì mười lần có chín lần là **IPv6 hoặc DNS tại chỗ** của thiết bị đang đi vòng qua đường truyền. Từ tháng 9/2026, ba cách kết nối toàn thiết bị của LeoTun đều chặn IPv6 từ phía đường truyền; cấu hình Hiddify nhập trước tháng 9 cần xóa đi và quét mã QR nhập lại. Các bước dò lỗi xem [IPv6 và DNS là chỗ bị lọt](../troubleshooting/03-ipv6-and-dns-leak.md).

## Xem trên TV

TV và đầu thu không cài được ứng dụng, nên có hai cách:

1. **Dùng router**: thiết lập đường truyền về Trung Quốc trên router và bật chia luồng, TV bắt Wi-Fi đó là xem được. Cả nhà đều được hưởng; xem [Cho ông bà, bố mẹ và chiếc TV trong nhà](../router/04-family-tv-and-router.md).
2. **Truyền màn hình**: bật đường truyền về Trung Quốc trên điện thoại rồi truyền lên TV. Đơn giản, nhưng điện thoại phải bật suốt.

## Chất lượng hình

1080p cần ổn định từ 5 Mbps trở lên. Nếu giờ cao điểm buổi tối bị giật, hãy chọn khu vực đang đèn xanh hoặc đổi cách kết nối; vẫn giật thì nguyên nhân thường nằm ở băng thông rộng tại chỗ. Chọn điểm vào gần bạn và có đường tối ưu về đại lục hiệu quả hơn là đổi nền tảng.

---
Biên soạn bởi nhóm [LeoTun](https://www.leotun.com/vi?utm_source=github&utm_content=china-access-02) · Có thắc mắc? Xem [trang liên hệ](https://www.leotun.com/vi/contact?utm_source=github&utm_content=china-access-02) (nhóm chat, email và hỗ trợ đều có ở đó) · Đăng ký để dùng thử miễn phí 4 giờ; mời một người bạn trả phí thì mỗi người nhận 15 điểm (khoảng 15 ngày gói Cá nhân), ưu đãi áp dụng lâu dài
