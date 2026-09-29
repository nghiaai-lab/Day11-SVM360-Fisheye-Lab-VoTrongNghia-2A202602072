# Đối chiếu chất lượng cục bộ — rectangle

Teaching reference, không phải gold set đã phê duyệt; không có điểm đạt tự động.
Nguồn: export r1_craft đã khóa SHA256 `7c9c5d8635cab4a8789fba141ed68b4e9078f333ea24e43fd06ae241b46ea6e9`; slice `B2-mid`.
Ghép hình học greedy một-một theo IoU ≥ 0.50, rồi so class; H ≥ 40 px.
Box trái nằm chủ yếu trong ignore_region reference không tính. Polygon, polyline, track không được chấm.
Đây là phép tính offline của lab, không phải báo cáo hay kết quả tương đương CVAT Premium.

Frame được tính: adasind_060000.jpg, adasind_086220.jpg, adasind_102750.jpg. Frame thiếu trong export: không.
TP=8; FP=0; FN=12; số lần đối chiếu=20; mean IoU của TP=1.000.

| Chỉ số | Micro | Macro | Nhãn thấp nhất |
|---|---:|---:|---:|
| accuracy | 0.400 | 0.850 | 0.800 |
| precision | 1.000 | 0.750 | 0.000 |
| recall | 0.400 | 0.326 | 0.000 |
| jaccard | 0.400 | 0.326 | 0.000 |
| dice | 0.571 | 0.445 | 0.000 |

| Nhãn | TP | FP | FN | Accuracy | Precision | Recall | Jaccard | Dice |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bike | 1 | 0 | 3 | 0.850 | 1.000 | 0.250 | 0.250 | 0.400 |
| Pedestrian | 2 | 0 | 2 | 0.900 | 1.000 | 0.500 | 0.500 | 0.667 |
| ThreeWheeler | 5 | 0 | 4 | 0.800 | 1.000 | 0.556 | 0.556 | 0.714 |
| Truck | 0 | 0 | 3 | 0.850 | 0.000 | 0.000 | 0.000 | 0.000 |

| Frame | TP | FP | FN | Accuracy | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| adasind_060000.jpg | 5 | 0 | 5 | 0.500 | 1.000 | 0.500 |
| adasind_086220.jpg | 3 | 0 | 2 | 0.600 | 1.000 | 0.600 |
| adasind_102750.jpg | 0 | 0 | 5 | 0.000 | 0.000 | 0.000 |

Confusion matrix: hàng = teaching reference; cột = export đã khóa.
`<missing>` là thiếu box; `<extra>` là box thừa. Xem `local_quality_confusion.csv`.

| Reference \ Export | Bike | Pedestrian | ThreeWheeler | Truck | <missing> |
|---|---:|---:|---:|---:|---:|
| Bike | 1 | 0 | 0 | 0 | 3 |
| Pedestrian | 0 | 2 | 0 | 0 | 2 |
| ThreeWheeler | 0 | 0 | 5 | 0 | 4 |
| Truck | 0 | 0 | 0 | 0 | 3 |
| <extra> | 0 | 0 | 0 | 0 | 0 |

Chi tiết xung đột trong `local_quality_conflicts.csv`; dữ liệu máy đọc trong `local_quality.json`.
Mismatching label đóng góp một FP cho class vẽ và một FN cho class reference; attribute khác được báo riêng.
Micro accuracy đếm mỗi cặp ghép sai class là một lần đối chiếu; Jaccard đếm cả FP và FN.
Macro/worst bỏ nhãn không xuất hiện ở cả hai phía; chỉ số không có mẫu là N/A.
