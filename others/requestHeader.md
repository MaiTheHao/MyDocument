# Headers trong `fetch()`

**Headers** trong `fetch()` được sử dụng để chỉ định thông tin bổ sung (metadata) gửi kèm với request, giúp server hiểu cách xử lý dữ liệu được gửi hoặc yêu cầu từ client. Header là một phần quan trọng của HTTP và dễ dàng cấu hình thông qua thuộc tính `headers` trong tùy chọn.

---

### **Ví dụ sử dụng `fetch()` với headers**
```javascript
fetch(url, {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
        'Authorization': 'Bearer your-token',
        'Custom-Header': 'CustomValue'
    },
    body: JSON.stringify({ key: 'value' })
});
```

---

### **Danh sách các Header phổ biến**

| **Tên Header**      | **Ý nghĩa**                                                    | **Ví dụ giá trị**                             |
|----------------------|---------------------------------------------------------------|-----------------------------------------------|
| **Content-Type**     | Xác định định dạng của dữ liệu trong request body.            | `application/json`, `text/plain`, `multipart/form-data` |
| **Accept**           | Xác định loại dữ liệu mà client mong muốn server trả về.      | `application/json`, `text/html`, `*/*`        |
| **Authorization**    | Gửi thông tin xác thực, thường là token (Bearer, Basic Auth). | `Bearer your-access-token`                   |
| **Cache-Control**    | Điều khiển cách cache request/response trên client hoặc proxy.| `no-cache`, `no-store`, `max-age=3600`       |
| **Origin**           | Chỉ định nguồn gốc của request, thường dùng trong CORS.      | `https://example.com`                         |
| **Referer**          | URL tham chiếu nơi request được gửi đi.                       | `https://example.com/page`                    |
| **User-Agent**       | Thông tin về client (trình duyệt, thư viện, ...) gửi request. | `Mozilla/5.0 (Windows NT 10.0; Win64; x64)`   |
| **Cookie**           | Gửi cookie từ client đến server.                             | `sessionId=abc123; token=xyz456`             |
| **Custom headers**   | Các header do người dùng định nghĩa.                         | `X-Custom-Header: MyValue`                   |

---

### **Chú ý khi sử dụng headers**
- **Content-Type:** Đặc biệt quan trọng khi gửi dữ liệu qua body (`application/json` cho JSON, `multipart/form-data` cho upload file).  
- **Authorization:** Đảm bảo bảo mật bằng cách chỉ truyền token qua kết nối an toàn (HTTPS).  
- **Custom headers:** Sử dụng khi API yêu cầu các header đặc biệt hoặc để truyền thông tin tùy chỉnh.  
- **CORS (Cross-Origin Resource Sharing):** Khi gửi request đến nguồn gốc khác, các header như `Origin` và `Referer` có thể quan trọng trong việc định cấu hình quyền truy cập.  

Sử dụng headers đúng cách giúp tối ưu hóa giao tiếp giữa client và server, tăng cường bảo mật và cải thiện hiệu suất API.