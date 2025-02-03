
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

# Điểm khác biệt giữa == và ===?
**==**: So sánh giá trị
**===**: So sánh giá trị và kiểu dữ liệu

# Giải thích các loại scope trong JavaScript.
- Global scope
- Block scope {}
- Function scope

# undefined khác gì với null trong JavaScript?
- **undefined** là không xác định được giá trị
- **null** là có giá trị và giá trị đó không có data

# Kể tên các kiểu dữ liệu nguyên thủy (primitive types) trong JavaScript.
- Number, boolean, string, undefined, null, symbol, bigint

# Dữ liệu phức hợp
- Array: là kiểu dữ liệu ĐẶC BIỆT object, object, function, date, RegExp

# typeof NaN trả về gì? Tại sao?
- Kết quả trả về là: Number. Tại vì JS sử dụng NaN như một giá trị không hợp đại diện cho phép toán số học.

# Trong JavaScript, giá trị của this thay đổi như thế nào trong các context khác nhau?
- This là sự đại diện cho nhiều ngữ cảnh khác nhau.
* **Trình duyệt**:
console.log(this) ==> window
* **constructor**:
Trong hàm constructor, this được sử dụng để tham chiếu đến đối tượng mới được tạo ra bởi từ khóa new.

# Giải thích khái niệm hoisting trong JavaScript.
- Nó sẽ được đưa lên đầu phạm vi của function, khai báo biến

# Sự khác biệt giữa một hàm function declaration và function expression?

- function declaration ( khai báo hàm):
    + Được hoisted trên đầu tiên của scope nên có thể gọi trước khi khai báo.
- function expression ( biểu thức hàm):
    + Không được hoisted.

# Event loop
- Khi có một tác vụ đồng bộ, nó sẽ được đưa vào call stack và thực thi ngay lập tức.

- Khi call stack trống, event loop sẽ kiểm tra microtask queue trước, bởi vì microtasks có độ ưu tiên cao hơn macrotasks. 
Các microtasks bao gồm Promises, queueMicrotask, MutationObserver,... Nếu có microtasks trong hàng đợi, chúng sẽ được thực thi hết
trước.

- Sau khi microtask queue rỗng, event loop mới lấy một tác vụ từ macrotask queue (bao gồm setTimeout, setInterval, setImmediate, 
I/O tasks, MessageChannel...) để xử lý.

- Sau khi xử lý xong một macrotask, event loop sẽ quay lại kiểm tra microtask queue trước rồi mới tiếp tục với macrotask tiếp 
theo viết.

# Callback, Promise và Async/Await khác nhau như thế nào?
- **Callback** là một hàm nhận một hàm khác làm tham số và sẽ được gọi khi tác vụ bất đồng bộ hoàn thành.
+ Nhược điểm:
 - Callback hell( lồng nhiều callback, gây khó hiểu và bảo trì).
 - Khó xử lí lỗi( phải truyền err qua callback ).

+ Khi nào dùng?
 - Khi xử lí các tác vụ đơn giản, không lồng quá sâu.

- **Promise** là một đôi tượng đại diện cho tác vụ bất đồng bộ.
- Có 3 trạng thái: pending( chờ xử lí), fullfilled (hoàn thành), rejected( thất bại)
- Nó có thể thành công ( resolve()) hoặc thất bại(rejecte()).

* Cách hoạt động
 - Dùng .then() -> để xử lí Promise hoàn thành
 - Dùng .catch() -> để xử lí Promise lỗi.

+ Ưu điểm:
 - Tránh **callback hell**, dễ đọc, dễ hiểu.
 - Dễ xử lí lỗi hơn vì nhờ có .catch() 

+ Khi nào dùng?
 - Khi xử lí nhiều các tác vụ bất đồng bộ mà tránh dùng callback

- **Async/Await** là cách viết giúp đoạn code bất đồng bộ thành giống đồng bộ hơn. Vì **async** biến 1 hàm trả về Promise, **await** 
giúp đợi Promise hoàn thành trước khi thực hiện bước tiếp theo.

* Cách hoạt động
 - Dùng async để định nghĩa hàm bất đồng bộ.
 - Dùng await để đợi promise, thay vì dùng .then() giống ở promise.

+ Ưu Điểm
 - Tránh **callback hell**, dễ đọc, dễ hiểu.
 - Dễ xử lí lỗi hơn vì nhờ có try catch.

# Tại sao Node.js là môi trường đơn luồng (single-threaded) nhưng vẫn có thể xử lý nhiều request cùng lúc? 
Event Loop giúp kiểm soát và điều phối request mà không cần tạo nhiều luồng. Khi gặp tác vụ I/O (đọc file, truy vấn DB...), 
Node.js sẽ giao nó cho hệ điều hành xử lý. Trong thời gian đó, Node.js vẫn có thể tiếp tục nhận và xử lý các request khác thay vì 
bị chặn.

# Mô tả cách hoạt động của require() trong Node.js.
- require() trong Node.js là một hàm dùng để import module vào chương trình. Nó giúp tải các module có sẵn (built-in modules), 
module bên ngoài (installed via npm) hoặc module do người dùng tự định nghĩa.

# process.nextTick() khác gì với setTimeout(fn, 0)?
- process.nextTick
    + Độ ưu tiên RẤT cao.
    + Thực thi ngay sau khi call stack rỗng và trước khi chạy vào event loop.
    + khi bị lỗi mà gọi nextTick nhiều quá thì sẽ bị block macrotask luôn --> tràn CPU.
- setTimeout(fn, 0)
    + Độ ưu tiên thấp hơn vì nó thuộc macrotask queue.
    + Thực thi ở vòng lặp tiếp theo của event loop.

# Các module system phổ biến trong Node.js là gì? Khác nhau thế nào giữa CommonJS và ESM?
- Cú pháp: 
    + require và module.export 
    + import và export default function
- Khả năng đồng bộ và bất đồng bộ
    + CommonJS: require() là đồng bộ. Khi được yêu cầu 1 module thì nó được đọc và tải lên trước khi đoạn code được thực thi.
    + ESM: là bất đồng bộ. Nó mang lại sự tối ưu về thời gian tải và tải nguyên.
- Phạm vi và cách thực thi:
    + CommonJS: thực thi ngay lập tức, nếu có lỗi thì dừng lại toàn bộ chương trình.
    + ESM: Mô-đun ESM thực thi ngay lập tức khi import, được phân tích tĩnh trước khi thực thi.
- Caching:
    + CommonJS: Mô-đun được require() chỉ một lần và kết quả sẽ được cached (lưu vào bộ nhớ) để sử dụng lại trong các lần sau.
    + ESM: Mô-đun ESM cũng có cơ chế caching, import luôn đảm bảo rằng mô-đun đã được load từ lần gọi đầu tiên.

# Sự khác nhau giữa HTTP và HTTPS?
- HTTP là giao thức không mã hóa và không an toàn.
- HTTPS là giao thức an toàn, sử dụng mã hóa SSL/TLS để bảo vệ thông tin truyền tải và xác thực server.


