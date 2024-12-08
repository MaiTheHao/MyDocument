# Quá Trình Tải JavaScript Trong HTML

---

## 1. Quá trình tải thông thường (Normal Loading)
- Khi gặp thẻ `<script>`, trình duyệt sẽ:
  - Tạm dừng việc phân tích (parse) HTML
  - Tải file JavaScript
  - Thực thi JavaScript
  - Tiếp tục phân tích HTML
- **Nhược điểm**: Làm chậm quá trình hiển thị trang web.

---

## 2. Async Loading
- **Cú pháp**: `<script async src="script.js">`
- **Đặc điểm**:
  - Tải JavaScript song song với quá trình phân tích HTML.
  - Khi JavaScript tải xong, HTML tạm dừng để thực thi JavaScript.
  - Các script `async` có thể thực thi **không theo thứ tự**.
- **Phù hợp cho**:
  - Scripts độc lập (không phụ thuộc scripts khác).
  - Analytics, tracking scripts.

---

## 3. Defer Loading
- **Cú pháp**: `<script defer src="script.js">`
- **Đặc điểm**:
  - Tải JavaScript song song với quá trình phân tích HTML.
  - Chỉ thực thi JavaScript sau khi HTML được phân tích xong.
  - Các script `defer` luôn thực thi **theo đúng thứ tự khai báo**.
- **Phù hợp cho**:
  - Scripts phụ thuộc vào DOM.
  - Scripts phụ thuộc lẫn nhau.

---

## So sánh
1. **Normal**:  
   Chặn parse HTML → Tải JS → Thực thi JS → Tiếp tục parse HTML.
2. **Async**:  
   Parse HTML song song với tải JS → Tạm dừng parse HTML để thực thi JS → Tiếp tục parse HTML.
3. **Defer**:  
   Parse HTML song song với tải JS → Parse HTML xong → Thực thi JS.

---

## Khuyến nghị sử dụng
- **Defer**: Cho hầu hết scripts cần DOM.
- **Async**: Cho scripts độc lập (analytics, ads).
- **Normal**: Cho scripts quan trọng cần chạy ngay lập tức.
