# Toolkit — Từ Evidence Đến Build Slice

Dùng sau khi nhóm đã có evidence. Mục tiêu là chốt một build slice đủ nhỏ cho Day 06.

## 1. Gom evidence thành cụm

Gom theo **workflow/pain**, không gom theo tên feature.

Ví dụ cụm tốt:
- "Nghĩ trưa nay ăn gì quá mệt mỏi"
- "Lười lướt app nhặt từng củ hành củ tỏi"
- "Lên mạng xem công thức xong nhưng siêu thị hết hàng thịt lợn"

## 2. Viết insight

Form:

```text
User [người nội trợ/dân văn phòng bận rộn] không chỉ cần [nơi để mua thực phẩm].
Họ thật ra cần [giảm tải áp lực nhận thức (cognitive load) khi lên thực đơn],
vì [lướt app nhặt từng món vừa lâu vừa dễ quên nguyên liệu phụ (hành, tỏi)].
```

## 3. Viết opportunity

Form:

```text
Cơ hội là dùng AI để [automate việc lên thực đơn và nhặt đồ vào giỏ hàng],
giúp user [hoàn tất việc đi chợ trong 10 giây],
trong khi vẫn kiểm soát [rủi ro mua nhầm đồ bị dị ứng bằng bước Human Review].
```

## 4. Chọn build slice

Build slice tốt phải qua 5 câu hỏi:

| Câu hỏi | Đạt khi |
|---|---|
| User cụ thể chưa? | Nhân viên văn phòng tranh thủ lúc 5h chiều đặt đồ ăn tối. |
| Task đủ hẹp chưa? | Từ lúc mở app chat "Nhà có 3 quả trứng" đến lúc xuất hiện Giỏ hàng. |
| AI decision rõ chưa? | AI kết hợp Prompt + Tồn kho (Inventory) + Thói quen user (Lịch sử mua) để chọn đúng nhãn hiệu và tự bốc vào giỏ. Chốt đơn đẩy sang siêu thị gom hàng (Picker). |
| Failure path rõ chưa? | AI nhặt nhầm nguyên liệu user bị dị ứng hoặc vượt quá ngân sách (100k). |
| Có evidence không? | Lấy từ bài bóc phốt trên group hội chị em. |

## 5. Quyết định: giữ, giảm scope, hay đổi hướng?

| Tình huống | Quyết định |
|---|---|
| Evidence yếu, user mơ hồ | Dừng build sâu; quay lại research 20 phút. |
| Rủi ro cao | AI tự thanh toán rủi ro cao -> Chọn **Augmentation** (AI add giỏ hàng, user bấm thanh toán). |

## 6. Câu chốt cuối

Điền câu này trước khi rời lớp:

```text
Dựa trên [bằng chứng về nỗi đau phải lướt app nhặt từng nguyên liệu],
nhóm sẽ build [tính năng "Đi chợ bằng thực đơn 1 chạm"],
cho [nhân viên văn phòng bận rộn],
để giải quyết [áp lực nghĩ xem tối nay ăn gì và lười mua lặt vặt],
bằng cách AI [automate việc lên mâm cơm dựa trên Prompt, Tồn kho siêu thị và Thói quen cá nhân, sau đó tự nhặt đồ vào giỏ để giao hỏa tốc],
và sẽ test failure path [AI nhặt nhầm đồ user dị ứng hoặc vượt ngân sách].
```

## 7. Backlog

Những thứ **không build trong Day 06**:

- Không build phần quét camera xem tủ lạnh có gì (nhập bằng text cho nhanh).
- Không build phần theo dõi Calo/Sức khỏe phức tạp.
- Không build luồng tự động thanh toán.
