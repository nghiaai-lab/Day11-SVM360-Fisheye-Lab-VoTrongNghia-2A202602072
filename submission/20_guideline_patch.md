# Guideline patch

- **Rule mới đề xuất:** Trước khi khóa, tôi sẽ kiểm mỗi frame có nhìn thấy thân xe hay không. Nếu có thì phải có `ignore_region` với `reason=ego_body`. Nếu chưa chắc biên, ghi `IGNORE_SCOPE`, chụp ảnh và hỏi người soát.
- **Áp dụng cho:** `ignore_region.reason=ego_body`, đặc biệt các cấu trúc sát camera ở mép trái/dưới.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** R07 yêu cầu vẽ `ego_body` nhưng chưa nói phải kiểm gì trước khi khóa nếu support prefill chỉ có `lens_border`. Hai frame `060000` và `086220` import được nhưng đến Self-QC tôi mới thấy thiếu vùng này.
- **`rules_version` mới:** v1.0.0 → v1.1.0.
- **Hiệu lực từ:** dùng từ bước Self-QC P2 và các lần khóa sau.
