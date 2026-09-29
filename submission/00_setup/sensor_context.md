# Sensor context — quan sát trước khi gán nhãn

- Slice `B2-mid` của tôi có ba ảnh `adasind_060000.jpg`, `adasind_086220.jpg` và `adasind_102750.jpg`, kích thước 1080 × 1920. Cả ba là ảnh của một camera fisheye ADASIND; ảnh parking là nguồn khác.
- Tôi thấy rõ vòng kính cong và phần tối bên ngoài. Vật gần mép bị méo nhiều. Phần tối ngoài vòng kính được tính là `lens_border`, không phải mặt đường hay `ego_body`.
- Ở mép trái và phía dưới có phần xe rất gần camera. Tôi cần nhìn từng frame để tách thân/gương/tay lái khỏi vành đen trước khi vẽ `ego_body`.
- Repo không có vị trí lắp camera, intrinsics/extrinsics, độ sâu, timestamp đồng bộ hay calibration bốn camera nên tôi không đoán các thông số này. Phần front/rear/left/right chỉ là bài lập kế hoạch SVM giả lập.
