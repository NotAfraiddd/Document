# OOP là gì? Tính chất của OOP?
- Object-Oriented Programming là một mô hình lập trình dựa trên đối tượng (Object), trong đó các đối tượng được tạo ra 
từ lớp(Class)
- 4 tính chất của OOP:
    + Tính kế thừa: Lớp con kế thừa các thuộc tính và phương thức của lớp cha.
    + Tính đóng gói: Bảo vệ dữ liệu, và có thể thay đổi dữ liệu bằng cách phương thức được định nghĩa trong class.
    + Tính trừu tượng: Chỉ hiển thị kết quả thôi, không biết các phương thức được hoạt động như nào.
    + Tính đa hình: Lớp con có thể ghi đè lên các phương thức của lớp cha để cho ra kết quả khác.
# Sự khác nhau giữa interface và abstract?
- Interface: là định nghĩa các phương thức mà không cần logic, có thể implement từ class. Không có constructor.
- Abstract: định nghĩa các phương thức( có thể có logic),các lớp abstract chỉ implement interface, cần phải định nghĩa lại các phương thức 
không có logic, còn nếu có logic thì sử dụng bình thường. Có constructor

# Ngăn xếp và hàng đợi khác nhau gì?
- Ngăn xếp( stack ): LIFO - Last in first out ( push() -> pop() )
- Hàng đợi(queue): FIFO - First in first out ( add() -> poll())
# Linked List
- Gồm 3 loại: danh sách liên kết đơn, đôi, vòng.
# Con trỏ là gì?
- con trỏ là nơi lưu lại địa chỉ bộ nhớ của node
# Có bao nhiêu kiểu dữ liệu chính?
- 2 kiểu: 
    + nguyên thủy: byte, short, int, long, float, double, char, boolean.
    + tham chiếu: Là các kiểu dữ liệu **không lưu trực tiếp giá trị**, mà **lưu địa chỉ bộ nhớ** của đối tượng.
        - String, Array, Class, Interface, Collection
# Có mấy cách tạo string?
- 2 cách
    + Tạo trưc tiếp: Chuỗi này sẽ được lưu trong String Pool (bộ nhớ cache của chuỗi trong Heap).
    VD: String str1 = "Hello";
    + Tạo bằng new String: **Luôn tạo ra một đối tượng mới trong Heap**, ngay cả khi chuỗi "Hello" đã tồn tại trong String Pool.
    String str2 = new String("Hello");
# String là bất biến đúng không?
- Yes. 
```
String s1 = "Hello";  
s1 = s1 + " World";  
System.out.println(s1);
```
**String s1 = "Hello";** sẽ tạo ra chuỗi và được lưu lại trong String Pool.
**s1 = s1 + " World";** sẽ được tham chiếu tới vị trí s1 và tạo ra 1 đối tượng mới ở trong HEAP.
**System.out.println(s1);** vì s1 được tham chiếu tới HEAP nên sẽ in ra ở đây được.
# Nếu 1 chuỗi không có sẵn trong Pool, làm sao để tham chiếu tới và lưu nó lại trong POOL được?
String s1 = "Hello";  
s1 = (s1 + " World").intern();  
System.out.println(s1);

String Pool:                Heap:
┌────────────────┐         ┌────────────────┐
│ "Hello"        │         │ "Hello World"  │  (GC có thể dọn)
│ "Hello World"  │ ← s1    └────────────────┘
└────────────────┘

Vậy có thể hiểu là sau khi dùng intern() nó sẽ tham chiếu tới vị trí s1 và tạo ra chỗ lưu trữ mới trong POOL, ở bên Heap thì có
thể bị dọn dẹp.

# Nếu muốn thay đổi chuỗi thì làm sao?
- Dùng StringBuilder hoặc StringBuffer (Có thể thay đổi giá trị). nó không tạo ra đối tượng mới trong Heap
```
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb);
```

# Class với đối tượng khác nhau gì?
- Class là có thuộc tính và hành vi( phương thức).
- Đối tượng là là được tạo ra từ class, và nó sẽ có thuộc tính và phương thức của clas.
* Nếu không có class, thì không có đối tượng. Nếu không có đối tượng, thì class là một khái niệm trừu tượng thôi.

# Có mấy mức độ truy cập cho lớp? Có mấy mức độ truy cập cho các thành viên của lớp?
- Có 2 mức độ truy cập cho lớp.(Public và default)
- Có 4 mức độ truy cập cho các thành viên của lớp: private, default, protected, Public.
    + private dùng trong nội bộ class.
    + default thì dùng trong cùng package.
    + protected dùng trong cùng package và kế thừa lớp con.
    + public thì dùng đc mọi nơi.

# Tính đa hình được thể hiện qua đâu?
- Override và overloading
    + Override: ghi đè
    + overloading: nạp chồng - cùng tên phương thức nhưng khác tham số.

