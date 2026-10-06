# 🥋 Dojo Booking System - Hệ thống Đặt Lịch Học CLB Võ

---

### Bước 1: Review & Chốt với khách hàng (Sign-off) ⭐ *Việc cần làm ngay*

Bản đặc tả hiện tại của bạn vẫn còn các mục đánh dấu ⚠️ (ví dụ: hạn chốt hủy lớp, trời mưa xử lý thế nào, thời gian lên Advanced là 7 hay 8 tháng).

- **Hành động:** Gửi link web vừa deploy cho khách xem.
- **Mục tiêu:** Hẹn một buổi trao đổi ngắn (hoặc nhắn qua Zalo) đi qua từng câu hỏi còn mở (Mục 7) để khách chốt phương án cuối cùng. Khi khách gật đầu đồng ý toàn bộ, bạn mới chuyển sang bước tiếp theo để tránh bị "thay đổi yêu cầu giữa chừng".

---

### Bước 2: Thiết kế giao diện mô phỏng (Wireframe / Mockup UI)

Khách hàng (thầy dạy võ) và học viên thường **khó hình dung qua chữ**, nhưng nhìn vào hình ảnh giao diện là họ hiểu ngay lập tức.

- **Hành động:** Dùng công cụ như **Figma** (hoặc vẽ phác thảo đơn giản):
  1. *Màn hình Lịch tuần:* Hiển thị các ca Sáng, Chiều, Tối với màu sắc phân biệt rõ lớp Basic / Advanced, số chỗ còn trống (VD: `5/8`).
  2. *Màn hình Đặt/Hủy chỗ:* Nút bấm đặt và popup báo thành công.
  3. *Màn hình Admin/Giáo viên:* Danh sách điểm danh học viên từng ca.

---

### Bước 3: Phân rã công việc thành Task (Backlog / GitHub Issues)

Chuyển đổi các User Story (US) và Business Rule (BR) trong tài liệu thành các đầu việc kỹ thuật cụ thể. Mở mục **Issues** hoặc **Projects** trên GitHub repo của bạn:

- **Tạo các task rõ ràng cho Developer:**
  1. *Task 1:* Thiết kế Cơ sở dữ liệu (bảng Học viên, Lớp/Ca, Lịch đặt chỗ).
  2. *Task 2:* Viết logic kiểm tra quyền đặt lịch (kiểm tra sĩ số tối đa 8 hoặc 10, kiểm tra đúng Level).
  3. *Task 3:* Làm giao diện xem lịch theo tuần.

---

### Bước 4: Lựa chọn công nghệ & Bắt tay vào Code (MVP)

Nếu bạn hoặc đội ngũ chuẩn bị lập trình, hãy làm phiên bản MVP (Sản phẩm tối thiểu) trước:

- **Công nghệ gợi ý cho dự án này:**
  1. *Frontend:* React / Vue / HTML + TailwindCSS (hoặc Zalo Mini App nếu muốn chạy trực tiếp trong Zalo).
  2. *Backend & Database:* Supabase hoặc Firebase (rất nhanh, miễn phí, không cần dựng server phức tạp).
- **Quy tắc làm:** Ưu tiên luồng cốt lõi nhất: *Học viên mở lên thấy lịch → Bấm chọn ca → Báo đặt thành công*.

---

### Bước 5: Viết kịch bản kiểm thử (Test Cases)

Dựa trực tiếp vào bảng BR (Quy tắc nghiệp vụ) và EC (Edge cases) mà bạn đã viết trong đặc tả để test:

- **Các trường hợp cần kiểm tra:**
  1. Thử cho 2 người cùng bấm đặt chỗ cuối cùng xem có bị vượt quá 8/10 người không?
  2. Học viên Basic thử bấm vào lớp Advanced xem có bị chặn lại đúng như quy tắc không?
  3. Kiểm tra tính năng hủy lớp và thông báo khi gặp trời mưa ở sân thượng.
