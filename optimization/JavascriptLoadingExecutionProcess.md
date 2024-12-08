# 🚀 Quá Trình Tải JavaScript Trong HTML

---

## 1️⃣ Quá trình tải thông thường (Normal Loading)
📋 **Quy trình**:
  - Khi gặp thẻ `<script>`, trình duyệt:
    - 🛑 Tạm dừng phân tích (parse) HTML
    - 📥 Tải file JavaScript
    - ⚙️ Thực thi JavaScript
    - ▶️ Tiếp tục phân tích HTML
🔴 **Nhược điểm**: Làm chậm quá trình hiển thị trang web.

---

## 2️⃣ Async Loading
📌 **Cú pháp**: `<script async src="script.js">`  
🔍 **Đặc điểm**:
  - ⏳ Tải JavaScript song song với phân tích HTML.
  - 🛑 Khi JavaScript tải xong, HTML tạm dừng để thực thi JS.
  - ⚠️ Các script `async` có thể thực thi **không theo thứ tự**.
🎯 **Phù hợp cho**:
  - Scripts độc lập (không phụ thuộc scripts khác).
  - 📊 Analytics, tracking scripts.

---

## 3️⃣ Defer Loading
📌 **Cú pháp**: `<script defer src="script.js">`  
🔍 **Đặc điểm**:
  - ⏳ Tải JavaScript song song với phân tích HTML.
  - ✅ Chỉ thực thi JavaScript sau khi HTML được phân tích xong.
  - 🔄 Các script `defer` luôn thực thi **theo thứ tự khai báo**.
🎯 **Phù hợp cho**:
  - Scripts phụ thuộc vào DOM.
  - Scripts phụ thuộc lẫn nhau.

---

## ⚖️ So sánh
1️⃣ **Normal**:  
   🛑 Chặn parse HTML → 📥 Tải JS → ⚙️ Thực thi JS → ▶️ Tiếp tục parse HTML.

2️⃣ **Async**:  
   ▶️ Parse HTML song song với tải JS → 🛑 Tạm dừng parse HTML để thực thi JS → ▶️ Tiếp tục parse HTML.

3️⃣ **Defer**:  
   ▶️ Parse HTML song song với tải JS → ✅ Parse HTML xong → ⚙️ Thực thi JS.

---

## ✅ Khuyến nghị sử dụng
- 🟢 **Defer**: Cho hầu hết scripts cần DOM.
- 🟡 **Async**: Cho scripts độc lập (analytics, ads).
- 🔴 **Normal**: Cho scripts quan trọng cần chạy ngay lập tức.