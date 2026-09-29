# Escalation ticket

## Ticket 1

- **Frame:** `adasind_060000.jpg` và cùng lỗi trên `adasind_086220.jpg`.
- **Ảnh chụp:** `submission/screenshots/b2_mid_frame0_support.png`.
- **Expected impact:** thiếu `ego_body` làm vùng phạm vi không đầy đủ; các box sát camera có thể được tính sai là vật cần so sánh. Recall của bản khóa cũng thấp vì support-prefill và time-box.
- **Owner:** `qa` phối hợp `annotator`.
- **Recommendation:** mở lại hai frame, vẽ polygon sát phần thân xe thật sự nhìn thấy và khóa lại; nếu không phân định được biên, giữ escalation và nhờ Lab Coach xác nhận thay vì chép reference.
