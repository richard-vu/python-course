## **Python Debugging Reference (English - Vietnamese)**
*Tài liệu tham khảo lệnh Debug Python*

### 1. Starting the Debugger (Khởi động trình gỡ lỗi)

| Command / Code | English Description | Vietnamese Description |
| :--- | :--- | :--- |
| `python -m pdb file.py` | **Start from CLI:** Runs the script under the debugger from the very beginning. | **Chạy từ dòng lệnh:** Chạy script dưới chế độ debug ngay từ dòng đầu tiên. |
| `breakpoint()` | **Inline Code:** Place this inside your Python script where you want to pause. | **Trong mã nguồn:** Đặt lệnh này vào trong code tại vị trí bạn muốn chương trình dừng lại. |
| `import pdb; pdb.set_trace()` | **Inline Code (Legacy):** Old way to set a breakpoint (for Python < 3.7). | **Trong mã nguồn (Cũ):** Cách cũ để đặt điểm dừng (dành cho Python phiên bản thấp hơn 3.7). |

---

### 2. Execution Control (Điều khiển luồng chạy)

Đây là nhóm lệnh quan trọng nhất để di chuyển qua từng dòng code.

| Key | Command | English Description | Vietnamese Description |
| :--- | :--- | :--- | :--- |
| **`n`** | `next` | **Execute next line.** Runs the current line and stops at the next one. Does *not* enter functions. | **Chạy dòng tiếp theo.** Thực thi dòng hiện tại và dừng ở dòng kế tiếp. *Không* đi sâu vào bên trong hàm con. |
| **`s`** | `step` | **Step into.** Execute the current line. If it's a function call, stop inside that function. | **Đi vào hàm.** Thực thi dòng hiện tại. Nếu dòng đó gọi một hàm, trình debug sẽ nhảy vào bên trong hàm đó. |
| **`c`** | `continue` | **Continue execution.** Runs until the next breakpoint or script execution ends. | **Tiếp tục chạy.** Chạy một mạch cho đến khi gặp điểm dừng (breakpoint) tiếp theo hoặc hết chương trình. |
| **`r`** | `return` | **Return.** Continue execution until the current function returns. | **Về đích hàm.** Chạy tiếp cho đến khi hàm hiện tại thực hiện xong (gặp lệnh return). |
| **`q`** | `quit` | **Quit debugger.** Abort the program and exit. | **Thoát.** Hủy bỏ chương trình và thoát khỏi chế độ debug. |

---

### 3. Inspection & Context (Kiểm tra dữ liệu & Ngữ cảnh)

Nhóm lệnh dùng để xem giá trị biến và code xung quanh.

| Key | Command | English Description | Vietnamese Description |
| :--- | :--- | :--- | :--- |
| **`p`** | `print` | **Print variable.** Evaluate and print the value of an expression. (e.g., `p my_var`). | **In biến.** Tính toán và in ra giá trị của biến hoặc biểu thức. (Ví dụ: `p bien_x`). |
| **`pp`** | `pretty print` | **Pretty print.** Print complex structures (dictionaries, lists) in a readable format. | **In đẹp.** In các cấu trúc dữ liệu phức tạp (như dictionary, list) theo dạng dễ đọc, có xuống dòng. |
| **`l`** | `list` | **List source code.** Show 11 lines of source code around the current line. | **Hiển thị code.** Hiện 11 dòng code xung quanh vị trí hiện tại để bạn biết mình đang ở đâu. |
| **`ll`** | `long list` | **List all source.** List all source code for the current function. | **Hiển thị toàn bộ.** Hiện toàn bộ code của hàm hiện tại. |
| **`w`** | `where` | **Print stack trace.** Show which function called the current function (useful for nested calls). | **Truy vết.** Hiển thị ngăn xếp gọi hàm (để biết hàm nào đã gọi hàm hiện tại). |
| **`a`** | `args` | **Print arguments.** Print the argument list of the current function. | **In tham số.** In ra danh sách các tham số đầu vào của hàm hiện tại. |

---

### 4. Breakpoints Management (Quản lý điểm dừng)

| Key | Command | English Description | Vietnamese Description |
| :--- | :--- | :--- | :--- |
| **`b`** | `break` | **Set breakpoint.** Set a break at a line number (e.g., `b 10`) or function name (e.g., `b my_func`). | **Đặt điểm dừng.** Đặt breakpoint tại số dòng (vd: `b 10`) hoặc tên hàm (vd: `b ten_ham`). |
| **`b`** | `break` (alone) | **List breakpoints.** List all breakpoints currently set. | **Liệt kê điểm dừng.** Xem danh sách tất cả các breakpoint đang có. |
| **`cl`** | `clear` | **Clear breakpoint.** Remove a breakpoint (e.g., `cl 1` clears breakpoint #1). | **Xóa điểm dừng.** Xóa một breakpoint (vd: `cl 1` để xóa breakpoint số 1). |

---

### 5. Vocabulary Summary (Tổng hợp từ vựng)

* **Debugger:** Trình gỡ lỗi.
* **Breakpoint:** Điểm ngắt / Điểm dừng.
* **Expression:** Biểu thức.
* **Evaluate:** Đánh giá / Tính toán giá trị.
* **Stack Trace:** Vết ngăn xếp (Lịch sử gọi hàm).
* **Scope:** Phạm vi (biến).

---