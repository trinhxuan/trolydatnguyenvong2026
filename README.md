# Trợ Lý Nguyện Vọng 2026 – HSA 2026 A00 Percentile Simulation

Bản cập nhật này bổ sung bảng **HSA 2026 nhóm Khoa học Q01–Q10 (N = 41.235)** và mô-đun quy đổi **HSA → A00 năm 2026 mô phỏng** theo bách phân vị.

## Luồng quy đổi 2026

```text
Điểm HSA 2026 nhóm Khoa học Q01–Q10
→ tra phân vị (%) và top (%) trong bảng HSA 2026
→ đối sánh phổ điểm 2025 khối A00 rồi mô phỏng A00 2026 và các thanh điều chỉnh
→ tìm điểm A00 2026 có cùng top (%)
→ nội suy tuyến tính trong khoảng điểm THPT
```

## Dữ liệu giữ nguyên

- Bảng ĐHQGHN 2024 chính thức: A00, B00, C00, D01, A01 và HSA Toán → THPT Toán.
- Bảng ĐHQGHN 2025 chính thức: A00, B00, C00, D01.
- Chế độ 2026 là mô phỏng, dùng cho tham khảo chiến thuật đến khi có phổ THPT 2026 chính thức.

Không sử dụng công thức tuyến tính sai `HSA × 30 / 150`.


## Cập nhật nhãn mô phỏng ĐHQGHN

Mục “A00 2026 MÔ PHỎNG THEO PHÂN VỊ” đã được đổi thành “Cập nhật kiểu ĐHQGHN • Bách phân vị + nội suy”. Mô tả hiển thị: ứng dụng dùng bảng quy đổi chính thức ĐHQGHN 2026 và phổ điểm 2025 khối A00 theo 2 bảng số liệu người dùng cung cấp; điểm không trùng mốc được nội suy tuyến tính giữa hai dòng liền kề.

## Cập nhật Bộ Giả Lập A00 2026

Mục **“Bộ Giả Lập Phổ Điểm THPT A00 Dự Kiến 2026”** đã được code lại để lấy nền từ:

1. Bảng thứ hạng phần trăm HSA 2026 lựa chọn phần thi Khoa học Q01–Q10.
2. Phổ điểm thi tốt nghiệp THPT khối A00 năm 2025 theo biểu đồ người dùng cung cấp.

Ứng dụng tạo bảng neo HSA → A00 theo nguyên tắc cùng top %, sau đó cho phép hiệu chỉnh kịch bản A00 2026 theo các vùng Top 1%, Top 5%, Top 10% và Top 20%.


## Cập nhật giao diện sáng Hy vọng & May mắn
- Chuyển toàn bộ nền tối sang tông sáng: xanh hy vọng, vàng may mắn, trắng/mint dễ đọc trên điện thoại.
- Thêm favicon, icon 512x512, apple-touch-icon và ảnh chia sẻ `og-image.png`.
- Thêm `site.webmanifest`, `theme-color`, Open Graph và Twitter Card để khi chia sẻ/lưu ra màn hình điện thoại có biểu tượng riêng.
- Không thay đổi thuật toán quy đổi điểm; chỉ cập nhật giao diện và tài nguyên nhận diện.
