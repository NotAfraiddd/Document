# Functional Components Lifecycle (Sử dụng Hooks)
+ **componentDidMount(Mounting)**: useEffect(() => {...}, []) sẽ thực thi lần đầu khi component mount.
+ **componentDidUpdate(Updating)**: useEffect(() => {...}, [dependencies]) sẽ thực thi khi dependencies thay đổi.
+ **componentWillUnmount(Unmounting)**: Bạn có thể return một function từ useEffect, và hàm này sẽ được gọi khi component unmount.

# Làm thế nào để tránh rerender?
Có 3 trường hợp bị re-render:
 + State
 + Prop
 + Component cha bị thay đổi, thì component con bị rerender

Để tránh re-render không cần thiết, sử dụng React.memo. => sử dụng cho **functional component**
```
const ChildB = React.memo(() => {
  console.log('ChildB re-rendered');
  return <p>Child B - No props</p>;
});
```

**class component** thì sử dụng `shouldComponentUpdate`. nó sẽ trả về true/false
```
shouldComponentUpdate(nextProps, nextState) {
if (this.props.count === nextProps.count) {
    return false; // Không cần re-render nếu count không thay đổi
}
return true; // Re-render nếu count thay đổi
}

render() {
console.log('Counter component re-rendered');
return <h1>{this.props.count}</h1>;
}
```
# Khi nào bạn nên sử dụng useCallback và useMemo trong React?
**useCallback()**: Dùng để ghi nhớ một hàm, giúp tránh việc tạo mới hàm trong mỗi lần render.

**useMemo()**: Dùng để ghi nhớ giá trị được tính toán, giúp tránh tính toán lại khi các dependencies không thay đổi.

**NOTE**
React thực hiện **shallow comparison** nên sử dụng **useCallback** cho **hàm** thôi. Còn nếu prop **không phải hàm** thì không 
nên sử dụng.

- **Props là giá trị nguyên thủy ( number, string, boolean )**: Thì sẽ sử dụng **React.memo** ở component con luôn vì nếu giá trị 
prop không thay đổi thì không bị render lại.
- **Props là object hay array**: Thì cho dù **prop không thay đổi** gì hết nhưng React sẽ xem đó là **tạo ra một prop mới**, 
khiến component bị render.

# Tạo 1 Hook bất kì? Giải thích ?

```
import { useState, useCallback } from "react";

const useToggle = (initialValue = false) => {
  const [state, setState] = useState(initialValue);

  const toggle = useCallback(() => {
    setState((prevState) => !prevState);
  }, []);

  return [state, toggle];
};

export default useToggle;
```

### Note: Tại sao lại sử dụng useCallback trong tình huống này?
Bởi vì, muốn cải thiện việc rerender khi không cần thiết. Hàm `toggle` trong `useToggle` sẽ không bị **TẠO MỚI** sau mỗi lần HOOK này được sử dụng 

# Phân biệt call, apply, bind.
```
const person = {
    name: "Alice",
    greet: function (message) {
        console.log(${message}, my name is ${this.name});
    }
};
const anotherPerson = { name: "Bob" };
```
**call():** gọi hàm ngay, nhưng truyền tham số riêng lẽ.
  - ví dụ: person.greet.call(anotherPerson,"Hello");

**bind():** Không gọi hàm ngay, nhưng trả về một hàm mới.

```
const newGreet = person.greet.bind(anotherPerson, "Hey");
newGreet();  
👉 Output: "Hey, my name is Bob"
```
======================

```
const person = {
    name: "Alice",
    greet: function (greeting, punctuation) {
        console.log(`${greeting}, my name is ${this.name}${punctuation}`);
    }
};
const anotherPerson = { name: "Bob" };
```

**apply():** gọi hàm ngay, nhưng truyền tham số là mảng.
 - ví dụ: person.greet.apply(anotherPerson,["Hello","!"]);
 --> output:  "Hello, my name is Bob!"

