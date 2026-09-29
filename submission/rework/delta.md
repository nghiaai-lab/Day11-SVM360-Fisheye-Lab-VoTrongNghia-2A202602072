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

## Giải thích

Tôi chưa sửa được bốn ca này trong CVAT. Bản v2 giữ nguyên bản đầu (`7C9C-5D86`) nên số trước và sau không đổi; các finding vẫn đang mở. Frame `102750` đã cắt theo time-box nên tôi không đưa các ca của frame đó vào danh sách rework.
