# System Architecture

## Tổng quan kiến trúc
Hệ thống mũ bảo hiểm thông minh được thiết kế theo mô hình IoT gồm ba khối chính:
- Phần cứng đeo trên mũ (Embedded System)
- Ứng dụng di động (Mobile App)
- Hạ tầng kết nối và cảnh báo khẩn cấp

Phần cứng trên mũ chịu trách nhiệm thu thập dữ liệu thời gian thực, xử lý cảnh báo và điều khiển hiển thị. Ứng dụng di động nhận dữ liệu từ mũ qua BLE, xử lý dẫn đường và gửi SMS/SOS khi cần.

## Thành phần phần cứng chính
- Vi điều khiển ESP32-S3: lõi kép, xử lý song song, hỗ trợ FreeRTOS.
- Cảm biến IMU MPU-6050: đo gia tốc 3 trục và con quay hồi chuyển.
- Camera MaixCam: xử lý ảnh thị giác máy tính để giám sát trạng thái mắt.
- Module HUD: màn hình OLED nhỏ, bộ quang học kết hợp combiner để hiển thị thông tin trong tầm nhìn.
- Pin Lithium 3000mAh: cung cấp năng lượng cho toàn bộ hệ thống.
- Module GPS và kết nối Bluetooth Low Energy (BLE).

## Mặt cứng kỹ thuật
- ESP32-S3 đặt ở đỉnh mũ để đo chính xác chuyển động đầu và bảo vệ linh kiện.
- Camera gắn phía gò má trái, hướng về mắt người lái.
- HUD gắn bên phải, chiếu ảnh qua kính phản xạ để không che khuất tầm nhìn.
- Pin và mạch sạc đặt phía sau gáy, tạo đối trọng cân bằng.

## Phần mềm nhúng
Phần mềm được phát triển với Arduino framework kết hợp FreeRTOS.
- Module giám sát gia tốc và va chạm
- Module xử lý ảnh và phát hiện buồn ngủ
- Module điều khiển HUD và giao tiếp BLE
- Cơ chế quản lý năng lượng và lọc nhiễu

## Thuật toán chính
### Phát hiện va chạm
- Tính gia tốc tổng hợp `Atotal = sqrt(ax^2 + ay^2 + az^2)`.
- So sánh với ngưỡng `Athreshold`.
- Xác thực bằng phân tích góc nghiêng và trạng thái sau va chạm để giảm báo động giả.

### Phát hiện buồn ngủ
- Phân tích trạng thái mắt từ ảnh camera để xác định Mở/Đóng.
- Theo dõi tỷ lệ thời gian nhắm mắt liên tục và chuỗi dao động gật đầu.
- Kết hợp PERCLOS và dữ liệu góc nghiêng đầu từ MPU-6050.

### Cảnh báo đa phương thức
- Rung phản hồi xúc giác (haptic feedback)
- Âm thanh cảnh báo
- Hiển thị biểu tượng và thông báo trên HUD
- Gửi thông báo đến ứng dụng di động và SMS SOS nếu cần

## Thiết kế HUD
- Giao diện tối giản, chỉ hiển thị chỉ dẫn đường, tốc độ và cảnh báo.
- Ảnh hiển thị tập trung ở vùng ngoại vi để không che khuất đường đi.
- Điều chỉnh độ sáng tự động theo môi trường.

## Hình ảnh minh họa
Các hình ảnh sẵn có trong `assets/images/` gồm sơ đồ khối hệ thống, bố trí linh kiện, giao diện HUD và luồng xử lý.
