# Sensor context — quan sát trước khi gán nhãn

- Slice cá nhân `B2-mid` gồm ba ảnh `adasind_060000.jpg`, `adasind_086220.jpg` và `adasind_102750.jpg`, kích thước 1080 × 1920. Đây là ảnh từ **một camera fisheye** ADASIND; ảnh parking là nguồn camera thường riêng.
- Trên ba ảnh có đường biên cong của vùng nhìn và vành tối ngoài vòng kính. Vật ở gần mép chịu méo hình mạnh; vùng tối ngoài vòng nhìn cần được soát như `lens_border`, không tính là mặt đường hay `ego_body`.
- Mép trái/dưới có cấu trúc rất gần camera. Khi gán nhãn sẽ xét từng frame xem phần nào thật sự là thân/gương/tay lái xe để vẽ `ego_body` theo rule; không suy từ vành đen rằng có thân xe ở mọi vị trí.
- Repo không cung cấp vị trí hoặc độ cao lắp camera, intrinsics/extrinsics, độ sâu, timestamp đồng bộ hay calibration giữa bốn camera. Không suy các thông số đó từ ảnh. Bài phân bổ front/rear/left/right là tình huống SVM giả lập, không phải bốn luồng ảnh có sẵn trong ADASIND.
