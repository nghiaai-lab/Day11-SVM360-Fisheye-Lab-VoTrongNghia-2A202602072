# Bài cá nhân và phần QA nhóm — Võ Trọng Nghĩa · 2A202602072

## Bài cá nhân B2-mid

Tôi đã lưu đủ các file P0–P6 để `lab11.py check` chạy đạt ngày 29/09/2026. Các phần còn thiếu về nhãn được ghi ở Self-QC và QA.

- P0: [parking XML](submission/parking/annotations.xml) và [observations](submission/parking/observations.md).
- P1: [C0 XML](submission/p1_calib/annotations.xml), [lock C0](submission/p1_calib/lock.txt) và [compare C0](submission/p1_calib/compare.md).
- P2: slice `B2-mid`, [lock `7C9C-5D86`](submission/r1_craft/lock.txt), [Self-QC](submission/r1_craft/selfqc.md) và [compare](submission/r1_craft/compare.md).
- P3–P4: [QA mù B2-mid](submission/r2_qa/qa_review.md), [findings](submission/findings.csv), [local quality](submission/r3_diag/local_quality.md) và [zone table](submission/r3_diag/zone_table.md).
- P5–P6: [delta rework](submission/rework/delta.md), [guideline patch](submission/20_guideline_patch.md), [escalation ticket](submission/30_escalation_ticket.md), [review plan](submission/45_review_plan.md) và [exit ticket](submission/50_exit_ticket.md).

Bài dùng `degrade frame3` và `degrade k12`. B2-mid dùng support prefill (`prefill_kept=8`, `prefill_edited=0`, `new=0`). Hai frame phải làm vẫn thiếu `ego_body`; frame thứ ba đã cắt. Bản rework chưa đổi XML nên tôi không tính các lỗi này là đã sửa.

## Đóng góp QA trong nhóm

[Repo nhóm K4-DAY11-Lab11](https://github.com/DTKien2005/K4-DAY11-Lab11) lưu phần việc chung của A, B và C; [TEAMMATES.md](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md) ghi phân vai. B4-center và bản v2 do Nguyễn Trí Tín gán/sửa; tôi chỉ soát và gửi finding, không tính các export đó là nhãn mình vẽ.

## Phần tôi làm trong nhóm

| Pha | Việc và kết quả | Bằng chứng trong repo cá nhân | Nguồn nhóm |
|---|---|---|---|
| P0 | Tôi soát parking và `free_space` của A; hai nét sát mép vẫn cần xem lại. | [Ghi chú parking](submission/parking/b_review_notes.md) | [Export parking của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/parking/annotations.xml) |
| P1 | Tôi soát C0 và đề nghị tách L2 thành `Pedestrian` và `Bike` theo R03 vì người đang dắt xe. | [Ghi chú C0](submission/p1_calib/b_review_notes.md) | [Bản C0 đã khóa của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/p1_calib/lock.txt) |
| P3 | Tôi nhận B4-center khóa `6997-BF13`, kiểm SHA-256 khớp rồi soát ba ảnh trước khi mở reference/model. | [Tiếp nhận](submission/r2_qa/qa_intake.md), [review B4-center](submission/r2_qa/qa_review_B4-center.md), [overlay](submission/r2_qa/qa_overlay.html), [ảnh chụp](submission/screenshots/qa_B_295948_overlay.png) | [Lock bản đầu của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/r1_craft/lock.txt) |
| P3 | Tôi chốt bốn finding ở `adasind_295948.jpg`: L4/L5/L7 cần kiểm `occluded` và một box `Car` cao 26,99 px dưới ngưỡng. Các chỗ chưa chắc ở `270517` và `271039` tôi để mở. | [Chi tiết B4-center](submission/r2_qa/qa_review_B4-center.md) | [Bàn giao P3 trên TEAMMATES](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md) |
| P5 | `TEAMMATES.md` ghi B đã kiểm bản `9313-188F`. XML v2 đã bỏ box dưới H=40, nhưng L4/L5 vẫn là `occluded=false` và L7 không còn. Vì vậy tôi chưa tính ba ca thuộc tính là đã sửa xong. | [Đối chiếu P5](submission/rework/b_recheck.md) | [Bảng bàn giao](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md), [lock v2](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/rework/lock2.txt), [delta](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/rework/delta.md) |

## Bài của tôi và bài nhóm

- [Manifest nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/manifest.json) là kết quả check bài chung. Bài cá nhân của tôi có manifest riêng trong repo này.
- `submission/00_setup/mode.json` giao B2-mid cho tôi. B4-center là bài chung và review đó là phần tôi làm thêm với nhóm.
- [README nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/README.md) còn gắn B2-mid/Parking Lock với tên tôi, nhưng phần này không khớp `TEAMMATES.md` và lịch sử commit. Tôi chỉ tính phần nào có file và commit đối chiếu được.
- `submission/findings.csv` hiện dùng cho B2-mid. Bốn finding B4-center cũ nằm trong [review B4-center](submission/r2_qa/qa_review_B4-center.md) và [ghi chú P5](submission/rework/b_recheck.md).
- `lab11.py check` đã đạt trên repo cá nhân. Tôi vẫn giữ các cảnh báo chưa sửa để thầy xem đúng tình trạng bài.
