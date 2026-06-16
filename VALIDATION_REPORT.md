# VALIDATION REPORT – Cập nhật HSA 2026 Q01–Q10 + mô phỏng A00 THPT 2026

## 1. Dữ liệu đã cập nhật

Đã nhập đầy đủ bảng HSA 2026 nhóm Khoa học Q01–Q10 từ ảnh người dùng cung cấp, từ điểm 133 đến 19, gồm ba cột:

- Điểm thi HSA
- Phân vị (%)
- Tốp (%)

Mốc kiểm tra trong bảng:

| HSA | Phân vị (%) | Tốp (%) |
|---:|---:|---:|
| 133 | 100.00 | 0.00 |
| 129 | 100.00 | 0.01 |
| 112 | 99.32 | 0.81 |
| 100 | 94.51 | 6.21 |
| 98 | 92.92 | 8.05 |
| 95 | 89.85 | 11.31 |
| 80 | 62.35 | 40.26 |
| 67 | 27.52 | 74.88 |
| 50 | 2.22 | 98.23 |
| 19 | 0.00 | 100.00 |

## 2. Thuật toán quy đổi 2026 đã sửa

Trước bản này, chế độ 2026 vẫn lấy phân vị HSA 2026 rồi nội suy vào bảng ĐHQGHN 2025 và cộng độ dịch chuyển. Cách đó chưa thực sự ghép trực tiếp với phổ THPT A00 2026 mô phỏng.

Bản mới dùng đúng luồng:

```text
Bảng ĐHQGHN 2026 nhóm Khoa học Q01–Q10 → top (%) HSA 2026 → phổ điểm 2025 khối A00 → A00 2026 mô phỏng cùng top (%)
```

Hàm chính:

```js
getVnuEquivalentBundle(hsaScore, hsaPercentileData, 2026)
calculatePercentileMatch(hsaPercentileData.top, getSimulated2026Distribution(), total)
```

## 3. Nguyên tắc nội suy

Nếu top (%) rơi trong một khoảng điểm THPT, ứng dụng nội suy tuyến tính trong bin đó:

```text
equivalentScore = current.max - fraction * (current.max - current.min)
```

## 4. Lưu ý

- Chế độ 2026 là mô phỏng vì chưa có phổ THPT 2026 chính thức.
- Các cột B00/C00/D01/A01 không mô phỏng trong chế độ 2026 nếu chưa có phổ riêng tương ứng.
- Các chế độ ĐHQGHN 2024 và 2025 vẫn dùng bảng chính thức đã nhập trước đó.


## Cập nhật theo yêu cầu mới

Đã đổi cụm “Cập nhật kiểu HOCMAI • Bách phân vị + nội suy” thành “Cập nhật kiểu ĐHQGHN • Bách phân vị + nội suy”. Đã đổi mô tả sang: ứng dụng dùng bảng quy đổi chính thức ĐHQGHN 2026 và phổ điểm 2025 khối A00 theo 2 bảng số liệu này; điểm không trùng mốc được nội suy tuyến tính giữa hai dòng liền kề.

## Cập nhật mới – Bộ Giả Lập Phổ Điểm THPT A00 Dự Kiến 2026

Đã code lại riêng mục **“Bộ Giả Lập Phổ Điểm THPT A00 Dự Kiến 2026”** theo đúng hai bảng người dùng cung cấp:

```text
Bảng thứ hạng phần trăm HSA 2026 Q01–Q10
+ Phổ điểm thi tốt nghiệp THPT khối A00 năm 2025
→ cùng top (%) thì xem là tương đương
→ nội suy tuyến tính trong khoảng điểm A00 2025
→ tạo A00 2026 mô phỏng theo các thanh hiệu chỉnh top 1%, 5%, 10%, 20%
```

### Thay đổi kỹ thuật

- Thêm cụm thông tin nguồn dữ liệu ngay trong bộ giả lập:
  - HSA 2026 Q01–Q10, N = 41.235.
  - Phổ điểm thi A00 năm 2025 theo từng cột 0–29.
- Thêm bảng neo mô phỏng **HSA 2026 → A00 nền 2025 → A00 mô phỏng 2026**.
- Sửa phổ A00 2025 theo ảnh biểu đồ người dùng gửi:
  - 29–30: 344
  - 28–29: 1.964
  - 27–28: 4.216
  - 26–27: 6.047
  - 25–26: 7.402
  - 24–25: 8.525
  - 23–24: 9.456
  - 22–23: 10.385
  - 21–22: 11.482
  - 0–1 đến 14–15 nhập theo nhãn trong biểu đồ; các cột 16–20 được khôi phục từ chiều cao cột vì bị watermark che một phần.
- Sửa trục biểu đồ A00 về đúng nhãn **0–29** như biểu đồ gốc.
- Sửa tô sáng biểu đồ theo đúng khoảng chứa điểm, không làm tròn sai sang cột khác.
- Đặt mặc định tab quy đổi dùng chế độ **Mô phỏng 2026** để bộ giả lập hiện ngay khi mở mục quy đổi.

### Mốc kiểm thử khi các thanh hiệu chỉnh = 0.00

| HSA | Phân vị HSA 2026 | Top HSA 2026 | A00 nền/mô phỏng 2026 |
|---:|---:|---:|---:|
| 112 | 99.32% | 0.81% | 28.51 |
| 110 | 98.99% | 1.27% | 28.13 |
| 100 | 94.51% | 6.21% | 26.41 |
| 98 | 92.92% | 8.05% | 25.93 |
| 95 | 89.85% | 11.31% | 25.22 |

Các giá trị trên thay đổi nếu người dùng kéo các thanh giả lập kịch bản 2026.
