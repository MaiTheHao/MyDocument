Headers trong fetch() là nơi bạn chỉ định các thông tin bổ sung (metadata) gửi kèm với request,
giúp server hiểu cách xử lý dữ liệu được gửi hoặc yêu cầu từ client. Header là một phần quan 
trọng của HTTP, và trong fetch, bạn có thể dễ dàng cấu hình chúng thông qua thuộc tính headers 
trong tùy chọn.

fetch(url, {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
        'Authorization': 'Bearer your-token',
        'Custom-Header': 'CustomValue'
    },
    body: JSON.stringify({ key: 'value' })
});

Tên Header        Ý nghĩa                                                        Ví dụ giá trị
--------------------------------------------------------------------------------------------------------------
Content-Type      Xác định định dạng của dữ liệu trong request body.             application/json, text/plain, multipart/form-data

Accept            Xác định loại dữ liệu mà client mong muốn server trả về.       application/json, text/html, */*

Authorization     Gửi thông tin xác thực,                                        Bearer your-access-token
                  thường là token (Bearer token, Basic Auth). 

Cache-Control     Điều khiển cách cache request/response trên                    no-cache, no-store, max-age=3600
                  client hoặc proxy. 

Origin            Chỉ định nguồn gốc của request, thường được dùng trong CORS.   https://example.com

Referer           URL tham chiếu nơi request được gửi đi.                        https://example.com/page

User-Agent        Thông tin về client (trình duyệt, thư viện, ...)               Mozilla/5.0 (Windows NT 10.0; Win64; x64)
                  gửi request.  

Cookie            Gửi cookie từ client đến server.                               sessionId=abc123; token=xyz456

Custom headers    Các header do người dùng định nghĩa                            X-Custom-Header: MyValue
                  (ví dụ, trong các API yêu cầu header đặc biệt).