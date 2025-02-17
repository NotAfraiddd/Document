# Next.js là gì và tại sao nên sử dụng?
NextJS là một framework của ReactJS, giúp xây dựng các website SSR, và static site(SSG). Nó cải thiện hiệu suất, SEO và mang lại trải nghiệm tốt cho người dùng
# Khác biệt giữa SSR và SSG trong Next.js là gì?
**SSR:** mỗi lần có request từ Client, thì server nó sẽ xử lí logic, render trang HTML + CSS dựa vào dữ liệu lấy được và gửi HTML + CSS đó về cho client

**SSG:** trong lần build time lần đầu tiên, nó sẽ tìm và chạy toàn bộ `getStaticProps` ở tất cả các trang đó xong rồi. Dựa vào dữ liệu đó NextJS sẽ  render HTML tĩnh cho mỗi trang. Các trang HTML tĩnh, CSS, và JavaScript được tạo ra và lưu sẵn trên server.

**NOTE** nếu có `getServerSideProps` or `getStaticProps` thì nó sẽ xử lí trước rồi dựa vào dữ liệu đó để trả về HTML+CSS như trên.

# Cách thức tạo một API route trong Next.js?
Trong Next.js, bạn có thể tạo các API route bằng cách thêm tệp JavaScript hoặc TypeScript vào thư mục pages/api. Ví dụ, để tạo một API đơn giản trả về JSON:
```
// pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello, World!' });
}
```

# Cách sử dụng dynamic import trong Next.js? Ưu nhược điểm?

```
import dynamic from 'next/dynamic';

const DynamicComponent = dynamic(() => import('../components/DynamicComponent'));

export default function Home() {
  return <DynamicComponent />;
}
```

Import bình thường thì được gọi là **static import**, code được tải ngay khi ứng dụng khởi động, không có sự trì hoãn. Nhược điểm phải nhờ `tree-shaking` để loại bỏ code không cần thiết.

còn `dynamic import` thì code sẽ được tải khi cần thiết, giảm kích thước tải ban đầu nhưng sẽ tạo ra độ trễ của component đó.

# Giải thích về Dependency Injection trong Node.js?
+ không sử dụng Dependency Injection thì constructor từ các service không thể linh hoạt, vì nó tạo trực tiếp một instance từ DatabaseService trong constructor, làm nó
phụ thuộc chặt chẽ vào DatabaseService.
+ Sử dụng Dependency Injection, DatabaseService được truyền từ bên ngoài vào UserService thông qua constructor

# Làm thế nào để chuyển hướng (redirect) trong Next.js?
+ Sử dụng `<Link/>` dùng trong chuyển hướng giao diện
+ Sử dụng `useRouter.push` dùng trong chuyển hướng sự kiện như click,..
+ Sử dụng `redirect` trong getServerSideProps() dùng trong chuyển hướng ở server, bảo mật.
  ```
  export async function getServerSideProps(context) {
    return {
      redirect: {
        destination: '/login', // Chuyển hướng đến trang login
        permanent: false, // false = 302 (tạm thời), true = 301 (vĩnh viễn)
      },
    };
  }
  ```
# Cách sử dụng next/link để điều hướng giữa các trang?
- Có thể sử dụng để redirect nhanh mà không cần phải reload lại trang giống thẻ a href
- Có hỗ trợ truyền query parameters, history không cần ghi lại, replace thì giữ đúng vị trí cuộn scroll.

# NestJS là gì? So sánh NestJS với ExpressJS?
- NestJS là framework của nodeJS.
- NestJS có kiến trúc MVC, dependency injection cùng với các tính năng khác như middleware, pipes, guards, và interceptors.
--> Phù hợp cho các dự án lớn và phức tạp.

- ExpressJS là framework của NodeJS
- Dễ dàng tích hợp các thư viện khác như passport...
--> Phù hợp cho các dự án nhỏ, tích hợp nhanh, dễ dàng sử dụng.