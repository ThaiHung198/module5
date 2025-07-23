# Arrow Functions trong JavaScript (ES6)

## 🧠 Giới thiệu

Arrow function (`=>`) là cách viết hàm ngắn gọn trong JavaScript được giới thiệu từ **ES6 (2015)**.  
Chúng giúp viết code ngắn gọn hơn và có cách **xử lý `this` khác với function truyền thống**.

---

## 🚩 Cú pháp cơ bản

```javascript
const func = (param1, param2) => {
  // thân hàm
};
```

Nếu chỉ có một tham số:

```javascript
const greet = name => {
  console.log("Hello " + name);
};
```

Nếu chỉ có một dòng trả về:

```javascript
const square = x => x * x;
```

Nếu không có tham số:

```javascript
const sayHi = () => console.log("Hi!");
```

---

## 🔍 Đặc điểm chính

### 1. ✂️ Ngắn gọn hơn

```javascript
// Truyền thống
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

---

### 2. 🚫 Không có `this` riêng

Arrow function **không có `this` riêng**, mà kế thừa từ phạm vi bao ngoài.

```javascript
function Timer() {
  this.seconds = 0;
  setInterval(() => {
    this.seconds++;
    console.log(this.seconds); // ✅ đúng vì arrow dùng `this` từ Timer
  }, 1000);
}
```

Với function thường, `this` sẽ bị mất trong `setInterval`.

---

### 3. ❌ Không dùng làm constructor

```javascript
const Person = (name) => {
  this.name = name;
};
const p = new Person("Alice"); // ❌ Lỗi: arrow function không dùng với `new`
```

---

### 4. ❌ Không có `arguments` object

Arrow function **không có biến đặc biệt `arguments`**.

```javascript
const test = () => {
  console.log(arguments); // ❌ Lỗi
};
```

Dùng rest parameter thay thế:

```javascript
const test = (...args) => {
  console.log(args); // ✅
};
```

---

## ✅ Khi nào dùng Arrow Function?

- Khi cần viết hàm ngắn gọn, không cần `this`, `arguments`, hay dùng `new`.
- Rất phù hợp với:
  - Hàm callback
  - Array methods (`map`, `filter`, `reduce`)
  - Các xử lý không liên quan đến ngữ cảnh `this`

---

## 📌 Ghi nhớ

| Đặc điểm                     | Arrow Function | Function thường |
|-----------------------------|----------------|------------------|
| Cú pháp ngắn                | ✅              | ❌               |
| Có `this` riêng             | ❌              | ✅               |
| Có `arguments`              | ❌              | ✅               |
| Dùng làm constructor        | ❌              | ✅               |
| Dùng cho callback, xử lý nhẹ| ✅              | ✅               |

---

## 📚 Tham khảo
- [MDN Web Docs - Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)