# Hồ sơ cá nhân — Võ Trọng Nghĩa · 2A202602072 · Vai B

Repo này là chỉ mục bằng chứng **QA độc lập** của Nghĩa trong nhóm Day 11 SVM/360 Fisheye. [Repo nhóm K4-DAY11-Lab11](https://github.com/DTKien2005/K4-DAY11-Lab11) giữ hồ sơ tích hợp A → B → C; [TEAMMATES.md của nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md) ghi rõ phân vai và bàn giao. Các export nhãn parking, C0, B4-center và bản sửa v2 là phần của người gán nhãn Nguyễn Trí Tín. Nghĩa soát và đưa finding; không nhận các export đó là nhãn do mình vẽ.

## Bằng chứng do Nghĩa thực hiện

| Pha | Việc và kết quả | Bằng chứng trong repo cá nhân | Nguồn nhóm |
|---|---|---|---|
| P0 | Soát vạch parking và `free_space` của A; giữ riêng hai nét sát mép là ca cần xác nhận thêm. | [Ghi chú parking](submission/parking/b_review_notes.md) | [Export parking của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/parking/annotations.xml) |
| P1 | Soát C0; nêu ca L2 người dắt xe cần tách `Pedestrian` và `Bike` theo R03. | [Ghi chú C0](submission/p1_calib/b_review_notes.md) | [Bản C0 đã khóa của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/p1_calib/lock.txt) |
| P3 | Nhận B4-center đã khóa `6997-BF13`, kiểm SHA-256 `6997bf13e8daac9ae1cbf02fa422682f9eb3b960cc2812c21d587eaa9293e7f0`; QA mù đủ ba ảnh trước reference/model. | [Tiếp nhận](submission/r2_qa/qa_intake.md), [review](submission/r2_qa/qa_review.md), [overlay](submission/r2_qa/qa_overlay.html), [ảnh chụp](submission/screenshots/qa_B_295948_overlay.png) | [Lock bản đầu của A](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/r1_craft/lock.txt) |
| P3 | Ghi bốn finding xác nhận ở `adasind_295948.jpg`: ba thuộc tính `occluded` L4/L5/L7 cần kiểm sửa và một box `Car` cao 26,99 px dưới ngưỡng R01. Giữ riêng các ca chưa đủ căn cứ ở `270517` và `271039`; không gọi chúng là lỗi đã xác nhận. | [Bốn dòng `r2_qa`](submission/findings.csv), [chi tiết theo frame](submission/r2_qa/qa_review.md) | [Finding trong hồ sơ nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/findings.csv) |
| P5 | [Bảng bàn giao nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md) ghi B đã kiểm bản sửa khóa `9313-188F` và xác nhận đạt: bỏ một box dưới H=40, cập nhật ba `occluded=true`. Đây là xác nhận lưu trong hồ sơ nhóm; repo cá nhân chưa có một biên bản P5 độc lập khác. | [Review gốc để đối chiếu](submission/r2_qa/qa_review.md) | [Lock v2](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/rework/lock2.txt), [delta](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/rework/delta.md) |

## Ranh giới khi chấm

- [Manifest nhóm](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/submission/manifest.json) ghi `failed_gates: []` cho **hồ sơ tích hợp**, không phải xác nhận `lab11.py check` của repo cá nhân này.
- `submission/00_setup/mode.json` trong repo cá nhân ghi `B2-mid` theo cơ chế chia slice của CLI; nhóm đã làm trên slice chung `B4-center` với ba vai A/B/C như [TEAMMATES.md](https://github.com/DTKien2005/K4-DAY11-Lab11/blob/main/TEAMMATES.md). Bằng chứng QA của Nghĩa là review B4-center của A.
- Nếu yêu cầu lớp là mỗi người **chỉ nộp vai được phân**, hãy đọc repo này cùng repo nhóm. Nếu yêu cầu là mỗi người phải tự hoàn tất toàn bộ P0–P6, repo cá nhân này chưa đủ bộ hiện vật đó.
