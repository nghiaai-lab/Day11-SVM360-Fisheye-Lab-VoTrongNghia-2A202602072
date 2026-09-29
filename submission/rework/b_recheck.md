# Tôi kiểm lại bản P5 của nhóm

Tôi kiểm lại ngày 29/09/2026 bằng [QA P3 B4-center](../r2_qa/qa_review_B4-center.md), [ảnh QA](../screenshots/qa_B_295948_overlay.png) và [XML v2 của nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/rework/annotations-v2.xml).

- XML v2 có SHA-256 `9313188f1a2e8609768b9a2b3293378ec9c34ef796448fced8af9a05c9dbc2ee`, khớp [lock2](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/rework/lock2.txt) mã `9313-188F`.
- Box `Car` cao 26,99 px ở `adasind_295948.jpg` đã được bỏ, đúng yêu cầu R01 tôi ghi ở P3.
- L4 Bike và L5 Pedestrian vẫn có custom attribute `occluded=false`. Cờ `occluded="1"` trên shape là trường khác, nên tôi chưa tính hai finding này là đã sửa.
- L7 Truck không còn trong XML v2. Delta nhóm ghi box này là `SPURIOUS`. Vì box đã bị bỏ nên không thể nói thuộc tính cũ đã được đổi sang `true`.

[TEAMMATES.md](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md) ghi cả ba thuộc tính đã đổi sang `true`, nhưng XML v2 không cho thấy điều đó. Vì vậy L4 và L5 vẫn cần nhóm kiểm lại. `findings.csv` của nhóm cũng khác bốn finding tôi đã ghi, nên tôi giữ file review B4-center riêng để thầy đối chiếu.
