# 🌟 **LAZY LOADING TRONG JAVASCRIPT** 🌟  

---

## 📌 1. Lazy Loading là gì?  
- 🌟 Lazy loading là kỹ thuật tối ưu hóa trang web bằng cách trì hoãn việc tải các tài nguyên cho đến khi thực sự cần thiết.  
- 📈 Giúp cải thiện hiệu suất trang web và tiết kiệm băng thông.  

---

## 📌 2. Lazy Loading Images bằng thuộc tính `loading="lazy"`  
- 🔹 Cách đơn giản nhất để lazy load hình ảnh:  
  ```html
  <img src="image.jpg" loading="lazy" alt="Mô tả">
  ```  
- 🔧 **Các thuộc tính quan trọng**:  
  - `loading="lazy"`: Kích hoạt lazy loading.  
  - `width`, `height`: Nên thêm để tránh layout shift.  
  - `decoding="async"`: Cho phép giải mã hình ảnh không đồng bộ.  

---

## 📌 3. Lazy Loading Elements bằng Intersection Observer  
- 📊 Sử dụng Intersection Observer API để theo dõi khi element xuất hiện trong viewport.  

### 🔍 Ví dụ code:
```javascript
const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            // Xử lý khi element xuất hiện trong viewport
            loadElement(entry.target);
            observer.unobserve(entry.target);
        }
    });
});

const elements = document.querySelectorAll('.lazy');
elements.forEach(element => observer.observe(element));
```

---

## 📌 4. Các phương pháp Lazy Loading khác  
### 🔸 **Dùng scroll event (không khuyến khích)**:  
```javascript
window.addEventListener('scroll', () => {
    // Kiểm tra vị trí element và viewport
    // Load content khi cần
});
```

### 🔸 **Lazy Loading Components trong React**:  
```javascript
import { lazy, Suspense } from 'react';
const LazyComponent = lazy(() => import('./LazyComponent'));
```

---

## 📌 5. Best Practices 🛠️  
- ✔️ Luôn cung cấp fallback content.  
- ✔️ Sử dụng loading skeleton hoặc placeholder.  
- ✔️ Tránh **Cumulative Layout Shift (CLS)**.  
- ✔️ Ưu tiên **Intersection Observer** thay vì scroll event.  
- ✔️ Chỉ lazy load những content ở **below the fold**.  

---

## 📌 6. Lưu ý quan trọng ⚠️  
- ❌ Không nên lazy load các element quan trọng (**above the fold**), chỉ lazy load các element cần thiết (**below the fold**).  
- ✅ Cân nhắc **user experience** và **performance**.  
- 🔄 Test trên nhiều thiết bị và tốc độ mạng khác nhau.  
- 🛡️ Luôn có phương án dự phòng cho trình duyệt không hỗ trợ.  