# STAGE 10 BT 6

## phần 1. phân tích lỗi và bản chất vấn đề

- **sai lầm 1 trong tư duy của nam (dùng rich text cho mã nguồn):** nam dùng microsoft word (.docx) để viết tài liệu dự án và đẩy lên github. định dạng docx là file nhị phân (binary), nên khi các thành viên trong nhóm mở trực tiếp trên trình duyệt web, github không thể render hay hiển thị nội dung trực tiếp được mà bắt buộc mọi người phải tải file về máy rất bất tiện.
- **sai lầm 2 (xung đột git conflict):** do file word chứa nhiều cấu trúc ngầm và mã định dạng phức tạp bên trong, nên khi nam chỉ sửa một dấu phẩy nhỏ rồi commit lên, hệ thống git không thể so sánh từng dòng văn bản (git diff) chính xác mà báo lỗi xung đột toàn bộ file, khiến cả đội mất thời gian xử lý.
- **tại sao markdown an toàn và nhẹ hơn:** markdown là văn bản thô (plain text) thuần túy nên dung lượng cực kỳ nhẹ, github hỗ trợ render trực tiếp thành giao diện đẹp mắt ngay trên web, đồng thời git có thể dễ dàng so sánh từng dòng thay đổi nhỏ nhất để tránh triệt để lỗi conflict.

---

## phần 2. hoàn thiện và chuyển đổi sang file readme.md

```markdown
# dự án nhóm "greentech" - tài liệu giới thiệu

chào mừng anh em đến với kho lưu trữ mã nguồn của dự án green-tech. tài liệu này tóm tắt những ý tưởng chính và mục tiêu phát triển hệ thống nông nghiệp thông minh.

## 1. mục tiêu dự án
- xây dựng hệ thống giám sát môi trường tự động cho trang trại lan.
- tối ưu hóa quy trình tưới tiêu bằng công nghệ iot kết hợp ai assistant.

## 2. thành viên nhóm phát triển
- phạm gia bảo - phụ trách hệ thống và lập trình backend.
- các thành viên khác - phụ trách tài liệu và kiểm thử thiết bị.

## 3. hướng dẫn đóng góp
mọi người khi chỉnh sửa tài liệu vui lòng tuân thủ việc sử dụng định dạng markdown thuần túy (.md) để tránh gây xung đột git conflict khi push code lên github nhé.