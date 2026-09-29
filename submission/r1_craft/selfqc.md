# Tự soát

- adasind_060000.jpg: thiếu ego_body
- adasind_086220.jpg: thiếu ego_body
- adasind_102750.jpg: thiếu ego_body
- Tên task thiếu raw_fisheye

## Checklist thủ công
- [x] Phạm vi H=40 và vật cần vẽ
- [x] lens_border và ego_body
- [x] Class sáu nhãn
- [x] Rider và Bike
- [x] Geometry trên ảnh fisheye gốc
- [x] truncated và occluded
- [x] Vật thiếu hoặc box trùng
- [x] ignore_region có reason
- [x] Tên task raw_fisheye và export CVAT 1.1

Tôi đã soát các mục trên ảnh. Hai frame phải làm (`060000`, `086220`) vẫn thiếu `ego_body`; frame `102750` đã cắt theo time-box. Task CVAT có `raw_fisheye` trong tên nhưng XML export không lưu tên task. Tôi giữ nguyên bản đã khóa và ghi các lỗi này để xử lý.

