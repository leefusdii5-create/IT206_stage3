# BÀI TẬP: XÂY DỰNG KẾ HOẠCH HỌC TẬP 7 NGÀY BẰNG AI

## 1. Xây dựng Prompt theo khung CREATE

### C - Context (Bối cảnh)
Bạn là chuyên gia tư vấn phương pháp học tập và quản lý thời gian cho sinh viên năm nhất. Sinh viên đang gặp khó khăn trong việc duy trì thói quen học tập và thường xuyên trì hoãn công việc.

### R - Request (Yêu cầu)
Lập kế hoạch học tập trong 7 ngày, từ thứ Hai đến Chủ nhật, bao gồm thời gian học trên lớp, tự học, làm bài tập và giải trí.

### E - Explanation (Giải thích)
Kế hoạch giúp sinh viên quản lý thời gian tốt hơn, hoàn thành bài tập đúng hạn và cân bằng giữa học tập với nghỉ ngơi.

### A - Action (Hành động)
- Phân chia thời gian học tập hợp lý trong ngày.
- Ưu tiên những môn có nhiều bài tập.
- Bố trí thời gian tự học vào buổi chiều và buổi tối.
- Sắp xếp thời gian nghỉ ngơi và giải trí mỗi ngày.
- Xây dựng kế hoạch đầy đủ cho cả 7 ngày.

### T - Tone (Giọng điệu)
Trình bày rõ ràng, thực tế, dễ hiểu và phù hợp với sinh viên năm nhất.

### E - Extras (Bổ sung)
- Không xếp lịch học trên lớp từ thứ Hai đến thứ Sáu ngoài khung 7h30–11h30.
- Mỗi ngày có ít nhất 1 giờ giải trí.
- Không học quá 3 giờ liên tục.
- Có thời gian nghỉ giữa các buổi học.
- Thứ Bảy và Chủ nhật dành thời gian tự học, ôn tập và nghỉ ngơi.

---

## 2. Prompt hoàn chỉnh

```text
Bạn là chuyên gia tư vấn phương pháp học tập và quản lý
thời gian dành cho sinh viên năm nhất.

NHIỆM VỤ:
Hãy lập kế hoạch học tập trong 7 ngày giúp sinh viên
khắc phục tình trạng trì hoãn và sử dụng thời gian
hiệu quả hơn.

THÔNG TIN VÀ RÀNG BUỘC:
- Học trên lớp từ thứ Hai đến thứ Sáu.
- Thời gian học trên lớp: 7h30–11h30.
- Tự học vào buổi chiều và buổi tối.
- Mỗi ngày có ít nhất 1 giờ giải trí.
- Không học quá 3 giờ liên tục.
- Có thời gian nghỉ ngơi và ăn uống hợp lý.

YÊU CẦU THỰC HIỆN:
1. Phân bổ thời gian học tập trong 7 ngày.
2. Ưu tiên các môn có nhiều bài tập hoặc sắp đến hạn.
3. Kết hợp học trên lớp, tự học, làm bài tập và ôn tập.
4. Bố trí thời gian giải trí và nghỉ ngơi mỗi ngày.
5. Cuối tuần có thời gian tổng kết kiến thức và chuẩn bị
   cho tuần học tiếp theo.

ĐỊNH DẠNG ĐẦU RA:
Trình bày bằng bảng Markdown gồm các cột:
- Ngày
- Thời gian
- Hoạt động
- Mục tiêu

Sau bảng, viết phần nhận xét ngắn về tính hợp lý
của kế hoạch.

LƯU Ý:
- Phải có đủ 7 ngày từ thứ Hai đến Chủ nhật.
- Không xếp lịch trùng thời gian.
- Không học quá 3 giờ liên tục.
- Không bỏ qua thời gian nghỉ ngơi.
- Không viết đoạn văn giải thích dài dòng.
```

---

## 3. Kết quả kế hoạch học tập mẫu trong 7 ngày

| Ngày | Thời gian | Hoạt động | Mục tiêu |
|---|---|---|---|
| Thứ Hai | 7h30–11h30 | Học trên lớp | Tiếp thu kiến thức mới |
| Thứ Hai | 14h00–16h00 | Tự học môn khó | Hiểu bài và ghi chú |
| Thứ Hai | 19h00–20h30 | Làm bài tập | Hoàn thành bài được giao |
| Thứ Hai | 20h30–21h30 | Giải trí | Thư giãn |
| Thứ Ba | 7h30–11h30 | Học trên lớp | Ghi chép bài đầy đủ |
| Thứ Ba | 14h00–16h00 | Làm bài tập môn nhiều bài | Hoàn thành bài tập |
| Thứ Ba | 19h00–20h30 | Ôn tập kiến thức | Củng cố bài học |
| Thứ Ba | 20h30–21h30 | Giải trí | Giảm căng thẳng |
| Thứ Tư | 7h30–11h30 | Học trên lớp | Tiếp thu kiến thức |
| Thứ Tư | 14h00–16h00 | Tự học và nghiên cứu | Nắm chắc nội dung |
| Thứ Tư | 19h00–20h30 | Làm bài tập | Cải thiện kỹ năng |
| Thứ Tư | 20h30–21h30 | Giải trí | Nghỉ ngơi |
| Thứ Năm | 7h30–11h30 | Học trên lớp | Hoàn thành nội dung học |
| Thứ Năm | 14h00–16h00 | Ôn tập môn khó | Khắc phục phần chưa hiểu |
| Thứ Năm | 19h00–20h30 | Làm bài tập | Hoàn thành nhiệm vụ |
| Thứ Năm | 20h30–21h30 | Giải trí | Thư giãn |
| Thứ Sáu | 7h30–11h30 | Học trên lớp | Tổng hợp kiến thức |
| Thứ Sáu | 14h00–16h00 | Hoàn thành bài tập còn thiếu | Đảm bảo đúng hạn |
| Thứ Sáu | 19h00–20h00 | Ôn tập kiến thức trong tuần | Hệ thống lại bài học |
| Thứ Sáu | 20h00–21h00 | Giải trí | Nghỉ ngơi |
| Thứ Bảy | 8h00–10h00 | Tự học môn khó | Nâng cao kiến thức |
| Thứ Bảy | 14h00–16h00 | Làm bài tập và thực hành | Cải thiện kỹ năng |
| Thứ Bảy | 19h00–20h00 | Đọc tài liệu | Mở rộng kiến thức |
| Thứ Bảy | 20h00–21h00 | Giải trí | Thư giãn |
| Chủ nhật | 8h00–10h00 | Ôn tập kiến thức | Củng cố kiến thức tuần |
| Chủ nhật | 14h00–15h00 | Lập kế hoạch tuần mới | Chuẩn bị công việc |
| Chủ nhật | 15h00–16h00 | Giải trí | Thư giãn |
| Chủ nhật | Buổi tối | Nghỉ ngơi | Chuẩn bị cho tuần mới |

## 4. Nhận xét về kế hoạch

- Kế hoạch phân bổ thời gian hợp lý giữa học trên lớp, tự học và giải trí.
- Các môn khó và môn có nhiều bài tập được ưu tiên.
- Có thời gian nghỉ giữa các buổi học, không học liên tục quá 3 giờ.
- Cuối tuần có thời gian ôn tập và chuẩn bị cho tuần tiếp theo.
- Giúp sinh viên hạn chế trì hoãn và hình thành thói quen học tập chủ động.