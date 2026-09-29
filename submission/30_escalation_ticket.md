# Escalation ticket

## Ticket 1

- **Frame:** `adasind_060000.jpg` và cùng lỗi trên `adasind_086220.jpg`.
- **Ảnh chụp:** `submission/screenshots/b2_mid_frame0_support.png`.
- **Expected impact:** thiếu `ego_body` có thể làm các box sát camera bị tính nhầm vào vùng hợp lệ. Bản khóa cũng có recall thấp; bài này dùng support prefill và time-box.
- **Owner:** `qa` phối hợp `annotator`.
- **Recommendation:** mở lại hai frame, chỉ vẽ phần thân xe nhìn thấy rồi khóa lại. Nếu chưa chắc biên, tôi sẽ giữ ticket để hỏi Lab Coach, không chép theo reference.
