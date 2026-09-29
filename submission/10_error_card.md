# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B2 | MISSING | 15 |
| center | B2 | SPURIOUS | 8 |
| center | B4 | ATTRIBUTE | 1 |
| center | C0 | MISSING | 1 |
| center | C0 | SPURIOUS | 2 |
| edge | B2 | MISSING | 5 |
| mid | B2 | MISSING | 10 |
| mid | B2 | SPURIOUS | 10 |
| mid | B4 | ATTRIBUTE | 2 |
| unknown | B2 | IGNORE_SCOPE | 2 |
| unknown | B4 | SPURIOUS | 1 |

## Top defects
- MISSING: 31 (ví dụ frame adasind_019560.jpg)
- SPURIOUS: 21 (ví dụ frame adasind_295948.jpg)
- ATTRIBUTE: 3 (ví dụ frame adasind_295948.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`.

- Lỗi nhiều nhất là `MISSING`. Frame `102750` có 5 box thiếu vì tôi đã cắt frame này theo time-box. Ở hai frame đầu, reference và model cùng có một số vật mà bản của tôi chưa có; tôi cần mở ảnh kiểm từng ca trước khi kết luận nguyên nhân.
- Tôi cần mở lại hai frame bắt buộc, thêm các vật đạt H=40 và `ego_body`, rồi nhờ QA soát và khóa lại. Ca chỉ có reference hoặc chỉ có model vẫn để `E5_unresolved`, không tự thêm box.
- Tôi dùng ảnh `submission/screenshots/b2_mid_frame0_support.png`, các dòng B2-mid trong `findings.csv`, `r1_craft/compare.md`, `local_quality_conflicts.csv` và các rule R01, R02, R07 để kiểm lại.
