# 🐴 MaCodeThanhCong — Expense Tracker

> *Mở đầu năm Ngọ — Mã đáo thành công!*

## 🐎 Giới thiệu

**Personal Expense Tracker** — Ứng dụng quản lý chi tiêu cá nhân.  
Project thực tế để học **OOP + REST API + SQL** với Java & Spring Boot.

## 🏗️ Tech Stack

| Layer | Công nghệ |
|---|---|
| Language | Java 17 |
| Framework | Spring Boot 3.2 |
| ORM | Spring Data JPA / Hibernate |
| Database | H2 (dev) → MySQL (production) |
| API | RESTful API (JSON) |
| Build | Maven |

## 📂 Cấu trúc Project

```
src/main/java/com/macode/expense/
├── model/          # Entity classes (OOP)
├── repository/     # Database access (SQL)
├── service/        # Business logic
├── controller/     # REST API endpoints
├── dto/            # Data Transfer Objects
├── exception/      # Custom exceptions
└── ExpenseTrackerApplication.java
```

## 🏁 Chạy Project

```bash
# Build
mvn clean install

# Run
mvn spring-boot:run

# Truy cập H2 Console (xem database)
# http://localhost:8080/h2-console
# JDBC URL: jdbc:h2:mem:expensedb
```

## 🗺️ Lộ trình học (5 giai đoạn)

### Phase 1: OOP Foundation — Entity & Encapsulation
- [ ] Tạo `Category.java` — class đơn giản, private fields, getter/setter
- [ ] Tạo `Transaction.java` — abstract class
- [ ] Tạo `Income.java` & `Expense.java` — kế thừa Transaction
- **Học:** Encapsulation, Inheritance, Abstract class

### Phase 2: SQL & Repository — Kết nối Database
- [ ] Tạo `CategoryRepository` — interface extends JpaRepository
- [ ] Tạo `TransactionRepository` — custom query với `@Query`
- [ ] Kiểm tra H2 Console — xem table được tạo tự động
- **Học:** JPA Entity mapping, SQL queries, CRUD operations

### Phase 3: REST API — Controller & Service
- [ ] Tạo `CategoryService` + `CategoryController` — CRUD API
- [ ] Tạo `TransactionService` + `TransactionController` — CRUD API
- [ ] Test API bằng Postman hoặc curl
- **Học:** REST API design, HTTP methods, JSON, Service layer pattern

### Phase 4: OOP nâng cao — Polymorphism & Abstraction
- [ ] Tạo interface `Reportable` — abstraction
- [ ] `ReportService` implements Reportable — polymorphism
- [ ] DTO pattern — tách biệt Entity vs API response
- [ ] Custom Exception + GlobalExceptionHandler
- **Học:** Interface, Polymorphism, DTO pattern, Exception handling

### Phase 5: SQL nâng cao & Hoàn thiện
- [ ] Viết custom queries: tổng chi theo tháng, theo category
- [ ] Chuyển từ H2 sang MySQL
- [ ] Thêm validation cho API input
- [ ] Viết API documentation
- **Học:** Complex SQL, Database migration, Validation

---

*🐎 Mã đáo thành công — Code hay, năm mới phát tài! 🐴*
