# 📘 Hướng dẫn Toàn tập: Môi trường Ảo Python (.venv)

# 📘 Comprehensive Guide: Python Virtual Environment (.venv)

**Phiên bản / Version:** 1.0 **Tác giả / Author:** Gemini **Mức độ / Level:** Cơ bản / Basic
-----
## I. Khái niệm / Concept

### 1. `.venv` là gì? What is `.venv`?

**🇻🇳 Tiếng Việt:**
Môi trường ảo (Virtual Environment) là một thư mục khép kín chứa một phiên bản Python riêng biệt và các thư viện độc lập cho một dự án cụ thể. Nó giống như một "hộp cát" (sandbox) giúp cô lập dự án của bạn khỏi hệ thống chính.

**🇺🇸 English:**
A Virtual Environment is a self-contained directory that contains a specific Python installation and independent libraries for a specific project. It acts like a "sandbox," isolating your project from the main system.
### 2. Tại sao cần sử dụng? / Why use it?

**🇻🇳 Tiếng Việt:**
  * **Tránh xung đột:** Dự án A dùng thư viện `X` bản 1.0, Dự án B dùng thư viện `X` bản 2.0. Môi trường ảo giúp 2 dự án chạy song song mà không lỗi.
  * **Giữ sạch hệ thống:** Không cài rác vào Python gốc của máy tính.
  * **Dễ dàng chia sẻ:** Giúp người khác biết chính xác dự án cần thư viện nào để chạy.*
*
**🇺🇸 English:**
**  * **Avoid Conflicts:** Project A needs library `X` v1.0, Project B needs `X` v2.0. Virtual environments allow both to run simultaneously without errors.
  * **Keep System Clean:** Prevents cluttering the global Python installation.
  * **Easy Sharing:** Helps others know exactly which libraries are needed to run the project.
-----

## II. Hướng dẫn từng bước / Step-by-Step Guide

Quy trình chuẩn: **Tạo** $\rightarrow$ **Kích hoạt** $\rightarrow$ **Cài đặt** $\rightarrow$ **Code** $\rightarrow$ **Thoát**.
Standard Workflow: **Create** $\rightarrow$ **Activate** $\rightarrow$ **Install** $\rightarrow$ **Code** $\rightarrow$ **Deactivate**.

### Bước 1: Tạo môi trường / Step 1: Create Environment

Mở Terminal/CMD tại thư mục dự án của bạn và chạy lệnh sau:
Open Terminal/CMD in your project folder and run:

```

bash
# Windows / macOS / Linux

python -m venv .venv

# ⚠️ Note for macOS/Linux users:

# Nếu lệnh 'python' trỏ tới Python 2, hãy dùng / If 'python' points to Python 2, use:

python3 -m venv .venv

```

-----

### Bước 2: Kích hoạt / Step 2: Activate (Quan trọng / Crucial)

Đây là bước khác nhau giữa các hệ điều hành.
This step varies between operating systems.

#### 🪟 Windows

**Option A: Command Prompt (cmd.exe)**

```

cmd
.venv\Scripts\activate

```

**Option B: PowerShell**

```

powershell
.venv\Scripts\activate

```

> **⚠️ Troubleshooting (PowerShell):**
> *VN:* Nếu gặp lỗi báo mật (security error), hãy chạy lệnh dưới đây một lần duy nhất:
> *EN:* If you encounter a security error, run this command once:


> powershell
> Set-ExecutionPolicy Unrestricted -Scope Process


#### 🍎 macOS / 🐧 Linux

**Bash / Zsh (Standard Terminal)**

```

bash
source .venv/bin/activate

```

-----

**✅ Dấu hiệu thành công / Success Indicator:**
Bạn sẽ thấy tên môi trường `(.venv)` xuất hiện ở đầu dòng lệnh.
You will see the environment name `(.venv)` appear at the beginning of the command line.
  * Ví dụ / Example: `(.venv) C:\Users\Dev\Project>`*
-----
### Bước 3: Quản lý thư viện / Step 3: Manage Libraries

Sau khi kích hoạt, mọi lệnh `pip` sẽ chỉ ảnh hưởng đến môi trường này.
Once activated, all `pip` commands affect only this environment.

| Hành động / Action | Lệnh / Command |
| --- | --- |
| **Cài thư viện** / Install library | `pip install [package_name]` <br> (e.g., `pip install requests`)**** |
| Xem danh sách** / List installed** | `pip list` |
| Gỡ cài đặt** / Uninstall** | `pip uninstall [package_name]` |
| Kiểm tra Python** / Check Python path** | `where python` (Windows)<br>`which python` (Mac/Linux) |

-----

### Bước 4: Thoát môi trường / Step 4: Deactivate

Khi bạn làm xong việc và muốn quay lại terminal bình thường.
When you are done and want to return to the normal terminal.

```

bash
deactivate

```

-----

## III. Quy trình làm việc nhóm / Team Workflow (Requirements.txt)

Khi chia sẻ code, KHÔNG** gửi thư mục `.venv`. Hãy gửi file `requirements.txt`.
When sharing code, **DO NOT** send the `.venv` folder. Send a `requirements.txt` file instead.**

**
### 1. Xuất danh sách thư viện (Người gửi)

### 1. Export library list (Sender)

Lưu danh sách các thư viện đang dùng vào file text.
Save the list of current libraries to a text file.

```

bash
# Đảm bảo đang kích hoạt .venv / Ensure .venv is active

pip freeze > requirements.txt

```

### 2. Cài đặt lại (Người nhận)

### 2. Install dependencies (Receiver)

Người nhận tạo `.venv` mới của họ, kích hoạt nó và chạy:
The receiver creates their own `.venv`, activates it, and runs:

```

bash
pip install -r requirements.txt

```

-----

## IV. Cấu hình Công cụ / Tool Configuration

### 1. Git & `.gitignore`

Luôn thêm dòng này vào file `.gitignore` để tránh upload môi trường ảo lên Github (vì nó rất nặng).
Always add this line to your `.gitignore` file to avoid uploading the virtual environment to Github (as it is very heavy).

```

text
.venv/

```

### 2. Visual Studio Code (VS Code)

Để VS Code tự động nhận diện môi trường ảo:
To make VS Code automatically recognize the virtual environment:

1. Mở folder dự án trong VS Code / Open project folder in VS Code.

2. Nhấn / Press: `Ctrl + Shift + P` (Win) or `Cmd + Shift + P` (Mac).

3. ***Gõ và chọn / Type and select: **Python: Select Interpreter**.*
4. Chọn dòng có đường dẫn `./.venv/Scripts/python` (hoặc `bin/python`).
Nó thường có biểu tượng ngôi sao (Recommended) / It usually has a star icon.

1. Khởi động lại Terminal trong VS Code (` Ctrl +  ` \`) / Restart Terminal in VS Code.