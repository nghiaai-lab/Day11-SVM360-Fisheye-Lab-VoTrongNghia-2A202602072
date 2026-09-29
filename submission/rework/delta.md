# Rework delta

| zone | matched before | matched after | missing before | missing after | spurious before | spurious after |
|---|---:|---:|---:|---:|---:|---:|
| center | 3 | 3 | 6 | 6 | 0 | 0 |
| mid | 4 | 4 | 4 | 4 | 0 | 0 |
| edge | 1 | 1 | 2 | 2 | 0 | 0 |

## Findings action=rework
- adasind_060000.jpg R5+M4 MISSING: chưa sửa
- adasind_060000.jpg R7+M6 MISSING: chưa sửa
- adasind_086220.jpg R2+M1 MISSING: chưa sửa
- adasind_086220.jpg R3+M4 MISSING: chưa sửa
- adasind_102750.jpg R1+M1 MISSING: chưa sửa
- adasind_102750.jpg R2+M2 MISSING: chưa sửa
- adasind_102750.jpg R5+M8 MISSING: chưa sửa

## Giải thích

Bản rework khóa cùng nội dung với bản r1 (`7C9C-5D86`), nên các số trước/sau không đổi. Không có thao tác CVAT đủ căn cứ và thời gian để đóng các finding; giữ chúng ở trạng thái chưa sửa và escalation thay vì sửa XML bằng tay hoặc nhận đã cải thiện.
