# Stage10 BT2
## Phần 1
- input: văn bản thô, câu lệnh và mã lệnh được đưa vào
- output: hiển thị đẹp mắt, dễ xem dễ nhìn, dễ thao tác, chi tiết
## Phần 2:
# Hướng dẫn cài đặt cảm biến độ ẩm cho trang trại Lan

Tài liệu này hướng dẫn chi tiết cách kết nối và thiết lập hệ thống tự động tưới nước dựa trên dữ liệu độ ẩm.

## 1. Cài đặt môi trường

Đầu tiên, mở terminal lên rồi gõ lệnh `pip install` để cài đặt thư viện điều khiển:

`pip install sensor-lib-v2 rpi-gpio`

Sau khi cài xong, kiểm tra lại phiên bản bằng lệnh `python3 --version`.

## 2. So sánh các loại cảm biến độ ẩm

| Tiêu chí | Cảm biến cũ (V1) | Cảm biến mới (V2) |
| :--- | :--- | :--- |
| **Độ bền** | Kém, dễ bị oxy hóa | Cao, chống gỉ tốt |
| **Độ chính xác** | Thấp, sai số lớn | Cao, ổn định |
| **Giá thành** | Rẻ | Tầm trung |

## 3. Mã nguồn điều khiển máy bơm (Python)

Dưới đây là đoạn code python mẫu đọc dữ liệu cảm biến và bật tắt máy bơm:

```python
import time
import sensor_lib

# Khởi tạo cảm biến ở chân GPIO 4
sensor = sensor_lib.get_sensor(pin=4)
PUMP_PIN = 17

def main():
    while True:
        humidity = sensor.read_humidity()
        print(f"Độ ẩm hiện tại: {humidity}%")
        
        if humidity < 40:
            print("Độ ẩm thấp, đang bật máy bơm...")
            sensor.turn_on(PUMP_PIN)
        else:
            print("Độ ẩm ổn định, tắt máy bơm.")
            sensor.turn_off(PUMP_PIN)
            
        time.sleep(10)

if __name__ == "__main__":
    main() 