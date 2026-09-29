# QA B4-center tôi làm cho nhóm

- Người soát: Võ Trọng Nghĩa (`nghia`), vai B.
- Bản nhãn của Nguyễn Trí Tín, vai A.
- Commit nhận file: `d7862e5cc9611907fd907d43287bb36c2c8f2111`.
- Mã khóa: `6997-BF13`.
- SHA-256: `6997bf13e8daac9ae1cbf02fa422682f9eb3b960cc2812c21d587eaa9293e7f0`.
- Tôi xem cả ba ảnh trước khi mở reference, model hoặc compare.

## adasind_270517.jpg

- Tôi thấy L1–L7 nhìn chung đúng class và box bám phần vật nhìn thấy.
- L1 bị vật phía trước che một phần nên `occluded=true` hợp lý.
- L3 chạm mép phải nên `truncated=true` hợp lý.
- Có một vùng tối phía sau L2 trông giống phương tiện, nhưng tôi chưa chắc đó là vật riêng và có đạt H=40 hay không. Tôi không ghi thành lỗi thiếu box.
- Hai vùng ignore nhìn chung bám vòng kính và phần xe gần camera; nếu sửa tiếp thì cần phóng ảnh để kiểm biên.

## adasind_271039.jpg

- Các class chính là `Car`, `ThreeWheeler` và `Pedestrian` nhìn chung hợp lý.
- L7, L8, L9 có cờ `occluded` gốc bằng 1 nhưng custom attribute bằng `false`. Tôi chưa chốt từng box vì phải nhìn đúng phần bị vật khác che; vùng blur không được tính là che khuất.
- L10 Pedestrian và L11 Car chưa thấy bị vật khác che đáng kể. Mép dưới L11 hơi rộng nên cần phóng ảnh kiểm lại.
- Ảnh chỉ có hai `lens_border`. Repo ghi frame này không thấy `ego_body`, nên tôi chưa tính đó là lỗi.
- Các điểm trên vẫn là ca cần xem lại, chưa phải finding đã xác nhận.

## adasind_295948.jpg

Tôi chốt bốn điểm ở ảnh này:

1. **L4 Bike — R05:** người và xe bị vật ở tiền cảnh che một phần. Custom `occluded=false` không khớp ảnh; tôi đề nghị đổi sang `true`.
2. **L5 Pedestrian — R05:** phần dưới cơ thể bị vật hoặc phương tiện phía trước che. Tôi đề nghị đổi custom `occluded` sang `true`.
3. **L7 Truck — R05:** xe ở phía sau vật khác và chỉ thấy một phần. Tôi đề nghị đổi custom `occluded` sang `true`.
4. **XML box #1 Car — R01:** box cao 26,99 px, thấp hơn H=40 nên tôi đề nghị bỏ khỏi bản nhãn. Box này không có mã L trong overlay vì tool chỉ đánh số box đạt ngưỡng.

L1 Truck, L2 Bike và L3 Truck chưa thấy lỗi class rõ. Hai người ở bên trái đã có box. Tôi cũng chưa thấy `lens_border` hoặc `ego_body` che nhầm vật ở ảnh này.

## Bàn giao

- Bốn điểm ở `adasind_295948.jpg` được ghi vào `findings.csv` của vòng QA nhóm.
- Ảnh minh chứng: [qa_B_295948_overlay.png](../screenshots/qa_B_295948_overlay.png).
- Các chỗ chưa chắc ở `270517` và `271039` vẫn để mở, không tính là lỗi đã chốt.
- Tôi gửi review cho A sửa trên bản làm việc. Bản khóa `6997-BF13` không bị sửa trực tiếp.
