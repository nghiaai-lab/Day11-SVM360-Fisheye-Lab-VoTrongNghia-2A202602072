# Đề xuất gold set theo camera — tình huống giả lập

Đề bài giả sử có 50.000 frame từ bốn camera và cần chọn 200 frame; repo không có tập ảnh này. Tôi chia mỗi camera thành 25 frame normal và 25 frame hard vì chưa có thống kê rủi ro để chia theo tỷ lệ khác. Đây chỉ là kế hoạch chọn mẫu, chưa phải 200 frame đã lấy hoặc gold set đã duyệt.

| camera_id | Normal cần chọn nếu có | Hard case cần chọn nếu có | Vì sao cần soát kỹ | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|---|
| front | Vật rõ trong vùng nhìn hữu dụng phía trước | Vật hai bánh hoặc người ở rìa và seam trước trái/phải; che khuất hoặc bị cắt | Class rider và biên box có thể khó đọc trên ảnh fisheye gốc | Giữ tọa độ ảnh fisheye gốc; lưu phiên bản calibration và timestamp nếu có; BEV là không gian khác | Người gán nhãn và người soát độc lập đối chiếu ảnh gốc cùng rule; bất đồng đưa người phân xử |
| rear | Vật rõ trong vùng nhìn phía sau | Vật gần đuôi xe hoặc seam sau trái/phải khi lùi đỗ nếu có | Thân xe và vật khác có thể che phần nhìn thấy | Giữ tọa độ ảnh gốc và metadata camera sau; chưa suy vùng lái xe an toàn từ ảnh tĩnh | Soát riêng camera sau; xác nhận vùng ignore và ca bị che trước khi khóa |
| left | Vật rõ trong camera trái | Vật tại seam trái trước/sau hoặc ở rìa méo | Một vật có thể xuất hiện cả ở camera trái và camera kề | Giữ ID camera trái và phép biến đổi hiệu chuẩn có phiên bản nếu có | Soát độc lập từng box trên ảnh trái rồi phân xử ca seam theo policy |
| right | Vật rõ trong camera phải | Vật tại seam phải trước/sau hoặc ở rìa méo | Không thể lấy nhãn camera trái thay cho camera phải | Giữ ID camera phải và phép biến đổi hiệu chuẩn có phiên bản nếu có | Soát độc lập ảnh phải và ghi bất đồng riêng trước khi chốt |

Tôi sẽ chọn theo `camera_id` và normal/hard, sau đó rải theo thời gian và bối cảnh nếu có metadata rồi bỏ frame gần trùng. Nếu tập nguồn không có một loại hard case, tôi sẽ ghi thiếu thay vì lấy frame của camera khác bù vào. Hai người soát độc lập; khi không thống nhất thì nhờ người thứ ba chốt trước khi gọi là gold.

- Tôi sẽ lấy mẫu lại khi đổi camera, vị trí lắp, calibration, độ phân giải, guideline hoặc bối cảnh dữ liệu; mỗi lần phải ghi phiên bản.
- Ví dụ ca seam: cùng một người xuất hiện ở front và left tại cùng thời điểm. Cả hai box trên ảnh gốc có thể đều đúng. Chỉ gộp hoặc nối track khi có timestamp đồng bộ, calibration và quy tắc output rõ ràng.
- ADASIND trong repo chỉ có một camera, còn ảnh parking là nguồn khác. Các báo cáo của bài này chưa chứng minh gold set bốn camera đã đúng.
