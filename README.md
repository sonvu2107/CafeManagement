# CafeManagement

Phần mềm quản lý quán cafe viết bằng Java Core + Swing. Tài liệu này hướng dẫn cách làm việc nhóm với GitHub và giải thích cấu trúc dự án.

---

## 1. Mục tiêu dự án

Xây dựng phần mềm quản lý quán cafe gồm các chức năng:

* Quản lý sản phẩm
* Quản lý nhân viên
* Bán hàng và tạo hóa đơn
* Quản lý khách hàng
* Thống kê doanh thu

---

## 2. Công nghệ sử dụng

* Java Core
* Java Swing
* JDBC
* MySQL (hoặc SQL Server tùy chọn)

---

## 3. Cấu trúc thư mục

Thư mục dự án được tổ chức theo mô hình 3 tầng: Model – DAO – Service – UI.

```
src/
 ├── model/        Chứa các class dữ liệu (SanPham, NhanVien, HoaDon...)
 ├── dao/          Chứa lớp làm việc với database (SQL)
 ├── service/      Chứa xử lý nghiệp vụ (thêm, sửa, xóa, bán hàng...)
 ├── ui/           Chứa giao diện Swing (Form + Event)
 └── main/         Chứa file chạy chính Main.java
```

Nguyên tắc:

* UI không chứa SQL.
* DAO không xử lý logic (chỉ query).
* Service là nơi xử lý nghiệp vụ.

---

## 4. Quy tắc làm việc nhóm trên Git

### 4.1 Không push trực tiếp lên nhánh main

Tất cả phải làm trên nhánh riêng để tránh xung đột code.

### 4.2 Tạo branch cá nhân

Mỗi thành viên tự tạo branch theo tên:

```bash
git checkout -b ten-cua-ban
```

Ví dụ:

```bash
git checkout -b son
```

### 4.3 Cập nhật code mới nhất trước khi làm

Luôn kéo code từ main về trước để tránh conflict:

```bash
git pull origin main
```

### 4.4 Quy trình làm việc chuẩn

Thực hiện theo thứ tự:

1. Tạo branch mới nếu chưa có
2. Code trên branch của bạn
3. Add file
4. Commit
5. Push branch lên GitHub
6. Tạo Pull Request để xin merge vào main

Lệnh mẫu:

```bash
git add .
git commit -m "Mo ta ro rang chuc nang da lam"
git push origin ten-cua-ban
```

### 4.5 Cách tạo Pull Request

1. Lên GitHub repo
2. Chọn "Compare & Pull Request"
3. Viết mô tả
4. Đợi review và merge

---

## 5. Quy tắc commit

Commit phải rõ ràng, mô tả chính xác phần đã làm.

Mẫu commit chuẩn:

```
[FEATURE] - Thêm form quản lý sản phẩm
[FIX] - Sửa lỗi tính tổng tiền hóa đơn
[UPDATE] - Điều chỉnh giao diện bán hàng
[REFACTOR] - Tối ưu service sản phẩm
```

Không commit file rác như:

* `.class`
* `/out/`
* `.idea/`
* `*.iml`

---

## 6. File .gitignore

Dùng để bỏ qua các file không cần đẩy lên Git.

```
*.class
/out/
/build/
/target/
.idea/
*.iml
```

---

## 7. Hướng dẫn setup dự án sau khi clone

Sau khi clone repo:

```bash
git clone https://github.com/sonvu2107/CafeManagement.git
```

Mở project bằng IntelliJ, Eclipse hoặc NetBeans:

1. Đánh dấu thư mục `src` là Source Root (nếu cần)
2. Cấu hình kết nối CSDL
3. Chạy file `Main.java`

---

## 8. Quy tắc code chung

* Đặt tên biến, hàm rõ ràng.
* Mỗi class chỉ chịu trách nhiệm 1 việc.
* Không nhét logic vào UI.
* Không nhét SQL vào Service hoặc UI.
* Mỗi commit giải quyết 1 phần rõ ràng.

---

## 9. Checklist trước khi push code

* Không lỗi compile
* Không thay đổi file không liên quan
* Code đã pull main về và resolve conflict
* Ko push file tạm thời (.class, .log, out/)

---

## 10. Góp ý hoặc đề xuất

Nếu có thay đổi lớn (cấu trúc project, DB…), tạo issue hoặc trao đổi trong nhóm trước khi thực hiện.

