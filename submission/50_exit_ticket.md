# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy
   tắc riêng? Vì sao? Hai box có thể đều đúng trong không gian ảnh gốc của từng camera; cần policy seam riêng. Chỉ gọi `DUPLICATE` khi output đích yêu cầu một đối tượng duy nhất và có timestamp đồng bộ, calibration cùng quy tắc hợp nhất để chứng minh hai box là cùng vật.
2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Trong cùng camera, giữ track ID khi quan sát liên tục cùng danh tính; thêm keyframe khi hình học/attribute đổi và đặt Outside tại frame vật rời vùng nhìn. Muốn nối qua hai camera cần timestamp đồng bộ, calibration/vùng seam, tín hiệu nhận dạng và policy output đã được duyệt.
3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm? Ở `adasind_060000.jpg`, L1/L2/L3 khớp reference nhưng model không có (`LR_noM`), nên giữ nhãn người và ghi `E4_model_domain` thay vì xóa theo model. Nếu làm lại, tôi sẽ vẽ `ego_body` trước, rà đủ vật theo H=40 trên từng frame rồi mới dùng support-prefill.
