# Stage 10 BT 3

## báo cáo: giảm chi phí vận hành chatbot ai bằng markdown

## phần 1. phân tích bài toán

- **cơ chế token của ai:** khi hệ thống tiếp nhận văn bản, các mô hình ngôn ngữ lớn không đọc nguyên câu mà bẻ nhỏ từ ngữ thành các đơn vị mã hóa gọi là **token**.
- **lý do markdown tối ưu hơn html:**
  - **cú pháp tinh gọn:** markdown chỉ dùng các ký tự thô cực kỳ ngắn gọn như `#`, `*`, `-` để thể hiện cấu trúc tiêu đề, danh sách hay định dạng.
  - **html rườm rà:** html bắt buộc phải kèm theo các cặp thẻ đóng mở dài dằng dặc (ví dụ: `<h1>...</h1>`, `<strong>...</strong>`, `<ul>...</ul>`).
- **hiệu quả thực tế:** việc loại bỏ các thẻ html dư thừa giúp cắt giảm số lượng token truyền tải qua lại với api của ai, từ đó tiết kiệm đáng kể chi phí vận hành hệ thống và rút ngắn độ trễ phản hồi cho người nông dân.

---

## phần 2. so sánh & đánh giá

| tiêu chí so sánh | định dạng markdown | định dạng html |
| :--- | :--- | :--- |
| **cú pháp** | ngắn gọn, tối giản bằng ký tự đặc biệt | dài dòng, lồng nhiều lớp thẻ tag |
| **số lượng token** | thấp, tiết kiệm chi phí gọi api | cao, tốn kém tài nguyên hệ thống |
| **độ dễ đọc** | rất cao, người đọc văn bản thô vẫn nắm rõ cấu trúc | thấp hơn, dễ bị rối mắt vì vướng thẻ html |
| **khả năng hiển thị** | hỗ trợ render trực tiếp trên các nền tảng web/app hiện đại | yêu cầu trình duyệt phân tích cây dom đầy đủ |

### giải pháp đề xuất cho hệ thống "greentech"

- **lựa chọn:** sử dụng hoàn toàn **markdown** làm chuẩn định dạng dữ liệu giao tiếp giữa backend và mô hình ai.
- **lập luận:** giúp hệ thống tối ưu hóa chi phí api dài hạn, giảm băng thông truyền tải dữ liệu và quan trọng nhất là đảm bảo tốc độ phản hồi nhanh chóng khi bà con nông dân cần tra cứu thông tin khẩn cấp ngoài đồng ruộng.