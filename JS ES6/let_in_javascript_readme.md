# `let` trong JavaScript (ES6)

## 🧠 Giới thiệu

`let` là một từ khóa trong JavaScript được giới thiệu từ **ES6 (ECMAScript 2015)**.  
Nó được dùng để **khai báo biến có phạm vi khối (block scope)**, khác với `var` trước đây vốn có phạm vi hàm (function scope).

---

## 🚩 Cú pháp

```javascript
let variableName = value;
```

---

## 🔍 Đặc điểm chính của `let`

### 1. 📦 Phạm vi khối (Block Scope)
Biến được khai báo bằng `let` chỉ tồn tại trong `{}` nơi nó được khai báo.

```javascript
{
  let a = 10;
  console.log(a); // ✅ In ra 10
}
console.log(a); // ❌ Lỗi: a is not defined
```

---

### 2. 🔁 Không thể khai báo lại trong cùng một khối

```javascript
let x = 5;
let x = 10; // ❌ Lỗi: Identifier 'x' has already been declared
```

---

### 3. 🔄 Có thể gán lại giá trị

```javascript
let name = "Alice";
name = "Bob"; // ✅ Cho phép thay đổi giá trị
```

---

### 4. 🚫 Hoisting nhưng không sử dụng được trước khi khai báo

```javascript
console.log(count); // ❌ Lỗi: Cannot access 'count' before initialization
let count = 3;
```

> Biến `let` bị hoisting nhưng **nằm trong "Temporal Dead Zone"** – vùng không được truy cập trước khi khai báo.

---

### 5. 🔂 Tốt hơn `var` trong vòng lặp

```javascript
for (let i = 0; i < 3; i++) {
  setTimeout(() => {
    console.log(i); // ✅ In lần lượt 0, 1, 2
  }, 100);
}
```

> Mỗi lần lặp, `let` tạo ra một bản sao mới của biến `i`, khác với `var`.

---

## ✅ So sánh `let` và `var`

| Tính chất            | `let`         | `var`         |
|---------------------|---------------|---------------|
| Phạm vi             | Block Scope   | Function Scope |
| Hoisting            | ✅ Có, nhưng không dùng được trước khi khai báo | ✅ Có và dùng được |
| Khai báo lại        | ❌ Không       | ✅ Có thể       |
| Gán lại             | ✅ Có thể      | ✅ Có thể       |
| Vòng lặp `for`      | An toàn       | Dễ gây lỗi     |

---

## 📝 Khi nào nên dùng `let`?

- Khi bạn **cần biến có khả năng thay đổi**.
- Khi bạn muốn **giới hạn phạm vi biến trong khối `{}`**.
- Khi bạn muốn **tránh lỗi khai báo lại**.
- Khi bạn muốn an toàn hơn so với `var`.

---

## 📌 Ghi nhớ

> Hãy ưu tiên dùng `let` thay vì `var` trong JavaScript hiện đại.  
> Nếu biến không bao giờ thay đổi → dùng `const`.

---

## 📚 Tham khảo
- [MDN Web Docs - let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)