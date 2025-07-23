
# `Array.prototype.filter()` trong JavaScript

## 🧠 Giới thiệu

`filter()` là một phương thức của mảng trong JavaScript, được dùng để **tạo ra một mảng mới chứa các phần tử thỏa mãn điều kiện** do hàm callback chỉ định.  
Khác với `map()`, `filter()` có thể **loại bỏ các phần tử không phù hợp**, giúp bạn lọc dữ liệu dễ dàng.

---

## 🚩 Cú pháp

```javascript
const newArray = array.filter(callback(currentValue, index, array), thisArg);
```

- `callback`: Hàm kiểm tra điều kiện cho mỗi phần tử.
  - `currentValue`: Giá trị hiện tại của phần tử.
  - `index` *(tùy chọn)*: Chỉ số của phần tử hiện tại.
  - `array` *(tùy chọn)*: Mảng đang được xử lý.
- `thisArg` *(tùy chọn)*: Giá trị dùng làm `this` trong callback.

---

## 🔍 Đặc điểm chính

### 1. ✅ Lọc các phần tử thỏa điều kiện

```javascript
const numbers = [1, 2, 3, 4, 5];
const even = numbers.filter(n => n % 2 === 0);
console.log(even); // [2, 4]
```

---

### 2. 🧪 Không làm thay đổi mảng gốc

```javascript
const data = [10, 20, 30];
data.filter(x => x > 15);
console.log(data); // [10, 20, 30]
```

---

### 3. 🚫 Bỏ qua phần tử không thỏa

`filter()` chỉ giữ lại phần tử mà callback trả về `true`.

```javascript
const names = ["Alice", "Bob", "Charlie"];
const shortNames = names.filter(name => name.length <= 3);
console.log(shortNames); // ['Bob']
```

---

### 4. ⚠️ Bỏ qua phần tử "trống" (sparse)

```javascript
const arr = [1, , 3];
const result = arr.filter(x => true);
console.log(result); // [1, 3]
```

> Phần tử trống không được callback xử lý.

---

### 5. 🔁 Dễ kết hợp với `map()`, `reduce()`

```javascript
const numbers = [1, 2, 3, 4, 5];
const squaredEven = numbers
  .filter(n => n % 2 === 0)
  .map(n => n ** 2);
console.log(squaredEven); // [4, 16]
```

---

## ✅ Khi nào nên dùng `filter()`?

- Khi bạn cần **lấy ra một phần dữ liệu từ mảng**.
- Khi bạn muốn **loại bỏ phần tử không thỏa điều kiện**.
- Khi muốn **viết code ngắn gọn và rõ ràng**.

---

## 📌 Ghi nhớ

> `filter()` = lọc các phần tử thỏa điều kiện → trả về mảng mới.  
> Nếu bạn chỉ muốn duyệt và xử lý mà không trả mảng → dùng `forEach()`.

---

## 📚 Tham khảo

- [MDN Web Docs - Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
