# Template — Thin SPEC Cuối Day 05

Thin SPEC không phải PRD đầy đủ. Đây là bản cam kết đủ rõ để sáng Day 06 nhóm build ngay.

## 1. Track, product/app và user

**Track:** Siêu thị / Grocery (B2C)
**Product/app thật:** Bách Hóa Xanh / VinID
**User cụ thể:** Dân văn phòng bận rộn đặt thực phẩm lúc 5h chiều.
**Nhóm có phải user thật không? Nếu không, khác ở đâu?** Có, các thành viên nhóm cũng hay đặt đồ nấu ăn online.

## 2. Evidence summary

| Evidence | Nguồn | User/pain nói lên điều gì? | SPEC phải đổi gì? |
|---|---|---|---|
| Lười nhặt đồ lặt vặt (hành, ngò, tỏi) và hay bị sót. | Tự trải nghiệm | User cần giải pháp gom món trọn gói (Bundle) | Làm AI tự add nguyên liệu phụ vào giỏ. |
| Nghĩ món nấu mệt não. | Group Yêu Bếp | Nỗi đau lớn nhất là chọn món chứ không phải mua đồ. | AI phải kiêm cả vai trò gợi ý mâm cơm. |

## 3. Pain statement

```text
User [Dân văn phòng bận rộn] đang gặp khó ở [bước lên ý tưởng mâm cơm và chọn đồ vào giỏ],
vì [phải lướt app tìm từng nguyên liệu cực kỳ mất thời gian và hay quên đồ lặt vặt],
dẫn tới [chán nản, thà ra chợ hoặc order đồ ăn ngoài cho nhanh].
Bằng chứng chính là [Trải nghiệm self-use và các bài đăng than phiền trên MXH].
```

## 4. Build slice

```text
Cho [người dùng bận rộn] đang [muốn mua thực phẩm nấu bữa tối],
prototype sẽ dùng AI để [nhận Prompt, phân tích Tồn kho siêu thị và Thói quen mua sắm cá nhân],
tạo ra [Giỏ hàng điền sẵn đúng nhãn hiệu yêu thích (VD: Nước mắm Nam Ngư), chốt đơn đẩy ngay cho nhân viên siêu thị (Picker) gom đồ đưa Shipper],
và xử lý [failure mode mua nhầm đồ dị ứng] bằng [Hiển thị giỏ hàng nháp để user review].
```

## 5. Auto/Aug decision

Chọn một:

- [x] **Augmentation:** AI gợi ý/draft/phân loại, user quyết cuối.
- [ ] **Conditional automation:** AI tự làm trong case hẹp; case mơ hồ/rủi ro chuyển người.
- [ ] **Automation:** AI tự quyết và tự hành động.

**Lý do chọn:** Việc thanh toán tiền (Checkout) là hành vi nhạy cảm. AI chỉ giúp lên danh sách đồ và đưa vào Giỏ, user bắt buộc phải review và tự bấm thanh toán.
**Human role:** reviewer / decider.

## 6. Four paths

| Path | Prototype phải thể hiện gì? |
|---|---|
| Happy | User nhập prompt -> AI nhận diện thói quen "hay mua đồ organic", tạo Giỏ hàng toàn thịt rau chuẩn VietGAP. Bấm thanh toán, đơn nổ sang thiết bị của Picker tại siêu thị. |
| Low-confidence | User chat "Gợi ý món chay" -> AI gợi ý món và hỏi "Mình lấy loại Đậu hũ hộp như tháng trước bạn hay mua nhé?" |
| Failure | Siêu thị hết Thịt lợn băm loại user hay mua -> AI bôi đỏ cảnh báo và hỏi "Có lấy loại thịt nạc dăm của hãng khác thay thế không?" |
| Correction | User quẹt (swipe) để đổi hãng thịt khác trước khi chốt đơn giao cho Shipper. |

## 7. Failure mode nguy hiểm nhất

```text
Nếu user [nhập ngân sách 100k],
AI có thể [ảo giác (hallucinate) và tính sai giá nguyên liệu, nhặt vào giỏ hàng lên tới 250k],
hậu quả là [user quẹt thẻ thanh toán bị hớ tiền gây bực tức].
Prototype sẽ xử lý bằng [human review: Luôn hiển thị tổng bill to rõ ràng ở nút Thanh Toán. Có cảnh báo màu vàng nếu ngân sách vượt giới hạn user đưa ra].
Owner kiểm thử path này là Đặng Ngọc Bách (MSV: 2A202600661).
```

## 8. Owner plan cho sáng Day 06

| Thành viên | Việc phụ trách | Bằng chứng cần có trong repo |
|---|---|---|
| Đặng Ngọc Bách | Research / evidence | Chụp 2-3 screen shot app hiện tại / group FB. |
| Đặng Ngọc Bách | SPEC | Bổ sung nốt file này hoàn thiện. |
| Đặng Ngọc Bách | Prototype | Vẽ UI màn hình chat và Giỏ hàng trên Figma. |
| Đặng Ngọc Bách | Test / failure path | Viết kịch bản Demo xử lý lỗi ngân sách 100k. |
| Đặng Ngọc Bách | Demo script / repo | Viết bài nói 3 phút, commit lên Github. |
