# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 9 | 6 | 0 | 5 | 8 | MISSING (6) |
| mid | 8 | 4 | 0 | 4 | 10 | MISSING (4) |
| edge | 3 | 2 | 0 | 2 | 0 | MISSING (2) |

## Nhận xét

- Bản của tôi thiếu nhiều nhất ở `center`: 6/9 box reference; sau đó là `mid` 4/8 và `edge` 2/3. Model có 10 box thừa ở `mid`, 8 box ở `center` và không có box thừa ở `edge`.
- Tôi giữ 8 box support prefill và bỏ frame thứ ba, nên số box thiếu cao là điều dễ hiểu. Với hai frame đầu, tôi vẫn phải xem từng ca trên ảnh mới biết lý do. Hai frame này còn thiếu `ego_body`, nhưng bảng trên chỉ đếm box. Ba frame chưa đủ để kết luận lỗi chung của model hoặc dữ liệu fisheye.
