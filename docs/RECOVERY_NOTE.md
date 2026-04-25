# Recovery Note

## Mục Đích

Ghi chú này mô tả nguồn dữ liệu được dùng để biên soạn lại bộ tài liệu dự án và tình trạng của các file Word gốc trong repository.

## Tình Trạng Tài Liệu Gốc

| File | Tình trạng | Ghi chú |
| --- | --- | --- |
| `MH05_SmartHelmet1.docx` | Đọc và trích xuất được | Là nguồn chính cho README và các tài liệu trong `docs/`. |
| `Springer-v2.docx` | Lỗi cấu trúc ZIP/DOCX | Không thể trích xuất ổn định trong môi trường hiện tại. |
| `Springer-v2-recover.docx` | Bản phục hồi đi kèm | Giữ lại để tham khảo/phục hồi thủ công khi cần. |
| `Springer-v2-repaired.zip` | Gói phục hồi đi kèm | Giữ lại nguyên trạng trong repository. |

## Nội Dung Đã Sử Dụng

Bộ tài liệu Markdown hiện tại được biên soạn từ:

- Nội dung văn bản của `MH05_SmartHelmet1.docx`.
- Các hình ảnh đã trích xuất vào `assets/images/`.
- Các thông tin kỹ thuật về ESP32-S3, MPU-6050, MaixCam, HUD, BLE, GPS/SMS và kết quả thử nghiệm trong báo cáo gốc.

## Nguyên Tắc Biên Soạn Lại

- Sửa lỗi mã hóa tiếng Việt trong các file Markdown cũ.
- Tổ chức nội dung theo cách người đọc dễ nắm: tổng quan trước, kỹ thuật sau, kết quả cuối cùng.
- Ưu tiên mô tả trung thực theo báo cáo gốc, không tự thêm số liệu ngoài nguồn.
- Giữ lại các file Word gốc để người dùng có thể đối chiếu hoặc phục hồi sâu hơn trong Microsoft Word.

## Khuyến Nghị

Nếu cần khai thác thêm `Springer-v2.docx`, nên mở file bằng Microsoft Word trên Windows và dùng chức năng sửa lỗi tài liệu. Sau khi phục hồi thành công, có thể bổ sung nội dung mới vào `docs/` và ghi rõ nguồn cập nhật trong ghi chú này.
