# `const` trong JavaScript (ES6)

## 🧠 Giới thiệu

`const` là một từ khóa trong JavaScript được giới thiệu từ **ES6 (ECMAScript 2015)**.  
Nó được dùng để **khai báo hằng số** – tức là **biến không thể gán lại giá trị sau khi khai báo**.  
Giống như `let`, `const` cũng có **phạm vi khối (block scope)**.

---

## 🚩 Cú pháp

```javascript
const variableName = value;
```

> Phải gán giá trị ngay khi khai báo.

---

## 🔍 Đặc điểm chính của `const`

### 1. 📦 Phạm vi khối (Block Scope)

```javascript
{
  const PI = 3.14;
  console.log(PI); // ✅ In ra 3.14
}
console.log(PI); // ❌ Lỗi: PI is not defined
```

---

### 2. ❌ Không thể khai báo lại hoặc gán lại

```javascript
const x = 5;
x = 10; // ❌ Lỗi: Assignment to constant variable

const x = 15; // ❌ Lỗi: Identifier 'x' has already been declared
```

---

### 3. ✅ Với đối tượng và mảng: không thể gán lại, nhưng có thể thay đổi nội dung

```javascript
const arr = [1, 2, 3];
arr.push(4); // ✅ Cho phép
console.log(arr); // [1, 2, 3, 4]

arr = [5, 6]; // ❌ Lỗi: Assignment to constant variable
```

Tương tự với object:

```javascript
const person = { name: "Alice" };
person.name = "Bob"; // ✅ Được phép
person = {}; // ❌ Lỗi
```

---

### 4. 🚫 Hoisting nhưng không sử dụng được trước khi khai báo

```javascript
console.log(a); // ❌ Lỗi: Cannot access 'a' before initialization
const a = 10;
```

Giống `let`, `const` cũng có "Temporal Dead Zone".

---

## ✅ So sánh `const`, `let`, `var`

| Tính chất            | `const`       | `let`         | `var`         |
|---------------------|---------------|---------------|---------------|
| Phạm vi             | Block Scope   | Block Scope   | Function Scope |
| Hoisting            | ✅ Có, nhưng không dùng được trước khi khai báo | ✅ Có, nhưng không dùng được trước khi khai báo | ✅ Có và dùng được |
| Khai báo lại        | ❌ Không       | ❌ Không       | ✅ Có thể       |
| Gán lại             | ❌ Không       | ✅ Có thể      | ✅ Có thể       |
| Dùng cho giá trị cố định | ✅ Rất phù hợp | ❌ Không phù hợp | ❌ Không phù hợp |

---

## 📝 Khi nào nên dùng `const`?

- Khi bạn muốn **giá trị không thay đổi sau khi khai báo**.
- Khi bạn muốn **bảo vệ giá trị khỏi việc bị gán lại**.
- Nên dùng mặc định `const` và chỉ dùng `let` khi thực sự cần gán lại.

---

## 📌 Ghi nhớ

> `const` không cho phép gán lại, nhưng nếu là object hoặc array thì vẫn có thể thay đổi nội dung bên trong.

---

## 📚 Tham khảo
- [MDN Web Docs - const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)