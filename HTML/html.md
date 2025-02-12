# Sự khác nhau giữa <strong> và <b>, <em> và <i> trong HTML
* Sự khác nhau giữa <strong> và <b>
    - strong,em: SEO tốt, có ỹ nghĩa về semantic
    - b,i: không có ảnh hưởng tới SEO, không có ỹ nghĩa semantic

# data-* là gì sử dụng như nào?
- Là dùng để truyền dữ liệu từ HTML sang JS
```
<button id="btn" data-user-id="123" data-role="admin">Nhấn vào đây</button>
const button = document.getElementById("btn");
console.log(button.dataset.userId); // "123"
console.log(button.dataset.role);   // "admin"
```

