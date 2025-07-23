
# `Array.prototype.reduce()` trong JavaScript

## 🧠 Giới thiệu

`reduce()` là một phương thức của mảng trong JavaScript, được dùng để **rút gọn mảng thành một giá trị duy nhất** bằng cách **lặp qua từng phần tử và tích lũy kết quả**.  
Nó rất mạnh khi bạn cần tính tổng, đếm, gom nhóm, hoặc biến đổi cấu trúc dữ liệu.

---

## 🚩 Cú pháp

```javascript
const result = array.reduce(callback(accumulator, currentValue, index, array), initialValue);
```

- `callback`: Hàm xử lý từng phần tử.
  - `accumulator`: Giá trị tích lũy qua mỗi lần gọi.
  - `currentValue`: Giá trị hiện tại trong vòng lặp.
  - `index` *(tùy chọn)*: Chỉ số của phần tử hiện tại.
  - `array` *(tùy chọn)*: Mảng đang được xử lý.
- `initialValue`: Giá trị khởi đầu của `accumulator` *(bắt buộc nên cung cấp)*.

---

## 🔍 Đặc điểm chính

### 1. ➕ Tính tổng các giá trị

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, val) => acc + val, 0);
console.log(sum); // 10
```

---

### 2. 🔢 Đếm số lượng phần tử thỏa điều kiện

```javascript
const fruits = ["🍎", "🍊", "🍎", "🍇"];
const count = fruits.reduce((acc, fruit) => {
  acc[fruit] = (acc[fruit] || 0) + 1;
  return acc;
}, {});
console.log(count); // { '🍎': 2, '🍊': 1, '🍇': 1 }
```

---

### 3. 🧱 Biến đổi mảng thành object

```javascript
const people = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" }
];

const peopleMap = people.reduce((acc, person) => {
  acc[person.id] = person.name;
  return acc;
}, {});
console.log(peopleMap); // { '1': 'Alice', '2': 'Bob' }
```

---

### 4. 🧪 Không làm thay đổi mảng gốc

```javascript
const arr = [1, 2, 3];
arr.reduce((acc, val) => acc + val, 0);
console.log(arr); // [1, 2, 3]
```

---

### 5. ⚠️ Nếu không truyền `initialValue`

Nếu không truyền `initialValue`, `reduce()` sẽ dùng phần tử đầu tiên làm `accumulator`, bắt đầu từ phần tử thứ hai.

```javascript
const numbers = [5, 10, 15];
const result = numbers.reduce((acc, val) => acc + val);
console.log(result); // 30
```

> ⚠️ Tuy nhiên, việc không cung cấp `initialValue` có thể gây lỗi nếu mảng rỗng.

---

## ✅ Khi nào nên dùng `reduce()`?

- Khi bạn cần **tính toán tổng, tích, đếm, hoặc gom nhóm dữ liệu**.
- Khi bạn muốn **rút gọn mảng về một giá trị duy nhất**.
- Khi cần thao tác dữ liệu phức tạp trong 1 bước.

---

## 📌 Ghi nhớ

> `reduce()` rất mạnh mẽ nhưng có thể khó đọc. Hãy sử dụng khi bạn hiểu rõ logic tích lũy.  
> Đừng quên truyền `initialValue` để đảm bảo an toàn!

---

## 📚 Tham khảo

- [MDN Web Docs - Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
