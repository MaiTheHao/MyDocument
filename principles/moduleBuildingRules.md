# ⚙️ Nguyên tắc lập trình dự án (SOLID)
Một tập hợp các nguyên tắc thiết kế hướng đối tượng bao gồm SRP, OCP, LSP, ISP, và DIP.

## 🎯 SRP (Single Responsibility Principle)
Một class chỉ nên có một lý do để thay đổi, nghĩa là nó chỉ nên có một trách nhiệm duy nhất.

## 🚪 OCP (Open/Closed Principle)
Các thực thể phần mềm (class, module, function, v.v.) nên được mở để mở rộng nhưng đóng để sửa đổi.

## 🔄 LSP (Liskov Substitution Principle)
Các đối tượng trong một chương trình nên có khả năng được thay thế bằng các instance của các subtype của chúng mà không làm thay đổi tính đúng đắn của chương trình.

## 🔍 ISP (Interface Segregation Principle)
Nhiều interface cụ thể tốt hơn là một interface chung chung.

## ⚡ DIP (Dependency Inversion Principle)
Các module cấp cao không nên phụ thuộc vào các module cấp thấp. Cả hai nên phụ thuộc vào các abstraction. Abstraction không nên phụ thuộc vào chi tiết. Chi tiết nên phụ thuộc vào abstraction.

# 🔰 Other

## 📝 DRY (Don't Repeat Yourself)
Tránh lặp lại mã. Thay vì lặp lại logic, hãy trừu tượng hóa nó thành các hàm hoặc module có thể tái sử dụng.

## 🎈 KISS (Keep It Simple, Stupid)
Giữ cho mã đơn giản và dễ hiểu. Tránh phức tạp hóa không cần thiết.

## 🎯 YAGNI (You Aren't Gonna Need It)
Chỉ triển khai những gì cần thiết. Tránh thêm các tính năng hoặc mã không cần thiết cho yêu cầu hiện tại.

# 📚 Chi tiết về SOLID

## Single Responsibility Principle (SRP)
- Mỗi class chỉ nên giải quyết một vấn đề cụ thể.
- Ví dụ: Class `UserAuthentication` chỉ xử lý việc xác thực, không nên thêm logic về logging hay database.
- Lợi ích: Dễ bảo trì, test và tái sử dụng code.

## Open/Closed Principle (OCP)
- Code nên dễ mở rộng mà không cần sửa đổi code hiện có.
- Sử dụng interface và abstract classes để đạt được điều này.
- Ví dụ: Thêm phương thức thanh toán mới mà không sửa code cũ.

## Liskov Substitution Principle (LSP)
- Các class con phải hoạt động đúng khi thay thế class cha.
- Không nên override method của class cha theo cách làm thay đổi hành vi cơ bản.
- Đảm bảo tính nhất quán trong hệ thống phân cấp kế thừa.

## Interface Segregation Principle (ISP)
- Tách interface lớn thành nhiều interface nhỏ, chuyên biệt.
- Client không nên phụ thuộc vào interface họ không sử dụng.
- Giúp code linh hoạt và dễ maintain hơn.

## Dependency Inversion Principle (DIP)
- Module cấp cao nên phụ thuộc vào abstraction.
- Tránh tight coupling giữa các module.
- Sử dụng dependency injection để implement nguyên tắc này.
