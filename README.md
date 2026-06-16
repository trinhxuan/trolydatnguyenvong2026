# Trợ Lý Nguyện Vọng 2026 — bản đã sửa lỗi

Ứng dụng HTML tĩnh đã được rà soát và đóng gói lại để chạy trực tiếp trên GitHub Pages.

## File chính

- `index.html`: file chạy chính của GitHub Pages, phải nằm ở thư mục gốc repository.
- `Tro_Ly_Nguyen_Vong_2026.html`: bản HTML cùng nội dung, giữ để mở trực tiếp nếu cần.
- `.nojekyll`: giúp GitHub Pages phục vụ file tĩnh trực tiếp.
- `.gitignore`: bỏ qua file tạm của hệ điều hành/trình soạn thảo.

## Các lỗi đã sửa

- Chống trắng trang khi Chart.js CDN tải chậm hoặc bị chặn.
- Bổ sung CSS fallback cho lớp `hidden`, giúp tab không bị bung toàn bộ khi Tailwind chưa tải kịp.
- Bổ sung các hàm đọc/ghi DOM an toàn để tránh lỗi khi một vùng giao diện bị thiếu hoặc bị đổi tên.
- Bọc các bước khởi tạo quan trọng bằng cơ chế chống crash.
- Đóng gói lại theo chuẩn GitHub Pages: các file nằm ngay ở thư mục gốc, không bị lồng thêm thư mục con.

## Cách đưa lên GitHub Pages

1. Tạo repository mới trên GitHub.
2. Giải nén file ZIP này.
3. Upload toàn bộ file bên trong thư mục giải nén lên thẳng thư mục gốc của repository, không upload cả thư mục mẹ.
4. Vào **Settings → Pages**.
5. Chọn **Deploy from a branch**.
6. Chọn nhánh `main`, thư mục `/root`, rồi bấm **Save**.
7. Mở đường dẫn GitHub Pages do GitHub cung cấp.

## Kiểm tra nhanh

Mở `index.html` trên trình duyệt. Nếu internet bị chặn CDN, giao diện có thể thiếu một số hiệu ứng/biểu đồ, nhưng ứng dụng không bị trắng trang.
