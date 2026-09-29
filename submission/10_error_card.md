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

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: lỗi nổi bật là `MISSING`. Ở B2-mid, các dòng `RM_noL` có reference và model cùng thấy nhưng L thiếu nên gán `E1_annotator_error`; các dòng `R_only` chỉ có reference được giữ `E5_unresolved`. Frame `102750` bị cắt time-box giải thích 5 box thiếu, còn hai frame giữ lại dùng support-prefill nhưng chưa rà đủ vật.
- Cách sửa và ai nhận việc (`owner`): annotator mở lại hai frame bắt buộc, bổ sung vật đạt H=40 và `ego_body`, sau đó QA soát lạnh và khóa mới. Ca `R_only` chuyển QA/Lab Coach phân xử; box chỉ model có được giữ `E4_model_domain`, không tự thêm.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): `submission/screenshots/b2_mid_frame0_support.png`, các dòng B2-mid trong `findings.csv`, `r1_craft/compare.md`, `local_quality_conflicts.csv`, cùng R01, R02 và R07.
