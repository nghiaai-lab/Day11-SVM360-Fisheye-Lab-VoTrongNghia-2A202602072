# Nhận xét P1 C0 — vai B

- Người soát: Võ Trọng Nghĩa.
- Chủ nhãn: Nguyễn Trí Tín.
- Nguồn: nhánh `p0-parking-export`, commit `56488ef` của repo nhóm.
- Frame: `adasind_019560.jpg`.
- Mã khóa bản được soát: `78D7-86D3`.
- SHA-256 XML: `78d786d384cf9e3f6ed5af0b07f5147826f4fb4c98f5637424b63cf023411019` (đã kiểm khớp khóa).
- Cách soát: tôi mở ảnh gốc cùng overlay và đối chiếu với [luật gán nhãn](../../docs/02-rules-vi.md).
- Bằng chứng nguồn: [XML C0 đã soát](https://github.com/DTKien2005/Day11-SVM360-Fisheye-Lab-Student/blob/56488ef147cb6fdb8829d65479b93cce435fed60/submission/p1_calib/annotations.xml), [mã khóa](https://github.com/DTKien2005/Day11-SVM360-Fisheye-Lab-Student/blob/56488ef147cb6fdb8829d65479b93cce435fed60/submission/p1_calib/lock.txt), [ảnh gốc](../../assets/images/adasind_019560.jpg).

## Nhận xét đã xác nhận trên ảnh

| Object ref | Rule | Tôi thấy | Nhận xét gửi A |
|---|---|---|---|
| L1 — `ThreeWheeler` | R02, R04 | Class đúng và box bám phương tiện. | Có thể giữ. |
| L2 — `Bike` | R03 | Người áo đỏ đang đứng/dắt xe máy, không ngồi điều khiển. | Cần tách thành hai box: `Pedestrian` cho người và `Bike` cho xe; mỗi box bám phần nhìn thấy theo R02. |
| L3 — `Bike` | R03 | Người áo vàng đang ngồi trên xe. | Có thể giữ một box `Bike` chung cho cả người và xe. |

## Những điểm còn cần rà soát

| Vị trí / phạm vi | Rule | Điều cần kiểm | Trạng thái |
|---|---|---|---|
| Các xe hai bánh phía phải, dưới mái che; chưa có mã L tương ứng | R01 | Kiểm từng đối tượng có cao từ 40 px trên ảnh gốc và thuộc vùng hợp lệ hay không; nếu thỏa điều kiện thì cần box. | Chưa xác nhận đối tượng cụ thể hoặc lỗi thiếu nhãn; chưa đo chiều cao. |
| L1–L3 | R05 | Không thấy box hiện tại bị vòng kính cắt nên `truncated=false` nhìn chung hợp lý. Rà riêng `occluded` nếu phần thân xe/người bị vật khác che đáng kể. | Chưa chốt lại từng giá trị `occluded`. |
| Hai polygon `lens_border` | R06, R08 | Biên phải bám phần viền tối ngoài trường nhìn. | Chưa xác nhận lỗi hình học cụ thể. |
| Polygon `ego_body` | R02, R06, R07, R09 | Chỉ phủ phần thân/cụm xe camera nhìn thấy ở mép dưới; không lấn sang mặt đường hoặc đối tượng giao thông. | Chưa xác nhận lỗi hình học cụ thể. |

## Bàn giao

Tôi đề nghị A sửa L2 thành một box `Pedestrian` và một box `Bike`. Lúc viết ghi chú này tôi chưa có bản A sửa để kiểm lại.

Tôi giữ XML và mã khóa của bản đã soát. Nếu A khóa lại C0 thì cần tạo lock mới và ghi lý do. File này là ghi chú P1, không phải QA P3 trong `findings.csv`.
