# VALIDATION REPORT

## Cập nhật mới

Đã code lại ô kết quả chính để hiển thị rõ **điểm HSA sau khi quy đổi sang thang 30 theo phương pháp bách phân vị của ĐHQGHN**.

## Thay đổi giao diện

- Đổi nhãn ô kết quả từ `A00 2026 MÔ PHỎNG THEO PHÂN VỊ` thành `HSA QUY ĐỔI THANG 30 ĐHQGHN`.
- Ô kết quả hiển thị điểm quy đổi thang 30 nổi bật hơn, đúng tinh thần giao diện sáng – hy vọng – may mắn.
- Thêm dòng diễn giải trực tiếp: `HSA ... → A00 2026 mô phỏng theo bách phân vị, top ...`.
- Thêm nhãn `Bách phân vị + nội suy ĐHQGHN` để tránh hiểu nhầm là quy đổi hệ số.

## Thuật toán giữ nguyên

Luồng tính vẫn là:

```text
HSA 2026 Q01–Q10
→ tra phân vị/top (%) theo bảng HSA 2026
→ đối sánh phổ điểm A00 năm 2025
→ mô phỏng A00 2026
→ nội suy tuyến tính trong khoảng điểm
```

Không dùng công thức sai `HSA × 30 / 150`.

## Kiểm tra kỹ thuật

- Đã kiểm tra cú pháp JavaScript bằng `node --check`.
- Không phát hiện lỗi cú pháp.
- Hai file `index.html` và `Tro_Ly_Nguyen_Vong_2026.html` đã được đồng bộ nội dung.
