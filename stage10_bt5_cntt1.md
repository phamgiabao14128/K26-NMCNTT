# STAGE 10 BT 5

## phần 1. phân tích bài toán (input/output và sơ đồ phối hợp)

- **input (đầu vào hệ thống):**
  - dữ liệu cảm biến đo độ ẩm đất, nhiệt độ và ánh sáng ngoài trời.
  - lệnh thủ công từ người nông dân qua ứng dụng di động hoặc web.
- **output (đầu ra hệ thống):**
  - kích hoạt máy bơm nước tự động khi đất khô.
  - hiển thị cảnh báo trạng thái hệ thống lên màn hình lcd và ứng dụng.
- **sơ đồ phối hợp phần cứng:** 
  - `cảm biến môi trường` -> truyền tín hiệu qua chân gpio -> `vi điều khiển (soc/cpu)` xử lý -> phát tín hiệu điều khiển -> `máy bơm / thiết bị ngoại vi`.

---

## phần 2. triển khai file readme.md hoàn chỉnh

# hướng dẫn vận hành hệ thống smart-farm 

tài liệu này mô tả chi tiết cách kết nối, cấu hình và vận hành hệ thống tưới cây tự động cho trang trại lan quy mô lớn.

## 1. mô tả dự án
hệ thống **smart-farm** là giải pháp tự động hóa nông nghiệp tích hợp công nghệ iot, giúp giám sát độ ẩm liên tục và tưới nước thông minh cho trang trại lan nhằm tối ưu hóa năng suất và tiết kiệm nước tối đa.

## 2. hướng dẫn cài đặt môi trường
đầu tiên, mở terminal trên máy tính hoặc raspberry pi rồi chạy lệnh sau để cài đặt các thư viện điều khiển phần cứng cần thiết:

```bash
pip install smartfarm-iot-core rpi-gpio