# BÀI LÀM PHA 1 – HACKATHON 02

- **Mã đề:** 02
- **Họ tên: Phạm Hồ Nam Khánh
- **Lớp: CNTT4
- **Link repository Pha1:**

> Pha 1 (70 phút đầu, KHÔNG dùng AI). Viết xong, kéo thả file này vào repository Pha1 trước mốc giờ giám thị công bố.

## 4.1. Bảo vệ dữ liệu và chống ảo giác

### a) Ghi chú đã ẩn danh hoá

**GHI CHU DA AN DANH**

```text
Khách hàng [TEN_KHACH],số điện thoại [SO_DIEN_THOAI], số CCCD[SO_CAN_CUOC],email[EMAIL_KHACH], đăng kí gói Yoga 1 tháng (mã YOG1) bắt đầu ngày 5/12/2026 cho 1 người lớn và một học sinh 15 tuổi khách đã chuyển khoản đặt cọc [SO_TIEN]. Khách yêu câu tập ca sáng 
```

### b) Hai câu lệnh chống ảo giác

**CAU LENH**

```text
Câu 1: Lưu ý: Câu trả lời cần dựa theo những thông tin được cung cấp trong file đính kèm và nếu thông tin nào liên quan đến câu trả lời nào không có trong file, hãy chỉ rõ và hỏi lại tôi.
Câu 2: Sau khi trả lời câu hỏi, hãy chỉ rõ những thông tin được lấy ra từ mục nào, điều khoản nào trong file
```

## 4.2. Trích xuất tin nhắn đăng ký gói tập ra JSON

**PROMPT**

```text
- Prompt: 
<tin_nhan>
TN1: Cho mình đăng ký 10 buổi tập với huấn luyện viên, bắt đầu 15/12 nhé, 2 người lớn và 1 bạn học sinh lớp 9, tập buổi tối.

TN2: Đăng ký Yoga cho 3 người, bắt đầu 04/01/2027. Một người vừa mổ dây chằng gối.

TN3: Gói gym tháng 12 còn ưu đãi không ạ? Nhóm em 4 người lớn, một bạn bị hen suyễn, muốn tập ca sáng.

</tin_nhan>

Với những thông tin được cung cấp, hãy giúp tôi chuyển những tin nhắn trên thành một mảng JSON 3 đối tượng sau, đúng thứ tự:
BẢNG MÃ GÓI TẬP
GYM1 – Gym tự do 1 tháng
YOG1 – Yoga 1 tháng
PT10 – 10 buổi tập cùng huấn luyện viên
.Dựa theo mẫu được cung cấp:
Tin nhắn mẫu 1:
Đăng ký giúp mình gói Yoga 1 tháng bắt đầu 03/11/2026, 1 người lớn với 1 bạn học sinh, tập ca sáng. Mình đang đau lưng nhẹ.
Kết quả đúng:
{"ma_goi": "YOG1", "ngay_bat_dau": "2026-11-03", "nguoi_lon": 1, "hoc_sinh": 1, "ca_tap": "sang", "ghi_chu": "đau lưng nhẹ"}

Tin nhắn mẫu 2:
Gói gym 1 tháng còn nhận không ạ, em tập buổi tối, khi nào bắt đầu cũng được.
Kết quả đúng:
{"ma_goi": "GYM1", "ngay_bat_dau": null, "nguoi_lon": 1, "hoc_sinh": 0, "ca_tap": "toi", "ghi_chu": null}
.Hãy đưa ra câu trả lời chính xác nhất và chỉ trả về JSON không chào hỏi, không giải thích
- Phân tích:
-C: Với những thông tin được cung cấp
    <tin_nhan>
TN1: Cho mình đăng ký 10 buổi tập với huấn luyện viên, bắt đầu 15/12 nhé, 2 người lớn và 1 bạn học sinh lớp 9, tập buổi tối.

TN2: Đăng ký Yoga cho 3 người, bắt đầu 04/01/2027. Một người vừa mổ dây chằng gối.

TN3: Gói gym tháng 12 còn ưu đãi không ạ? Nhóm em 4 người lớn, một bạn bị hen suyễn, muốn tập ca sáng.

</tin_nhan>
-R:
    hãy giúp tôi chuyển những tin nhắn trên thành một mảng JSON 3 đối tượng, đúng thứ tự.
    + Tên: BẢNG MÃ GÓI TẬP 
    + GYM1- Gym tự do 1 tháng
    + YOG1 – Yoga 1 tháng
    + PT10 – 10 buổi tập cùng huấn luyện viên

-E:
Dựa theo mẫu được cung cấp:
    Tin nhắn mẫu 1:
    Đăng ký giúp mình gói Yoga 1 tháng bắt đầu 03/11/2026, 1 người lớn với 1 bạn học sinh, tập ca sáng. Mình đang đau lưng nhẹ.
Kết quả đúng:
{"ma_goi": "YOG1", "ngay_bat_dau": "2026-11-03", "nguoi_lon": 1, "hoc_sinh": 1, "ca_tap": "sang", "ghi_chu": "đau lưng nhẹ"}

Tin nhắn mẫu 2:
Gói gym 1 tháng còn nhận không ạ, em tập buổi tối, khi nào bắt đầu cũng được.
Kết quả đúng:
{"ma_goi": "GYM1", "ngay_bat_dau": null, "nguoi_lon": 1, "hoc_sinh": 0, "ca_tap": "toi", "ghi_chu": null}
-A: 
    Hãy đưa ra câu trả lời
-T:
    Chính xác nhất
-E:
    chỉ trả về JSON không chào hỏi, không giải thích

```

## 4.3. Báo giá bằng Chain-of-Thought

### a) Prompt

**PROMPT**

```text
Với vai trò của một thủ quỹ chuyên nghiệp, hãy tính tổng số tiền cho nhóm công ty dăng kí gói YOG1 gồm 6 người lớn, 2 học sinh (14 tuổi và 16 tuổi) và 1 bé 8 tuổi đi cùng. Có 2 người lớn thuê tủ đồ riêng. Với những yêu cầu sau:
-Quy tắc tính giá:
1. Học sinh (từ 12 đến 17 tuổi) tính 70% giá người lớn. Trẻ dưới 12 tuổi đi cùng gia đình được dùng khu vui chơi miễn phí.
2. Nhóm từ 5 người lớn trở lên được giảm 5% trên tiền gói tập (tiền người lớn + tiền học sinh).
3. Phụ thu thuê tủ đồ riêng: 150.000 đồng/người. Phụ thu không được giảm giá.
4. Tổng tiền = tiền gói tập sau giảm + phụ thu.
- Cần suy luận từng bước theo thứ tự tiền người lớn - tiền học sinh - tiền gói tập - giảm giá nhóm - phụ thu - tổng tiền, ghi rõ các buớc tính và dòng cuối có dạng [RESULT: <TONG_TIEN> đồng]

```

## 4.4. Dây chuyền xử lý khiếu nại (Prompt Chaining)

### a) Prompt Trạm 1

**PROMPT**

```text
EMAIL KHIẾU NẠI CỦA KHÁCH

Tôi và chồng (2 người lớn) đăng ký gói Yoga YOG1 từ 01/11/2026, tập ca tối. Trong tuần qua có 3 buổi lớp Yoga bị huỷ mà phòng tập không báo trước, chúng tôi đến nơi mới biết. Huấn luyện viên Lan rất tận tâm, tôi không có gì phàn nàn về huấn luyện viên. Tôi đề nghị phòng tập giải quyết thỏa đáng.

Với email khiếu nại trên và vai trò của một chuyên viên phân tích, hãy đọc email và giúp tôi trả về một đối tượng JSON đúng 4 trường sau: 
 +Loại sự cố, thiết bị, thiết bị , huấn luyện viên, khác 

Cần kiểm tra kĩ mục khác cũng như tổng tiền cần đền bù trước khi đưa vào prompt 2

với câu trả lời đang dở phía trên, kèm theo bảng thông tin sau, hãy viết tiếp câu trả lời trên.
```

### b) Hai điều cần kiểm tra ở JSON đầu ra của Trạm 1

1. (Viết câu trả lời vào đây – xoá dòng này)

2.

### c) Câu lệnh viết tiếp

**CAU LENH**

```text
(Viết câu lệnh vào đây – xoá dòng này)
```

## 4.5. Prompt chấm bài theo Rubric

**PROMPT**

```text
(Viết prompt vào đây – xoá dòng này)
```

## 4.6. Hoàn thiện System Prompt

> Phần Vai trò và Chuẩn đầu ra đã cho sẵn. Viết tiếp phần Quy tắc ràng buộc và Xử lý ngoại lệ.

```text
[Vai trò]
Bạn là "Trợ lý FitZone", nhân viên tư vấn trên website của phòng tập FitZone Gym, giúp khách chọn và đăng ký một trong 3 gói tập: GYM1 (Gym tự do 1 tháng), YOG1 (Yoga 1 tháng), PT10 (10 buổi tập cùng huấn luyện viên).

[Quy tắc ràng buộc]
1. Chỉ tư vấn 3 gói tập của công ty
2. Không hứa giảm giá ngoài bảng giá 
3. Không hỏi xin thông tin CCCD, số thẻ ngân hàng

[Chuẩn đầu ra]
Trả lời bằng tiếng Việt, lịch sự, tối đa 120 từ. Giá gói tập trình bày dạng gạch đầu dòng. Kết thúc bằng một câu hỏi về nhu cầu tiếp theo của khách.

[Xử lý ngoại lệ]
- Khách hỏi ngoài phạm vi: Hãy trả lời lại bằng cách: Tôi không có thẩm quyền để trả lời câu hỏi của bạn
- Khách cung cấp thiếu thông tin: Vui lòng cung cấp lại những thông tin còn thiếu và chỉ rõ những thông tin còn thiếu cho khách
```
