# Câu 1: Nginx đóng vai trò gì trong docker?
- Nginx như một Reverse Proxy đóng vai trò nhận các yêu cầu từ frontend và chuyển tiếp chúng xuống backend thông qua cổng được xác định trước.
Ví dụ: 8085:80, 8085 là cổng mà chúng ta set trước đó dành cho docker.compose.yml để map cổng của máy chủ Nginx từ container ra môi trường 
host. Có nghĩa là bất cứ request gửi đến cổng 8085 thì sẽ được chuyển đến 80 trong container Nginx