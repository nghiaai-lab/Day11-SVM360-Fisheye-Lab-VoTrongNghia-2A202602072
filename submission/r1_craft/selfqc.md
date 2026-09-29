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

Các dấu `[x]` xác nhận đã soát; chúng không có nghĩa mọi cảnh báo đã được sửa. Hai `ego_body` còn thiếu và metadata tên task của job export được giữ nguyên ở phần cảnh báo phía trên, đã ghi finding/escalation. Task CVAT thực tế được tạo với tên chứa `raw_fisheye`; job export không mang trường tên task.

