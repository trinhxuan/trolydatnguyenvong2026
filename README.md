# Trợ Lý Nguyện Vọng 2026

Dự án HTML tĩnh đã được đóng gói để đưa lên GitHub/GitHub Pages.

## Cấu trúc

- `index.html`: file chạy chính cho GitHub Pages.
- `Tro_Ly_Nguyen_Vong_2026.html`: bản gốc được giữ nguyên.
- `.nojekyll`: giúp GitHub Pages phục vụ file tĩnh trực tiếp, không qua Jekyll.
- `.gitignore`: bỏ qua các file tạm của hệ điều hành/trình soạn thảo.

## Cách đưa lên GitHub

1. Tạo repository mới trên GitHub.
2. Upload toàn bộ các file trong thư mục này lên nhánh `main`.
3. Vào **Settings → Pages**.
4. Ở mục **Build and deployment**, chọn:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
5. Bấm **Save**.
6. Mở đường dẫn GitHub Pages do GitHub cung cấp.

## Ghi chú kỹ thuật

Mã HTML gốc không bị chỉnh sửa. Nội dung file gốc chỉ được sao chép nguyên vẹn sang `index.html` để GitHub Pages tự nhận trang chủ.
