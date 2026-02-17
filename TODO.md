# 📋 TODO — Expense Tracker Project

> Checklist chi tiết các việc cần làm. Đánh dấu [x] khi hoàn thành.

---

## 🔧 Phase 0: Chuẩn bị môi trường
- [x] Cài JDK 17
- [x] Setup Maven project (pom.xml)
- [x] Tạo cấu trúc thư mục package
- [x] Cấu hình application.properties (H2 database)
- [x] Tạo ExpenseTrackerApplication.java
- [x] Push lên GitHub
- [ ] Cài Postman (để test API sau này)
- [ ] Cài MySQL (chuẩn bị cho Phase 5)

---

## 🐴 Phase 1: OOP Foundation — Entity & Encapsulation
> **Mục tiêu:** Hiểu Encapsulation, Inheritance, Abstract class

### Lý thuyết cần nắm:
- [ ] Class vs Object là gì?
- [ ] Private fields + Getter/Setter (Encapsulation)
- [ ] Constructor — tại sao cần?
- [ ] `@Entity`, `@Id`, `@GeneratedValue` — JPA annotation
- [ ] Abstract class vs Concrete class
- [ ] Inheritance (`extends`) — kế thừa

### Code cần viết:
- [ ] `Category.java` — Entity đầu tiên
  - Fields: id, name, description, type (INCOME/EXPENSE)
  - Annotations: @Entity, @Id, @GeneratedValue
  - Getter/Setter (hoặc Lombok @Data)
- [ ] `Transaction.java` — Abstract class
  - Fields: id, amount, description, date, category
  - Đánh dấu `abstract` — không thể tạo object trực tiếp
- [ ] `Income.java` — extends Transaction
  - Field riêng: source (nguồn thu nhập)
- [ ] `Expense.java` — extends Transaction
  - Field riêng: paymentMethod (tiền mặt, chuyển khoản...)
- [ ] Chạy app, kiểm tra H2 Console xem table được tạo chưa

---

## 💾 Phase 2: SQL & Repository — Kết nối Database
> **Mục tiêu:** Hiểu JPA Repository, CRUD, SQL queries

### Lý thuyết cần nắm:
- [ ] JpaRepository cung cấp những method gì sẵn?
- [ ] Derived Query Methods (findByName, findByType...)
- [ ] `@Query` annotation — viết SQL / JPQL tùy chỉnh
- [ ] Quan hệ giữa các bảng: `@ManyToOne`, `@OneToMany`

### Code cần viết:
- [ ] `CategoryRepository.java` — interface extends JpaRepository
  - Method: findByType(), findByNameContaining()
- [ ] `TransactionRepository.java` — interface extends JpaRepository
  - Method: findByCategory(), findByDateBetween()
  - Custom @Query: tổng chi tiêu theo tháng
- [ ] Vào H2 Console chạy thử SQL:
  - `SELECT * FROM category;`
  - `SELECT * FROM transaction WHERE amount > 100000;`
  - `SELECT category_id, SUM(amount) FROM expense GROUP BY category_id;`

---

## 🌐 Phase 3: REST API — Controller & Service
> **Mục tiêu:** Hiểu REST API, HTTP methods, Service layer pattern

### Lý thuyết cần nắm:
- [ ] HTTP Methods: GET, POST, PUT, DELETE
- [ ] `@RestController`, `@RequestMapping`
- [ ] `@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`
- [ ] `@PathVariable` vs `@RequestBody` vs `@RequestParam`
- [ ] ResponseEntity — trả response đúng chuẩn
- [ ] Service layer — tại sao không gọi Repository từ Controller?

### Code cần viết:
- [ ] `CategoryService.java`
  - Các method: getAll(), getById(), create(), update(), delete()
- [ ] `CategoryController.java`
  - `GET    /api/categories`        — lấy tất cả
  - `GET    /api/categories/{id}`   — lấy theo id
  - `POST   /api/categories`        — tạo mới
  - `PUT    /api/categories/{id}`   — cập nhật
  - `DELETE /api/categories/{id}`   — xóa
- [ ] `TransactionService.java`
- [ ] `TransactionController.java`
  - `GET    /api/transactions`
  - `GET    /api/transactions/{id}`
  - `POST   /api/transactions`
  - `PUT    /api/transactions/{id}`
  - `DELETE /api/transactions/{id}`
- [ ] Test tất cả API bằng Postman
  - [ ] Test POST — tạo category mới
  - [ ] Test GET — lấy danh sách
  - [ ] Test PUT — cập nhật
  - [ ] Test DELETE — xóa

---

## 🎭 Phase 4: OOP nâng cao — Polymorphism & Abstraction
> **Mục tiêu:** Hiểu Interface, Polymorphism, DTO, Exception handling

### Lý thuyết cần nắm:
- [ ] Interface vs Abstract class — khác gì nhau?
- [ ] Polymorphism — 1 method, nhiều hành vi
- [ ] DTO pattern — tại sao không trả Entity trực tiếp cho client?
- [ ] Custom Exception — tại sao dùng?
- [ ] `@ControllerAdvice` — xử lý exception tập trung

### Code cần viết:
- [ ] `Reportable.java` — Interface
  - Methods: getMonthlySummary(), getByCategory(), getTotal()
- [ ] `ReportService.java` — implements Reportable
  - Tính tổng thu, tổng chi, số dư
  - Thống kê theo tháng, theo danh mục
- [ ] `ReportController.java`
  - `GET /api/reports/summary`
  - `GET /api/reports/monthly?month=2&year=2026`
  - `GET /api/reports/by-category`
- [ ] `TransactionRequest.java` — DTO nhận dữ liệu từ client
- [ ] `TransactionResponse.java` — DTO trả dữ liệu cho client
- [ ] `ResourceNotFoundException.java` — Custom Exception
- [ ] `GlobalExceptionHandler.java` — @ControllerAdvice

---

## 🔥 Phase 5: SQL nâng cao & Hoàn thiện
> **Mục tiêu:** SQL phức tạp, MySQL, Validation, hoàn thiện project

### Lý thuyết cần nắm:
- [ ] JOIN, GROUP BY, HAVING trong SQL
- [ ] Aggregate functions: SUM, COUNT, AVG
- [ ] Native Query vs JPQL
- [ ] Bean Validation: @NotNull, @Min, @Size, @Email
- [ ] MySQL vs H2 — khác biệt gì?

### Code cần viết:
- [ ] Viết custom queries phức tạp:
  - Tổng chi tiêu theo từng tháng trong năm
  - Top 5 danh mục chi tiêu nhiều nhất
  - So sánh thu chi giữa 2 tháng
- [ ] Chuyển từ H2 sang MySQL
  - Cài MySQL, tạo database `expense_tracker`
  - Cập nhật application.properties
  - Chạy và verify dữ liệu
- [ ] Thêm Validation cho API:
  - Amount > 0
  - Description không rỗng
  - Category phải tồn tại
- [ ] Viết data.sql — dữ liệu mẫu

---

## 🎁 Bonus (làm thêm nếu muốn gây ấn tượng)
- [ ] Thêm Pagination cho danh sách giao dịch
- [ ] Thêm Sorting (sắp xếp theo ngày, số tiền)
- [ ] Thêm Filter (lọc theo khoảng thời gian, danh mục)
- [ ] Viết Unit Test với JUnit 5
- [ ] Thêm Swagger/OpenAPI documentation
- [ ] Dockerize ứng dụng
- [ ] Thêm Spring Security (đăng nhập/đăng ký)
- [ ] Thêm Frontend (HTML/CSS/JS)

---

## 📝 Ghi chú cá nhân
> Ghi lại các vấn đề gặp phải, cách giải quyết, kiến thức mới học được...

- 

---

*Last updated: 2026-02-17*
