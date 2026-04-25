# Recovery Note

## Mục Đích

Ghi chú này mô tả nguồn dữ liệu được dùng để biên soạn lại bộ tài liệu dự án và tình trạng của các file Word gốc trong repository.

## Tình Trạng Tài Liệu Gốc

| File | Tình trạng | Ghi chú |
| --- | --- | --- |
| `reports/RESEARCH_REPORT_SMART_HELMET.docx` | Đọc và trích xuất được | Là nguồn chính cho README và các tài liệu trong `docs/`. |
| `paper/ACCEPTED_PAPER_SPRINGER_V2.docx` | Paper accepted, có dấu hiệu lỗi cấu trúc ZIP/DOCX khi đọc tự động | Được đặt riêng để làm rõ đầu ra học thuật; nên mở bằng Microsoft Word nếu cần phục hồi/chỉnh sửa. |
| `archive/Springer-v2-recover.docx` | Bản phục hồi đi kèm | Giữ lại để tham khảo/phục hồi thủ công khi cần. |
| `archive/Springer-v2-repaired.zip` | Gói phục hồi đi kèm | Giữ lại trong `archive/` để root repository gọn hơn. |

## Nội Dung Đã Sử Dụng

Bộ tài liệu Markdown hiện tại được biên soạn từ:

- Nội dung văn bản của `reports/RESEARCH_REPORT_SMART_HELMET.docx` (file gốc trước khi dọn folder là `MH05_SmartHelmet1.docx`).
- Các hình ảnh đã trích xuất vào `assets/images/`.
- Các thông tin kỹ thuật về ESP32-S3, MPU-6050, MaixCam, HUD, BLE, GPS/SMS và kết quả thử nghiệm trong báo cáo gốc.

## Nguyên Tắc Biên Soạn Lại

- Sửa lỗi mã hóa tiếng Việt trong các file Markdown cũ.
- Tổ chức nội dung theo cách người đọc dễ nắm: tổng quan trước, kỹ thuật sau, kết quả cuối cùng.
- Ưu tiên mô tả trung thực theo báo cáo gốc, không tự thêm số liệu ngoài nguồn.
- Giữ lại các file Word gốc/phục hồi trong `paper/`, `reports/` và `archive/` để người dùng có thể đối chiếu hoặc phục hồi sâu hơn trong Microsoft Word.

## Khuyến Nghị

Nếu cần khai thác thêm paper, nên mở `paper/ACCEPTED_PAPER_SPRINGER_V2.docx` bằng Microsoft Word trên Windows và dùng chức năng sửa lỗi tài liệu. Sau khi phục hồi thành công, có thể bổ sung thông tin accepted như DOI, hội nghị/tạp chí, thư chấp nhận hoặc link xuất bản vào `paper/README.md`.
