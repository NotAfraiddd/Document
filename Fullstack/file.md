
# Câu 1: Callback trong JavaScript có thể được hiểu như thế nào?
Callback trong Javascript là một function được sử dụng như là **một đối số** cho function khác.
- Function này có thể gọi tới function khác
- Callback có thể được gọi sau ở function này sau khi function khác đã kết thúc.

# Câu 2: So sánh sự khác nhau giữa let, var, const?
**Var**
- Phạm vi: Toàn cục hoặc phạm vi hàm
- Hoisting: Được hoisted lên đầu phạm vi của nó. Điều này có nghĩa là bạn có thể sử dụng biến trước khi khai báo mà không gặp lỗi.
- Cập nhật: Gía trị biến var có thể thay đổi sau khi đã khai báo

**Let**
- Phạm vi: Block code
- Hoisting: không thể sử dụng trước khi khai báo.
- Cập nhật: Gía trị biến Let có thể thay đổi sau khi đã khai báo

**Const**
- Phạm vi: Toàn cục hoặc phạm vi hàm
- Hoisting: không thể sử dụng trước khi khai báo.
- Cập nhật: Được sử dụng để khai báo các biến không thể thay đổi