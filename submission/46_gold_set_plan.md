# Đề xuất gold set theo camera — tình huống giả lập

Tình huống có 50.000 frame bốn camera và ngân sách chọn 200 frame; repo này không chứa tập đó. Bảng `45_sampling_plan.csv` chia đều 25 normal và 25 hard cho từng camera để bảo đảm độ phủ ban đầu khi chưa biết phân bố rủi ro thực tế. Đây là phân bổ thiết kế để rà soát, không phải 200 frame đã được lấy hay gold set đã được duyệt. Sau P4 sẽ xem lại lý do phân bổ nhưng không suy số liệu bốn camera từ ADASIND một camera.

| camera_id | Normal cần chọn nếu có | Hard case cần chọn nếu có | Vì sao cần soát kỹ | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|---|
| front | Vật rõ trong vùng nhìn hữu dụng phía trước | Vật hai bánh hoặc người ở rìa và seam trước trái/phải; che khuất hoặc bị cắt | Class rider và biên box có thể khó đọc trên ảnh fisheye gốc | Giữ tọa độ ảnh fisheye gốc; lưu phiên bản calibration và timestamp nếu có; BEV là không gian khác | Người gán nhãn và người soát độc lập đối chiếu ảnh gốc cùng rule; bất đồng đưa người phân xử |
| rear | Vật rõ trong vùng nhìn phía sau | Vật gần đuôi xe hoặc seam sau trái/phải khi lùi đỗ nếu có | Thân xe và vật khác có thể che phần nhìn thấy | Giữ tọa độ ảnh gốc và metadata camera sau; chưa suy vùng lái xe an toàn từ ảnh tĩnh | Soát riêng camera sau; xác nhận vùng ignore và ca bị che trước khi khóa |
| left | Vật rõ trong camera trái | Vật tại seam trái trước/sau hoặc ở rìa méo | Một vật có thể xuất hiện cả ở camera trái và camera kề | Giữ ID camera trái và phép biến đổi hiệu chuẩn có phiên bản nếu có | Soát độc lập từng box trên ảnh trái rồi phân xử ca seam theo policy |
| right | Vật rõ trong camera phải | Vật tại seam phải trước/sau hoặc ở rìa méo | Không thể lấy nhãn camera trái thay cho camera phải | Giữ ID camera phải và phép biến đổi hiệu chuẩn có phiên bản nếu có | Soát độc lập ảnh phải và ghi bất đồng riêng trước khi chốt |

Chọn mẫu theo `camera_id` và normal/hard trước; trong mỗi ô rải theo thời gian và bối cảnh nếu metadata cho phép, loại các frame gần trùng. Nếu một loại hard không có trong tập nguồn, ghi thiếu độ phủ thay vì thay bằng frame camera khác. Hai người soát độc lập kiểm ảnh và rule; người phân xử giải quyết khác biệt và ký phiên bản trước khi gọi là gold.

- Refresh khi camera, vị trí lắp, calibration, độ phân giải, guideline hoặc phân bố bối cảnh thay đổi; lấy mẫu lại các ca bị ảnh hưởng và ghi phiên bản.
- Ca seam: cùng một người xuất hiện ở front và left tại cùng thời điểm. Hai box trên ảnh gốc có thể đều hợp lệ. Cần timestamp đồng bộ, calibration và policy output đích trước khi gộp/xóa box hoặc nối track; thiếu các dữ kiện đó thì giữ ca là chưa phân xử.
- ADASIND trong repo chỉ là một camera; ảnh parking là camera thường. Teaching reference, peer agreement và quality report trên các ảnh này không chứng minh gold set bốn camera đã đúng.
