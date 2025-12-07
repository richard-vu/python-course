# **What is a Tuple? / Tuple là gì?**

  * **English:** A tuple is a built-in data type in Python used to store multiple items in a single variable. It is similar to a list, but with one key difference: tuples are **immutable**. This means once you create a tuple, you cannot change, add, or remove items from it.
  * **Tiếng Việt:** Tuple là một kiểu dữ liệu có sẵn trong Python dùng để lưu trữ nhiều phần tử trong một biến duy nhất. Nó tương tự như danh sách (list), nhưng có một điểm khác biệt chính: tuple có tính **bất biến (immutable)**. Nghĩa là một khi bạn đã tạo tuple, bạn không thể thay đổi, thêm, hoặc xóa các phần tử bên trong nó.

-----

# **Key Characteristics / Đặc điểm chính**

1.  **Ordered (Có thứ tự):**

      * **En:** The items have a defined order, and that order will not change. You can access items by index (e.g., `my_tuple[0]`).
      * **Vi:** Các phần tử được sắp xếp theo trật tự xác định và trật tự đó sẽ không thay đổi. Bạn có thể truy cập phần tử bằng chỉ số (ví dụ: `my_tuple[0]`).

2.  **Immutable (Bất biến):**

      * **En:** You cannot modify the tuple after it is created. This makes tuples faster and safer for data that shouldn't change (like coordinates or configuration settings).
      * **Vi:** Bạn không thể sửa đổi tuple sau khi tạo. Điều này giúp tuple xử lý nhanh hơn và an toàn hơn cho các dữ liệu không nên bị thay đổi (như tọa độ hoặc cài đặt cấu hình).

3.  **Allow Duplicates (Cho phép trùng lặp):**

      * **En:** Tuples can contain items with the same value.
      * **Vi:** Tuple có thể chứa các phần tử có giá trị giống nhau.

4.  **Syntax (Cú pháp):**

      * **En:** Tuples are written with round brackets `()`.
      * **Vi:** Tuple được viết bằng dấu ngoặc tròn `()`.

-----

# **Examples / Ví dụ**

## 1. Creating a Tuple (Tạo Tuple)

```python
# English: A tuple with mixed data types
# Tiếng Việt: Một tuple chứa nhiều kiểu dữ liệu khác nhau
my_info = ("John", 25, "Engineer")

# English: A tuple with a single item (note the comma)
# Tiếng Việt: Tuple có một phần tử (chú ý dấu phẩy)
one_item = ("Apple",) 
# Note: ("Apple") without a comma is a String, not a Tuple.
```

## 2. Accessing Items (Truy cập phần tử)

```python
coordinates = (10.5, 20.1, 33.8)

print(coordinates[0]) 
# Output: 10.5
```

### 3. Attempting to Change (Cố ý thay đổi - Lỗi)

```python
fruits = ("apple", "banana", "cherry")

# English: This will raise a TypeError because tuples are immutable.
# Tiếng Việt: Dòng này sẽ gây lỗi TypeError vì tuple là bất biến.
# fruits[1] = "orange"  <-- Error!
```

-----

### **Tuple vs. List: When to use? / Khi nào dùng Tuple hay List?**

| Feature | **List** `[]` | **Tuple** `()` |
| :--- | :--- | :--- |
| **Mutable?** (Có thể sửa đổi?) | **Yes / Có** (Add, remove, change items) | **No / Không** (Read-only / Chỉ đọc) |
| **Speed** (Tốc độ) | Slower (Chậm hơn) | Faster (Nhanh hơn) |
| **Use Case** (Trường hợp dùng) | Collections of data that may change (e.g., shopping cart). <br> *Dữ liệu có thể thay đổi (vd: giỏ hàng).* | Data that should remain constant (e.g., months of the year). <br> *Dữ liệu cần cố định (vd: các tháng trong năm).* |

