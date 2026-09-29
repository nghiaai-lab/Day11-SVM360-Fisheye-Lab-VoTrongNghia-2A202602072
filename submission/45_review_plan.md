# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| `adasind_060000.jpg` | 5 reference-only box; thiếu `ego_body` | Có cả thiếu vật center/mid và lỗi phạm vi, ảnh hưởng hai nhóm tiêu chí | ảnh gốc, `compare.html`, QA overlay và screenshot B2-mid |
| `adasind_102750.jpg` | 5 reference-only box do frame bị cắt time-box | Là giới hạn lớn nhất của chế độ rút gọn; cần tách rõ “chưa làm” khỏi lỗi model | `mode.json`, `compare.md`, local-quality conflicts |

Giới hạn của kết luận từ ba frame ADASIND: đây là một camera, chỉ ba thời điểm và frame thứ ba bị cắt theo time-box. Teaching reference có thể sai; các tỷ lệ thiếu không đại diện cho toàn hệ thống SVM hay dữ liệu vận hành.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: chia tầng `camera_id × normal/hard`, rải theo thời gian/bối cảnh và loại frame gần trùng trước khi lấy đủ 25 mỗi ô. Phân bổ này chỉ bảo đảm độ phủ thiết kế; chưa có nhãn gold hoặc mẫu ngẫu nhiên đại diện nên không dùng để ước lượng tỷ lệ lỗi.
