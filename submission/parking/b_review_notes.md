# Ghi chú QA P0 của tôi — vai B

Tôi soát file parking của Tín ở commit `00f969b`, đối chiếu với ảnh `parking-lot-core.jpg` và `docs/11-parking-lines-vi.md`. XML này trùng với file nhóm đã gửi cho tôi.

Bằng chứng nguồn: [XML parking đã soát](https://github.com/DTKien2005/Day11-SVM360-Fisheye-Lab-Student/blob/00f969b16d08b95247c7139dbc7bf8917a00879f/submission/parking/annotations.xml), [quan sát của A](https://github.com/DTKien2005/Day11-SVM360-Fisheye-Lab-Student/blob/00f969b16d08b95247c7139dbc7bf8917a00879f/submission/parking/observations.md), [ảnh gốc](../../assets/parking/parking-lot-core.jpg).

- `parking_line` 1 và 2: tôi thấy đây là vạch chia ô nên có thể giữ.
- `parking_line` 3 ở mép trái: đoạn sơn quá ngắn. Tôi hỏi lại Tín xem nó có thật sự chia một ô riêng hay chỉ bị cắt bởi khung ảnh.
- `parking_line` 4 ở mép phải: Tín cũng ghi là chưa chắc. Tôi chưa yêu cầu xóa chỉ vì nét này ngắn.
- `free_space`: phần khoanh nhìn chung nằm trên mặt đường trống phía trước. Cần nhìn kỹ quanh nét 1 và 2 để tránh lấn sang ô đỗ.
- Tôi đồng ý không gán đường sáng ngang phía xa (khoảng y=465), vì nó chạy dọc lối đi chứ không chia hai ô.

File có đúng ảnh, 4 polyline `parking_line` và 1 polygon `free_space`. Tôi vẫn để nét 3, nét 4 và biên `free_space` ở trạng thái cần xem lại trên ảnh. Đây chỉ là ghi chú parking, không phải QA fisheye ở P3.
