# Tiếp nhận P2 cho QA vai B

- Nguồn: [commit d7862e5](https://github.com/DTKien2005/Day11-SVM360-Fisheye-Lab-Student/commit/d7862e5cc9611907fd907d43287bb36c2c8f2111).
- Nhận lúc: 2026-09-29T12:40:15.681741+07:00.
- Slice tôi nhận: B4-center.
- SHA-256 XML khớp lock, mã 6997-BF13.
- Có đủ 3 ảnh 1080×1920; 27 box và 8 polygon.
- Mã L theo report.scoped của tool QA (box cao từ 40 px), bắt đầu lại trên từng ảnh.

## Các điểm tôi cần kiểm trên ảnh

1. `adasind_295948.jpg`: XML box #1 Car cao 26.99 px, dưới ngưỡng R01. Box này không có mã L trong overlay chuẩn nên overlay thêm ký hiệu XML#1.
2. Cờ `occluded` gốc và custom attribute không giống nhau tại `271039` L7/L8/L9 và `295948` L4/L5/L7. Tool đọc custom attribute, nên tôi phải xem ảnh theo R05 trước khi đề nghị sửa.
3. adasind_271039.jpg nằm trong danh sách ngoại lệ không có ego_body của repo; chỉ có hai lens_border không tự động là lỗi thiếu ego.

Sau khi nhận file, tôi xem cả ba ảnh và ghi bốn finding ở frame `295948`. Chi tiết nằm trong `qa_review_B4-center.md`. Lúc đó tôi chưa mở reference, model hoặc compare của slice này.
