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