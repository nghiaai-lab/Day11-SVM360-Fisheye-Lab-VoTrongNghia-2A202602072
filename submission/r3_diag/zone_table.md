# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 9 | 6 | 0 | 5 | 8 | MISSING (6) |
| mid | 8 | 4 | 0 | 4 | 10 | MISSING (4) |
| edge | 3 | 2 | 0 | 2 | 0 | MISSING (2) |

## Nhận xét

- Bản L thiếu nhiều nhất ở `center`: 6/9 reference; tiếp theo `mid` 4/8 và `edge` 2/3. Model có nhiều box thừa nhất ở `mid` (10), rồi `center` (8), trong khi `edge` không có box thừa.
- Nguyên nhân chắc chắn của L là dùng support-prefill và cắt frame thứ ba theo time-box nên recall thấp; hai frame giữ lại cũng còn thiếu `ego_body`. Với model, méo fisheye và vật nhỏ/nền đông là giả thuyết cần kiểm trên ảnh, không thể kết luận chỉ từ ba frame. Teaching reference là đối chứng dạy học, không phải gold set sản xuất.
