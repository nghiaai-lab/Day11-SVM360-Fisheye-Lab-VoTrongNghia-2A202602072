# Hồ sơ cá nhân và đóng góp vai B — Võ Trọng Nghĩa · 2A202602072

## Bài cá nhân B2-mid

Repo cá nhân đã hoàn tất bộ hiện vật P0–P6 và `lab11.py check` đạt ngày 2026-09-29. Các bằng chứng chính gồm:

- P0: [parking XML](submission/parking/annotations.xml) và [observations](submission/parking/observations.md).
- P1: [C0 XML](submission/p1_calib/annotations.xml), [lock C0](submission/p1_calib/lock.txt) và [compare C0](submission/p1_calib/compare.md).
- P2: slice `B2-mid`, [lock `7C9C-5D86`](submission/r1_craft/lock.txt), [Self-QC](submission/r1_craft/selfqc.md) và [compare](submission/r1_craft/compare.md).
- P3–P4: [QA mù B2-mid](submission/r2_qa/qa_review.md), [findings](submission/findings.csv), [local quality](submission/r3_diag/local_quality.md) và [zone table](submission/r3_diag/zone_table.md).
- P5–P6: [delta rework](submission/rework/delta.md), [guideline patch](submission/20_guideline_patch.md), [escalation ticket](submission/30_escalation_ticket.md), [review plan](submission/45_review_plan.md) và [exit ticket](submission/50_exit_ticket.md).

Theo time-box chính thức, bài đã chạy `degrade frame3` và `degrade k12`. Bản B2-mid dùng support prefill (`prefill_kept=8`, `prefill_edited=0`, `new=0`), còn thiếu `ego_body` trên ba frame và rework không thay đổi XML. Hồ sơ ghi rõ các hạn chế này; không nhận là đã sửa hoặc đạt chất lượng tối đa.

## Đóng góp QA trong nhóm

[Repo nhóm K4-DAY11-Lab11](https://github.com/DTKien2005/K4-DAY11-Lab11) giữ hồ sơ tích hợp A → B → C; [TEAMMATES.md của nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md) ghi phân vai và bàn giao. Các export B4-center và bản sửa v2 thuộc người gán nhãn Nguyễn Trí Tín. Nghĩa thực hiện QA và đưa finding, không nhận các export đó là nhãn cá nhân của mình.

## Bằng chứng do Nghĩa thực hiện

| Pha | Việc và kết quả | Bằng chứng trong repo cá nhân | Nguồn nhóm |
|---|---|---|---|
| P0 | Soát vạch parking và `free_space` của A; giữ riêng hai nét sát mép là ca cần xác nhận thêm. | [Ghi chú parking](submission/parking/b_review_notes.md) | [Export parking của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/parking/annotations.xml) |
| P1 | Soát C0; nêu ca L2 người dắt xe cần tách `Pedestrian` và `Bike` theo R03. | [Ghi chú C0](submission/p1_calib/b_review_notes.md) | [Bản C0 đã khóa của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/p1_calib/lock.txt) |
| P3 | Nhận B4-center đã khóa `6997-BF13`, kiểm SHA-256 `6997bf13e8daac9ae1cbf02fa422682f9eb3b960cc2812c21d587eaa9293e7f0`; QA mù đủ ba ảnh trước reference/model. | [Tiếp nhận](submission/r2_qa/qa_intake.md), [review B4-center](submission/r2_qa/qa_review_B4-center.md), [overlay](submission/r2_qa/qa_overlay.html), [ảnh chụp](submission/screenshots/qa_B_295948_overlay.png) | [Lock bản đầu của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/r1_craft/lock.txt) |
| P3 | Ghi bốn finding xác nhận ở `adasind_295948.jpg`: ba thuộc tính `occluded` L4/L5/L7 cần kiểm sửa và một box `Car` cao 26,99 px dưới ngưỡng R01. Giữ riêng các ca chưa đủ căn cứ ở `270517` và `271039`; không gọi chúng là lỗi đã xác nhận. | [Chi tiết B4-center](submission/r2_qa/qa_review_B4-center.md) | [Bàn giao P3 trên TEAMMATES](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md) |
| P5 | Bảng bàn giao nhóm ghi B đã kiểm bản sửa khóa `9313-188F` và xác nhận đạt. Đối chiếu XML v2 khi chuẩn bị nộp cho thấy box dưới H=40 đã bỏ, nhưng L4/L5 vẫn có custom `occluded=false`, còn L7 đã bị bỏ thay vì đổi thuộc tính. Vì vậy chưa thể xác nhận ba finding thuộc tính đã được xử lý như bảng bàn giao ghi. | [Đối chiếu P5 bổ sung](submission/rework/b_recheck.md) | [Bảng bàn giao](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md), [lock v2](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/rework/lock2.txt), [delta](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/rework/delta.md) |

## Ranh giới giữa bài cá nhân và bằng chứng nhóm

- [Manifest nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/manifest.json) ghi `failed_gates: []` cho **hồ sơ tích hợp**, không phải xác nhận `lab11.py check` của repo cá nhân này.
- `submission/00_setup/mode.json` giao `B2-mid` cho bài cá nhân. Nhóm đã làm trên slice chung `B4-center` với ba vai A/B/C; review B4-center là bằng chứng đóng góp thêm.
- Bảng thành viên trong [README nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/README.md) còn ghi `B2-mid` và gắn `Parking Lock` ở dòng Nghĩa; điều này không khớp TEAMMATES và lịch sử commit. Repo cá nhân này không nhận bản gán nhãn parking/B2-mid đó là sản phẩm của Nghĩa.
- `submission/findings.csv` hiện là bảng finding của bài cá nhân B2-mid. Bốn finding B4-center trước đây được lưu trong [review B4-center](submission/r2_qa/qa_review_B4-center.md) và [ghi chú P5 nhóm](submission/rework/b_recheck.md).
- `lab11.py check` đã đạt trên repo cá nhân. Kết quả này xác nhận đủ cấu trúc; các cảnh báo chất lượng được giữ nguyên để người chấm đánh giá theo rubric.
