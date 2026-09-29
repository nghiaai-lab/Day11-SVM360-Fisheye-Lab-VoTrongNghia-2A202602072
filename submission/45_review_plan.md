# Kế hoạch review từ lỗi quan sát được

Từ B2-mid, tôi chọn hai frame cần xem lại trước. Đây là dữ liệu của một camera; kế hoạch 200 frame cho bốn camera nằm trong `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| `adasind_060000.jpg` | Bản tôi thiếu 5 box so với reference; thiếu `ego_body` | Vừa thiếu box vừa thiếu vùng ignore nên tôi kiểm frame này trước | ảnh gốc, `compare.html`, QA overlay và screenshot B2-mid |
| `adasind_102750.jpg` | Bản tôi thiếu 5 box so với reference; frame đã cắt theo time-box | Các box này là phần chưa làm, không dùng để kết luận model sai | `mode.json`, `compare.md`, local-quality conflicts |

Ba frame ADASIND chỉ thuộc một camera và frame thứ ba đã bị cắt theo time-box. Vì vậy các tỷ lệ thiếu ở đây không đại diện cho cả hệ thống SVM. Teaching reference cũng chưa phải gold set.

## Chuyển sang kế hoạch bốn camera giả lập

Tôi chia 200 frame theo `camera_id × normal/hard`, rải theo thời gian và bối cảnh, rồi bỏ các frame gần trùng trước khi lấy đủ 25 frame mỗi ô. Đây mới là kế hoạch lấy mẫu; chưa có nhãn gold nên chưa dùng để tính tỷ lệ lỗi.
