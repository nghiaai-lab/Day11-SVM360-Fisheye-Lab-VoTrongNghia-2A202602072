# QA lạnh · B2-mid

- Người làm và tự soát: Võ Trọng Nghĩa (`nghia`).
- Mã khóa nhận soát: `7C9C-5D86`.
- SHA-256: `7c9c5d8635cab4a8789fba141ed68b4e9078f333ea24e43fd06ae241b46ea6e9`.
- Tôi khóa bản cá nhân rồi mới chạy QA và mở teaching reference sau.
- Tôi chỉ làm hai frame đầu theo `degrade frame3`; phần K12 cũng được bỏ.

## adasind_060000.jpg

- Tôi giữ L1, L2, L3 là `ThreeWheeler`; cả ba box đạt H=40. L3 chạm biên phải nên `truncated=true` phù hợp R05.
- L4 và L5 là hai `Pedestrian` tách riêng ở vùng trái. Tôi chưa đổi class khi chưa kiểm kỹ tư thế rider theo R03.
- Hai polygon `lens_border` có `reason` đúng. XML chưa có `ego_body` ở mép trái dưới; tôi ghi lại để kiểm theo R07.

## adasind_086220.jpg

- L1 `ThreeWheeler` chạm biên phải và có `truncated=true`, phù hợp R05.
- L2 `Bike` và L3 `ThreeWheeler` đều đạt H=40. Tôi chưa thấy box cùng class bị trùng.
- Hai polygon `lens_border` có `reason` đúng. XML vẫn thiếu `ego_body` ở mép trái dưới theo R07.

## adasind_102750.jpg

- Tôi cắt frame thứ ba theo `degrade frame3`. Export chỉ còn hai `lens_border`; frame này chưa được tính là đã gán nhãn.
- Tôi không ghi lỗi vật thể riêng cho frame đã cắt.

## Kết luận QA trước reference

1. Tôi giữ 8 box từ support prefill sau khi kiểm (`prefill_kept=8`, `prefill_edited=0`, `new=0`). Tôi chưa thêm hoặc sửa box nào.
2. XML của `adasind_060000.jpg` và `adasind_086220.jpg` chưa có `ego_body`. Tôi để hai finding này mở vì vẫn cần kiểm biên trên ảnh.
3. Task CVAT có `raw_fisheye` trong tên nhưng file export không lưu tên task. Tôi không sửa XML đã khóa.

Tôi để báo cáo QA nhóm B4-center trong `qa_review_B4-center.md`. File đó là phần nhóm, còn file này là QA của B2-mid.
