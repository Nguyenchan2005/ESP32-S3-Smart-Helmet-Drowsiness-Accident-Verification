# Implementation & Testing

## Quy trình hoạt động
1. Khởi động thiết bị.
2. Kết nối BLE giữa mũ và ứng dụng di động.
3. Thu thập dữ liệu gia tốc, góc nghiêng và hình ảnh mắt liên tục.
4. Hiển thị đường đi và cảnh báo cơ bản trên HUD.
5. Khi phát hiện bất thường, hệ thống chuyển sang chế độ cảnh báo tương ứng.

## Chế độ thông thường
- Mũ nhận dữ liệu định vị và chỉ đường từ ứng dụng.
- HUD hiển thị chỉ dẫn rẽ và tốc độ.
- Các cảm biến chạy nền để phát hiện buồn ngủ và va chạm.

## Phát hiện va chạm và SOS
- Khi `Atotal` vượt ngưỡng, hệ thống kiểm tra thêm góc nghiêng và trạng thái sau cú sốc.
- Nếu nghi ngờ tai nạn, kích hoạt đếm ngược xác thực 10-20 giây.
- Nếu không có phản hồi, gửi SMS SOS kèm tọa độ Google Maps.
- Nếu người dùng hủy báo động, gửi tin nhắn xác nhận an toàn.

## Giám sát buồn ngủ
- Camera thu hình ảnh ROI chứa mắt và phân loại trạng thái Open/Close.
- Nếu mắt nhắm liên tục trong `Tsleep` (~2 giây) hoặc tần suất nhắm mắt cao bất thường, kích hoạt cảnh báo.
- Thuật toán bổ sung phân tích gật đầu qua dữ liệu góc nghiêng head-pitch.

## Cảnh báo đa giác quan
- Rung phản hồi xúc giác trên mũ.
- Âm thanh báo động.
- Hiển thị biểu tượng và thông báo trên HUD.
- Ứng dụng điện thoại hiện cảnh báo và gợi ý dừng nghỉ.

## Thử nghiệm và đánh giá
### Kế hoạch thử nghiệm
- Thử nghiệm phòng lab từng module.
- Mô phỏng lái xe trên hệ thống rung.
- Thử nghiệm thực địa di chuyển nhẹ.

### Kết quả sơ bộ
- Phát hiện tai nạn: 100% trên 10 lần thử nghiệm mô phỏng.
- Thời gian gửi SOS: ~15 giây.
- Phát hiện buồn ngủ: chính xác 5/5 trong kịch bản nhắm mắt dài.
- Tỷ lệ báo động giả buồn ngủ: khoảng 10% khi người dùng nhìn xuống.

### Hạn chế
- Khả năng nhạy với ánh sáng yếu hoặc ngược sáng.
- Chưa cá nhân hóa ngưỡng giám sát mắt cho từng người dùng.
- Một số trường hợp không phân biệt được mũ rơi ngoài tình huống đội mũ.

## Hướng phát triển tiếp theo
- Thêm cảm biến nhận diện người đội mũ để giảm báo động giả khi mũ rơi.
- Tối ưu hóa thuật toán học máy để cá nhân hóa cảnh báo buồn ngủ.
- Nâng cấp HUD và thử nghiệm AR/Rear-view trong phiên bản tiếp theo.
- Hỗ trợ thêm cuộc gọi tự động cùng SMS trong chế độ SOS.
