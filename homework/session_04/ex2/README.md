# Session 04 - Exercise 2

## 1. Mục tiêu

Thực hành quản lý branch, tạo Merge Conflict và xử lý xung đột thủ công trong Git.

## 2. Các bước thực hiện

### Bước 1: Tạo commit ban đầu trên main

Tạo file `README.md` và commit phiên bản ban đầu trên branch `main`.

```bash
git add homework/session_04/ex2/README.md
git commit -m "docs: add initial README"
```

### Bước 2: Tạo branch feature-update

```bash
git checkout -b feature-update
```

Thay đổi nội dung `README.md` trên branch `feature-update` và commit:

```bash
git add homework/session_04/ex2/README.md
git commit -m "docs: update README on feature branch"
```

### Bước 3: Cập nhật main

Chuyển về `main`:

```bash
git checkout main
```

Thay đổi cùng một dòng trong `README.md` và commit:

```bash
git add homework/session_04/ex2/README.md
git commit -m "docs: update README on main branch"
```

### Bước 4: Merge feature-update

Thực hiện:

```bash
git merge feature-update
```

Git phát sinh Merge Conflict do hai branch cùng thay đổi một dòng trong `README.md`.

### Bước 5: Giải quyết conflict thủ công

Mở file `README.md` và tìm các ký hiệu:

```text
<<<<<<< HEAD
=======
>>>>>>> feature-update
```

Sau đó lựa chọn và kết hợp nội dung phù hợp, đồng thời xóa toàn bộ các ký hiệu đánh dấu conflict.

### Bước 6: Hoàn tất merge

Sau khi xử lý conflict:

```bash
git add homework/session_04/ex2/README.md
git commit -m "merge: resolve conflict between main and feature-update"
```

### Bước 7: Kiểm tra lịch sử commit

Sử dụng:

```bash
git log --graph --oneline --all
```

Kết quả hiển thị branch `feature-update` được tách ra từ `main` và sau đó được merge trở lại bằng một merge commit có hai nhánh tổ tiên.

## 3. Kết quả

Merge Conflict trong file `README.md` đã được xử lý thủ công thành công.

File `README.md` không còn các ký hiệu:

```text
<<<<<<<
=======
>>>>>>>
```

Lịch sử Git hiển thị rõ quá trình tạo branch, phát triển tính năng, cập nhật `main` và merge hai nhánh.
