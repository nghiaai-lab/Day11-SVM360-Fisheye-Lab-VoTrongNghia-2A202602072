# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ là hai đoạn sơn chéo nhìn thấy ở vùng tiền cảnh bên trái: một đoạn sát mép trái và một đoạn nằm chếch vào phía giữa ảnh. Mỗi polyline chỉ bám phần sơn đang nhìn thấy và dừng tại hai đầu đoạn sơn.
- Không vẽ đường biên ngang dài ở phần giữa–xa của bãi vì nó thể hiện mép/lối xe chạy, không tạo ranh giới cho một ô đỗ riêng lẻ.
- Polygon `free_space` bao phần mặt đường trống nhìn thấy ở tiền cảnh, dừng trước vùng giữa–xa của bãi và không đi qua chiếc xe đang đỗ. Trong vùng đã chọn không có phần bị xe hoặc vật cản che khuất đáng kể.
- Ca chưa chắc cần hỏi người soát: không có.
