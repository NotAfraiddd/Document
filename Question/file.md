# Đoạn code này chạy trên môi trường nào? Có thể chạy trên trình duyệt không?
- chạy trên môi trường nodejs và không thể chạy trên trình duyệt bởi vì em dùng require() và readline

# require() là gì? Khác gì với import trong JavaScript?
- require() là cách import module trong CommonJS, còn import là từ ES6.

# Trong file File.js, tại sao bạn dùng module.exports = File;? Nếu không có dòng này thì điều gì xảy ra?
- để export class File ra. NẾU không có dòng này thfi không sd được class File

# Ở app.js, tại sao bạn dùng readline.createInterface()? Có thể thay thế bằng gì khác?
- Nhằm để đọc dữ liệu từ terminal. Có thể dùng process.stdin trực tiếp

# Trong app.js, rl.on('line', (input) => { executeCommand(input); console.log(commands); }); hoạt động thế nào?
- Khi người dùng nhập lệnh và nhấn Enter, sự kiện line được kích hoạt.
- executeCommand(input) xử lý lệnh.
- Sau khi lệnh chạy xong, danh sách các lệnh (commands) lại được in ra để nhắc nhở người dùng.

# Dự án của bạn có cấu trúc thế nào? Bạn có thể giải thích tại sao bạn tách command.js, Folder.js và File.js thành các file riêng không?
- Tách file giúp code dễ bảo trì, mỗi file quản lý một nhiệm vụ riêng

# Nếu muốn mở rộng chương trình để hỗ trợ hệ thống tệp tin ngoài đời thực (VD: truy xuất file hệ thống), bạn sẽ làm thế nào?
- Muốn truy xuất file hệ thống thật, có thể dùng fs module trong Node.js.

# Ở Folder.js, trong addFile(), tại sao bạn kiểm tra this.items[fileName] trước khi thêm file? Nếu không kiểm tra thì có rủi ro gì?
- Kiểm tra this.items[fileName] để tránh ghi đè file có sẵn.

# Nếu người dùng nhập lệnh a-file myFile.txt nhưng quên nhập nội dung file, chương trình sẽ xử lý thế nào? Làm sao để cải thiện UX trong trường hợp này?
- Nếu thiếu nội dung khi tạo file, có thể thêm check if (!content) throw new Error('Content required');.

# Khi cập nhật tên file (hàm updateNameFile), bạn kiểm tra gì trước khi đổi tên? Có trường hợp nào mà code của bạn có thể gây lỗi không?
- Trong updateNameFile(), nên kiểm tra this.items[oldName] có tồn tại không trước khi đổi tên.

# Trong search(), bạn dùng đệ quy để tìm file/folder. Nếu folder có quá nhiều cấp (VD: hàng nghìn thư mục con), điều gì có thể xảy ra? Làm sao để tối ưu hóa?
- Tìm kiếm đệ quy có thể chậm nếu dữ liệu lớn.

# display() cũng sử dụng đệ quy để in cây thư mục. Nếu có hàng nghìn tệp tin, cách in ra console có bị ảnh hưởng không? Có cách nào để hiển thị đẹp hơn không?
- Hiển thị thư mục lớn có thể bị lag, có thể phân trang hoặc giới hạn kết quả hiển thị.

# Ở Folder.js, nếu có quá nhiều phương thức (hiện tại có hơn 10 phương thức), làm sao để tổ chức code tốt hơn?
- Nếu có quá nhiều method, có thể chia nhỏ thành module FileManager.js, FolderManager.js.

# Nếu muốn lưu trữ trạng thái cây thư mục vào một file JSON trên ổ đĩa, bạn sẽ làm thế nào?
- Lưu trạng thái vào file JSON bằng cách dùng fs.writeFileSync('tree.json', JSON.stringify(root));.