# QA lạnh · B2-mid

- Người làm và tự soát: Võ Trọng Nghĩa (`nghia`).
- Mã khóa nhận soát: `7C9C-5D86`.
- SHA-256: `7c9c5d8635cab4a8789fba141ed68b4e9078f333ea24e43fd06ae241b46ea6e9`.
- Thứ tự: khóa bản cá nhân rồi chạy QA trước khi mở teaching reference.
- Chế độ thời gian: `frame3` và `k12` đã được ghi trong `mode.json`; hai frame đầu là phạm vi bắt buộc của bản rút gọn.

## adasind_060000.jpg

- L1, L2, L3 `ThreeWheeler`: các box đạt H=40 và bám phương tiện nhìn thấy; L3 chạm biên phải, `truncated=true` phù hợp R05.
- L4 và L5 `Pedestrian`: hai box tách riêng ở vùng trái. Chưa suy nguyên nhân hoặc đổi class khi chưa đối chiếu kỹ tư thế rider theo R03.
- Hai polygon `lens_border` có `reason` đúng. Self-QC phát hiện chưa có polygon `ego_body` cho phần cấu trúc sát camera ở mép trái dưới; đây là finding phạm vi theo R07.

## adasind_086220.jpg

- L1 `ThreeWheeler` chạm biên phải và có `truncated=true`, phù hợp R05.
- L2 `Bike` và L3 `ThreeWheeler` đều đạt H=40; chưa thấy box trùng cùng class IoU cao.
- Hai polygon `lens_border` có `reason` đúng. Self-QC phát hiện thiếu `ego_body` ở mép trái dưới theo R07.

## adasind_102750.jpg

- Frame thứ ba được cắt theo time-box `degrade frame3`; export vẫn giữ hai `lens_border` nhưng không dùng frame này để nhận hoàn thành gán nhãn cá nhân.
- Không tạo finding vật thể từ frame đã cắt giảm.

## Kết luận QA trước reference

1. Giữ các box support-prefill đã kiểm về ngưỡng, class chính và trạng thái truncated; bản khóa ghi `prefill_kept=8`, `prefill_edited=0`, `new=0` để người chấm thấy rõ nguồn.
2. Hai finding chắc chắn là thiếu `ego_body` trên `adasind_060000.jpg` và `adasind_086220.jpg`; giữ trạng thái mở, không ghi đã sửa.
3. Metadata của job export không chứa tên task dù task trên CVAT được tạo với chuỗi `raw_fisheye`; ghi giới hạn này thay vì sửa XML khóa.

Báo cáo QA nhóm B4-center trước đây được bảo toàn tại `qa_review_B4-center.md`; nó không thay QA lạnh của slice cá nhân này.
