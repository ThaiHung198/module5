
# `Array.prototype.map()` trong JavaScript

## 🧠 Giới thiệu

`map()` là một phương thức của mảng trong JavaScript, được sử dụng để **tạo ra một mảng mới** bằng cách **áp dụng một hàm lên từng phần tử** của mảng gốc mà **không thay đổi mảng ban đầu**.

---

## 🚩 Cú pháp

```javascript
const newArray = array.map(callback(currentValue, index, array), thisArg);
```

- `callback`: Hàm được gọi cho mỗi phần tử.
  - `currentValue`: Giá trị của phần tử hiện tại.
  - `index` *(tùy chọn)*: Chỉ số của phần tử hiện tại.
  - `array` *(tùy chọn)*: Mảng gốc đang được gọi `map()`.
- `thisArg` *(tùy chọn)*: Giá trị dùng làm `this` trong callback.

---

## 🔍 Đặc điểm chính

### 1. 📦 Trả về mảng mới

`map()` không làm thay đổi mảng ban đầu, mà trả về **một mảng mới với số phần tử bằng nhau**.

```javascript
const numbers = [1, 2, 3];
const doubled = numbers.map(x => x * 2);
console.log(doubled); // [2, 4, 6]
```

---

### 2. 🔁 Duyệt từng phần tử

`map()` sẽ gọi hàm callback cho **mọi phần tử** (bao gồm cả `undefined` nếu phần tử đó tồn tại).

```javascript
const words = ['a', 'b', 'c'];
const upper = words.map(letter => letter.toUpperCase());
console.log(upper); // ['A', 'B', 'C']
```

---

### 3. 🧪 Không thay đổi mảng ban đầu

```javascript
const arr = [10, 20, 30];
arr.map(x => x + 1);
console.log(arr); // [10, 20, 30] — mảng cũ không thay đổi
```

---

### 4. ⚠️ Bỏ qua phần tử "trống"

```javascript
const arr = [1, , 3];
arr.map(x => x * 2); // [2, , 6]
```

> Phần tử bị thiếu (sparse elements) sẽ **bị bỏ qua**, callback không được gọi cho phần tử đó.

---

### 5. 🧠 Dễ kết hợp với các hàm mảng khác

`map()` thường được kết hợp với `filter()`, `reduce()`...

```javascript
const data = [1, 2, 3, 4, 5];
const result = data
  .filter(x => x % 2 === 0)
  .map(x => x * 10);
console.log(result); // [20, 40]
```

---

## ✅ Khi nào nên dùng `map()`?

- Khi cần **biến đổi từng phần tử** của mảng.
- Khi muốn **giữ nguyên mảng gốc**.
- Khi muốn **viết code ngắn gọn, dễ hiểu** theo kiểu hàm (functional style).

---

## 📌 Ghi nhớ

> `map()` = duyệt qua từng phần tử → trả về một mảng mới với giá trị đã được biến đổi.  
> Nếu bạn không cần trả về mảng mới → dùng `forEach()` thay vì `map()`.

---

## 📚 Tham khảo

- [MDN Web Docs - Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
