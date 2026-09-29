# Guideline patch

- **Rule mới đề xuất:** Trước khi khóa, mỗi frame ngoài danh sách ngoại lệ phải có ít nhất một `ignore_region` với `reason=ego_body`; nếu không xác định được biên thì ghi finding `IGNORE_SCOPE`, chụp ảnh và escalation, không tự đánh dấu đạt.
- **Áp dụng cho:** `ignore_region.reason=ego_body`, đặc biệt các cấu trúc sát camera ở mép trái/dưới.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** R07 yêu cầu vẽ nhưng chưa nêu rõ cổng bàn giao khi support-prefill chỉ chứa `lens_border`. Trong B2-mid, `adasind_060000.jpg` và `adasind_086220.jpg` qua được bước import nhưng self-QC mới phát hiện thiếu ego body.
- **`rules_version` mới:** v1.0.0 → v1.1.0.
- **Hiệu lực từ:** áp dụng từ self-QC P2 và mọi vòng khóa sau đó.
