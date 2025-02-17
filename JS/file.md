
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
    VD: function Sum(a,b) {}
- function expression ( biểu thức hàm):
    + Không được hoisted.
    VD: const sum = function Sum(a,b) {}
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

# Middleware trong Express.js là gì? 
- Middleware trong Express.js là các hàm trung gian được thực thi trong quá trình xử lý request trước khi response được gửi đến client.
    + Tạo middleware riêng biệt (UsersMiddleware.ts, ShopsMiddleware.ts).
    + Đăng ký middleware riêng trong AppModule với forRoutes('users') và forRoutes('shops').
    + Mỗi route có middleware riêng biệt, đảm bảo code rõ ràng và dễ bảo trì.

# Cách sử dụng dotenv để quản lý biến môi trường (environment variables)?
- dotenv là một thư viện giúp bạn quản lý các biến môi trường trong dự án Node.js thông qua file .env, giúp tách biệt thông tin nhạy 
cảm như API keys, database credentials khỏi mã nguồn.

+ Cài đặt dotenv bằng npm install dotenv
+ Tạo file .env để chứa biến môi trường (KEY=VALUE)
+ Load dotenv trong code bằng require('dotenv').config()
+ Không push file .env lên Git bằng cách thêm vào .gitignore
+ Có thể dùng dotenv-safe để đảm bảo tất cả biến cần thiết đều có giá trị
💡 Lưu ý: Nếu deploy trên cloud server như AWS hoặc Heroku, có thể đặt biến môi trường trực tiếp mà không cần .env.

# So sánh fs.readFileSync vs fs.readFile vs fs.createReadStream
fs.readFileSync:
 + Cách hoạt động: Đợi kết quả trước khi chạy tiếp.
 + Ưu điểm: Đơn giản, dễ hiểu.
 + Nhược điểm: Chặn chương trình, gây lag nếu xử lý dữ liệu lớn.
 + Khi nào dùng?: Khi xử lý đơn giản, file nhỏ.
fs.readFile:
 + Cách hoạt động: Không đợi, chạy tiếp ngay lập tức.
 + Ưu điểm: Không bị chặn, nhanh hơn so với blocking.
 + Nhược điểm: Cần dùng callback/Promise để xử lý dữ liệu.
 + Khi nào dùng?: Xử lý I/O, đọc API, truy vấn Database.
fs.createReadStream:
 + Cách hoạt động: Đọc/Ghi từng phần nhỏ (chunk) thay vì toàn bộ file.
 + Ưu điểm: Tiết kiệm RAM, tối ưu cho file lớn.
 + Nhược điểm: Cần xử lý sự kiện, phức tạp hơn một chút.
 + Khi nào dùng?: Khi xử lý file lớn, stream video, log.

# JSON Web Token (JWT) là gì? Tại sao cần sử dụng?
- JWT (JSON Web Token) là một chuẩn mã hóa thông tin dạng chuỗi JSON, được sử dụng trong xác thực người dùng (authentication) và phân quyền truy cập (authorization).
- cấu trúc gồm 3 phần: Header.Payload.Signature
    + Header: Chứa thông tin về thuật toán mã hóa, thường là HS256 hoặc RS256.
    + Payload: Chứa dữ liệu (claims), có thể là user ID, role, v.v.
    + Signature: Chữ ký số để đảm bảo JWT không bị giả mạo.
- Cách hoạt động:
    + User đăng nhập → Server xác thực thông tin & tạo JWT.
    + Server trả về JWT cho client (trình duyệt, mobile app, v.v.).
    + Client gửi JWT trong Authorization header của mỗi request.
    + Server kiểm tra JWT → Nếu hợp lệ, trả về dữ liệu → Nếu không, từ chối truy cập.

# CORS là gì? Cách cấu hình CORS trong NestJS?
- CORS (Cross-Origin Resource Sharing) là một cơ chế bảo mật của trình duyệt ngăn chặn hoặc cho phép các request được gửi từ một domain khác với domain của server.

#  So sánh Cluster vs Worker Threads
- Cluster
    + Cách hoạt động: nhiều process.
    + Chia sẻ bộ nhớ: Không( mỗi process riêng biệt)
    + Tính toán nặng: Không tốt, do cần truyền dữ liệu giữa các process.
    + Tốc độ khởi tạo: chậm do khởi tạo process mới.
    + Khi nào dùng: xử lí nhiều request song song.
- Worker Threads
    + Cách hoạt động: nhiều thread trong cùng 1 process.
    + Chia sẻ bộ nhớ: có bằng cách dùng sharedArrayBuffer.
    + Tính toán nặng: Tốt, vì có thể chia sẻ bộ nhớ
    + Tốc độ khởi tạo: Nhanh hơn (do chỉ tạo thread)
    + Khi nào dùng: Xử lý tác vụ tính toán nặng, chia sẻ bộ nhớ

# Khi nào nên sử dụng Redis trong ứng dụng Node.js?
- Redis là một hệ thống lưu trữ dữ liệu dạng key-value trên RAM.
- Khi nào nên dùng:
    + Rate Limiting (Giới hạn số request): Giới hạn số request từ một IP để tránh spam hoặc tấn công DDOS.
```
    const limiter = rateLimit({
    store: new RedisStore({ sendCommand: (...args) => redisClient.call(...args) }),
    windowMs: 60 * 1000, // 1 phút
    max: 10, // Tối đa 10 request mỗi phút
    });
```
    + Caching: API cần phản hồi nhanh, giảm tải DB
    + Session Management: Lưu session user khi dùng JWT/session-based auth. --> thích hợp cho SSR.

# WebSocket là gì? Khi nào sử dụng WebSocket thay vì HTTP?
- WebSocket là một giao thức giao tiếp hai chiều giữa client và server trên một kết nối TCP duy nhất.

- Lợi ích của WebSocket so với HTTP
    + Duy trì kết nối liên tục, không cần request lại từ client.
    + Độ trễ thấp, tối ưu cho dữ liệu real-time.
    + Giảm băng thông, vì không gửi lại headers mỗi lần như HTTP.

# Cách tối ưu hiệu suất một API trong Node.js?
- Tối ưu Truy vấn Database:
    + Sử dụng index trong database để tăng tốc độ truy vấn.
    + Chỉ lấy những trường cần thiết
    + Phân trang (Pagination)
    + Sử dụng cache (Redis)
- Sử dụng Caching (Bộ nhớ đệm): Redis giúp giảm tải database bằng cách lưu dữ liệu vào bộ nhớ đệm.
- Sử dụng Asynchronous & Streaming:
    + Dùng async/await hoặc streaming để xử lý dữ liệu lớn hiệu quả hơn.
    + Dùng fs.createReadStream thay vì fs.readFileSync khi đọc file lớn
- Tối ưu Middleware & Request Handling
    + Giới hạn request bằng express-rate-limit để tránh DDOS
    + Dùng compression để giảm kích thước response.
- Sử dụng GraphQL nếu cần API linh hoạt