# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy
   tắc riêng? Vì sao? Tôi chưa gọi hai box ở seam là `DUPLICATE` vì mỗi box có thể đúng trên ảnh của từng camera. Chỉ gộp khi output yêu cầu một vật duy nhất và có timestamp, calibration cùng quy tắc ghép rõ ràng.
2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Tôi giữ track ID khi vẫn nhận ra cùng vật trên các frame liên tiếp. Tôi thêm keyframe khi box hoặc attribute đổi và đặt Outside khi vật ra khỏi vùng nhìn. Muốn nối qua camera khác thì cần timestamp đồng bộ, calibration vùng seam và quy tắc tracking đã thống nhất.
3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm? Ở C0 `adasind_019560.jpg`, tôi tách người áo vàng thành L3 `Pedestrian` và chiếc xe thành một box `Bike`. Compare lại báo L3 là `SPURIOUS` và có R5 `MISSING`, nên cách gộp của reference khác bản tôi làm. Tôi giữ kết quả compare trong findings, không sửa bản đã khóa. Nếu làm lại, tôi sẽ phóng ảnh để xác định người đó có đang ngồi/điều khiển xe hay không rồi áp dụng R03 trước khi vẽ.
