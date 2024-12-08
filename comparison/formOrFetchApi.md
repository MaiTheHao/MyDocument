### 🔄 So sánh giữa Gửi Dữ Liệu qua HTML Form và Fetch API

---

#### **📝 HTML Form Truyền Thống (Thẻ `<form>`)**

**Ưu điểm:**
- ✅ Dễ dàng triển khai.
- ✅ Trình duyệt xử lý sẵn việc gửi dữ liệu form.
- ✅ Tự động kiểm tra tính hợp lệ của form.
- ✅ Hoạt động mà không cần JavaScript.
- ✅ Có sẵn chỉ báo tải (loading indicators) của trình duyệt.

**Nhược điểm:**
- ❌ Cần tải lại toàn bộ trang.
- ❌ Kiểm soát yêu cầu/đáp ứng bị hạn chế.
- ❌ Không thể theo dõi tiến trình.
- ❌ Khó xử lý các cấu trúc dữ liệu phức tạp.

---

#### **🚀 Gửi Dữ Liệu qua Fetch API**

**Ưu điểm:**
- ✅ Không cần tải lại trang (trải nghiệm giống ứng dụng SPA).
- ✅ Kiểm soát chi tiết yêu cầu gửi đi.
- ✅ Có thể xử lý các định dạng dữ liệu phức tạp.
- ✅ Khả năng xử lý lỗi tốt hơn.
- ✅ Theo dõi tiến trình gửi dữ liệu.
- ✅ Có thể chỉnh sửa dữ liệu trước khi gửi.

**Nhược điểm:**
- ❌ Cần có JavaScript.
- ❌ Triển khai phức tạp hơn.
- ❌ Phải tự kiểm tra tính hợp lệ của form.
- ❌ Cần tự thêm chỉ báo tải (loading indicators).
- ❌ Cần thêm mã để bảo vệ chống CSRF.

---

#### **📋 Hướng Dẫn Sử Dụng**

**Sử dụng HTML Form truyền thống khi:**
- Xây dựng các form đơn giản như form đăng nhập.
- Không cần JavaScript.
- Ưu tiên cải tiến dần (progressive enhancement).
- Cần triển khai nhanh.

**Sử dụng Fetch API khi:**
- Cần gửi dữ liệu bất đồng bộ (async).
- Xử lý dữ liệu phức tạp.
- Muốn cải thiện trải nghiệm người dùng.
- Cần xử lý lỗi chi tiết.
- Cần tùy chỉnh header yêu cầu.

---