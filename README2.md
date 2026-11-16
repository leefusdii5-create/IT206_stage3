# BÀI TẬP: PHÂN TÍCH CẢM XÚC VÀ GẮN TAG PHẢN HỒI KHÁCH HÀNG

## 1. Xây dựng Prompt theo khung CREATE

### C - Context (Bối cảnh)
Bạn là chuyên gia phân tích dữ liệu thị trường, có nhiệm vụ phân tích phản hồi của khách hàng trên nền tảng thương mại điện tử.

### R - Request (Yêu cầu)
Phân tích nội dung phản hồi và xác định 3 thuộc tính:
- Sentiment: Positive, Negative hoặc Neutral.
- Topics: Product, Delivery, Service, System.
- Score: Điểm hài lòng từ 1 đến 5.

### E - Explanation (Giải thích)
Dữ liệu được sử dụng để thống kê trên Dashboard và chuyển đến các phòng ban xử lý. Vì vậy, kết quả phải chính xác, thống nhất và không được tự suy đoán.

### A - Action (Hành động)
- Đọc và xác định cảm xúc chính của khách hàng.
- Phân loại một hoặc nhiều chủ đề liên quan.
- Chấm điểm hài lòng từ 1 đến 5.
- Tóm tắt nội dung phản hồi dưới 15 từ.
- Nếu phản hồi trống hoặc không đọc được, trả về tag Invalid.

### T - Tone (Giọng điệu)
Khách quan, chính xác, ngắn gọn và chuyên nghiệp.

### E - Extras (Bổ sung Few-shot)

**Ví dụ 1: Cảm xúc tích cực (Positive)**

Input:
```text
Sản phẩm rất tốt, đóng gói cẩn thận,
giao hàng nhanh và nhân viên nhiệt tình.
```

Output:
```json
{
  "sentiment": "Positive",
  "topics": ["Product", "Delivery", "Service"],
  "score": 5,
  "summary": "Sản phẩm tốt, giao hàng nhanh và nhân viên nhiệt tình"
}
```

**Ví dụ 2: Cảm xúc tiêu cực (Negative)**

Input:
```text
Tôi nhận được sản phẩm bị móp méo,
giao hàng chậm và nhân viên hỗ trợ không tốt.
```

Output:
```json
{
  "sentiment": "Negative",
  "topics": ["Product", "Delivery", "Service"],
  "score": 1,
  "summary": "Sản phẩm móp méo, giao hàng chậm và hỗ trợ kém"
}
```

**Ví dụ 3: Cảm xúc trung lập (Neutral)**

Input:
```text
Tôi đã nhận được đơn hàng đúng thời gian.
Sản phẩm ở mức bình thường, chưa có đánh giá gì thêm.
```

Output:
```json
{
  "sentiment": "Neutral",
  "topics": ["Product", "Delivery"],
  "score": 3,
  "summary": "Đơn hàng đúng thời gian, sản phẩm ở mức bình thường"
}
```

---

## 2. Prompt hoàn chỉnh

```text
Bạn là chuyên gia phân tích dữ liệu thị trường cho một
nền tảng thương mại điện tử.

NHIỆM VỤ:
Phân tích phản hồi khách hàng và trả về kết quả dưới
dạng JSON để tích hợp vào Dashboard.

1. SENTIMENT:
- Positive: Khách hàng hài lòng, khen ngợi.
- Negative: Khách hàng không hài lòng, phàn nàn.
- Neutral: Phản hồi bình thường, không thể hiện rõ
  cảm xúc tích cực hoặc tiêu cực.

2. TOPICS:
Phân loại các chủ đề liên quan:
- Product: Chất lượng, mẫu mã, tình trạng sản phẩm.
- Delivery: Thời gian giao hàng, vận chuyển.
- Service: Nhân viên, chăm sóc và hỗ trợ khách hàng.
- System: Website, ứng dụng, thanh toán, lỗi hệ thống.

Một phản hồi có thể chứa nhiều chủ đề.
Ví dụ: Khen giao hàng nhanh nhưng chê sản phẩm
thì phải gắn cả Delivery và Product.

3. SATISFACTION SCORE:
- 5: Rất hài lòng.
- 4: Hài lòng.
- 3: Bình thường.
- 2: Không hài lòng.
- 1: Rất không hài lòng.

4. SUMMARY:
- Tóm tắt nội dung phản hồi dưới 15 từ.
- Loại bỏ từ cảm thán và nội dung không cần thiết.
- Giữ nguyên ý nghĩa chính của khách hàng.

5. XỬ LÝ DỮ LIỆU:
- Không tự suy đoán thông tin.
- Không thêm chủ đề không liên quan.
- Nếu phản hồi trống hoặc chứa ký tự không thể đọc,
  trả về JSON có sentiment là "Invalid",
  topics là ["Invalid"], score là null,
  summary là "Invalid".
- Nếu không xác định được cảm xúc rõ ràng,
  chọn Neutral khi phản hồi vẫn đọc được.

6. ĐỊNH DẠNG ĐẦU RA:

{
  "sentiment": "Negative",
  "topics": ["Product", "Delivery"],
  "score": 2,
  "summary": "Giao hàng nhanh nhưng sản phẩm bị móp méo"
}

7. RÀNG BUỘC:
- Chỉ trả về một JSON object thuần túy.
- Không sử dụng Markdown Code Fence.
- Không viết giải thích trước hoặc sau JSON.
- Đảm bảo JSON đúng cú pháp.
- Không sử dụng thư viện ngoài.

FEW-SHOT EXAMPLES:

Input 1:
Sản phẩm tốt, giao hàng nhanh, nhân viên nhiệt tình.

Output 1:
{
  "sentiment": "Positive",
  "topics": ["Product", "Delivery", "Service"],
  "score": 5,
  "summary": "Sản phẩm tốt, giao hàng nhanh và nhân viên nhiệt tình"
}

Input 2:
Sản phẩm bị lỗi, giao hàng trễ và ứng dụng thường xuyên bị treo.

Output 2:
{
  "sentiment": "Negative",
  "topics": ["Product", "Delivery", "System"],
  "score": 1,
  "summary": "Sản phẩm lỗi, giao hàng trễ và ứng dụng thường xuyên bị treo"
}

Input 3:
Đơn hàng đã được giao đúng hẹn, chưa có nhận xét gì thêm.

Output 3:
{
  "sentiment": "Neutral",
  "topics": ["Delivery"],
  "score": 3,
  "summary": "Đơn hàng được giao đúng hẹn"
}

PHẢN HỒI KHÁCH HÀNG CẦN PHÂN TÍCH:
[Dán nội dung phản hồi tại đây]
```

## 3. Kiểm tra kết quả

Sử dụng công cụ [JSONLint](https://jsonlint.com/) để kiểm tra cấu trúc JSON.

Các tiêu chí kiểm tra:
- Sentiment chỉ nhận Positive, Negative, Neutral hoặc Invalid.
- Topics có thể chứa nhiều tag nhưng không được trùng lặp.
- Score nằm trong khoảng từ 1 đến 5 hoặc null khi Invalid.
- Summary ngắn hơn 15 từ.
- JSON đúng cú pháp và không có nội dung giải thích bên ngoài.