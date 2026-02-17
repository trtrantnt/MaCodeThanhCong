# 🐴 PROJECT CONTEXT — MaCodeThanhCong

> File này lưu lại ngữ cảnh dự án để AI có thể tiếp tục hỗ trợ mà không cần bắt đầu lại.
> Khi bắt đầu cuộc hội thoại mới, hãy gửi nội dung file này cho AI.

---

## 📌 Thông tin chung

- **Tên project:** MaCodeThanhCong (Expense Tracker — Quản lý chi tiêu cá nhân)
- **GitHub repo:** https://github.com/trtrantnt/MaCodeThanhCong
- **Tài khoản GitHub:** trtrantnt
- **Ngày bắt đầu:** 2026-02-17
- **Thư mục local:** D:\MaCodeThanhCong

---

## 🎯 Mục tiêu dự án

- Xây dựng ứng dụng **Expense Tracker** thực tế để show cho nhà tuyển dụng (vị trí **Fresher Java**)
- Tập trung học **OOP, REST API, SQL** thông qua việc tự code project
- AI đóng vai trò **mentor/hướng dẫn**, người học tự viết code

---

## 🏗️ Tech Stack

| Layer | Công nghệ |
|---|---|
| Language | **Java 17** (giữ 17, không upgrade 21 — phù hợp fresher) |
| Framework | Spring Boot 3.2 |
| ORM | Spring Data JPA / Hibernate |
| Database | H2 (dev) → MySQL (production sau) |
| API | RESTful API (JSON) |
| Build | Maven |
| Frontend | Chưa làm — dự kiến: HTML/CSS/JS + Fetch API + Chart.js |

---

## 📂 Cấu trúc Project hiện tại

```
MaCodeThanhCong/
├── pom.xml                          ✅ Đã tạo
├── README.md                        ✅ Đã tạo (có lộ trình 5 phase)
├── TODO.md                          ✅ Đã tạo (checklist chi tiết)
├── .gitignore                       ✅ Đã tạo
├── CONTEXT.md                       ✅ File này
└── src/main/
    ├── java/com/macode/expense/
    │   ├── ExpenseTrackerApplication.java  ✅ Entry point
    │   ├── model/           📁 Trống — Phase 1 sẽ code
    │   ├── repository/      📁 Trống — Phase 2 sẽ code
    │   ├── service/         📁 Trống — Phase 3 sẽ code
    │   ├── controller/      📁 Trống — Phase 3 sẽ code
    │   ├── dto/             📁 Trống — Phase 4 sẽ code
    │   └── exception/       📁 Trống — Phase 4 sẽ code
    └── resources/
        └── application.properties   ✅ Config H2 database
```

---

## 🗺️ Lộ trình & Tiến độ

| Phase | Nội dung | Trạng thái |
|---|---|---|
| **Phase 0** | Setup môi trường, Maven, Spring Boot | ✅ HOÀN THÀNH |
| **Phase 1** | OOP Foundation — Entity & Encapsulation | ⬜ CHƯA BẮT ĐẦU |
| **Phase 2** | SQL & Repository — Kết nối Database | ⬜ CHƯA BẮT ĐẦU |
| **Phase 3** | REST API — Controller & Service | ⬜ CHƯA BẮT ĐẦU |
| **Phase 4** | OOP nâng cao — Polymorphism & Abstraction | ⬜ CHƯA BẮT ĐẦU |
| **Phase 5** | SQL nâng cao & Hoàn thiện | ⬜ CHƯA BẮT ĐẦU |

---

## 📋 Việc tiếp theo cần làm

**→ Bắt đầu Phase 1:** Tạo các Entity class trong `model/`
1. `Category.java` — Entity đầu tiên (Encapsulation)
2. `Transaction.java` — Abstract class (Inheritance)
3. `Income.java` — extends Transaction
4. `Expense.java` — extends Transaction

---

## 🔑 Quyết định đã thống nhất

1. **Java 17** — không dùng 21, phù hợp tuyển dụng fresher
2. **Backend trước** — tập trung OOP + API + SQL, frontend làm sau
3. **AI là mentor** — hướng dẫn, giải thích; người học tự viết code
4. **REST API thuần** — không dùng Thymeleaf, frontend tách biệt (HTML/CSS/JS)
5. **H2 trước, MySQL sau** — Phase 5 mới chuyển MySQL
6. Backend REST API này **tương thích mọi frontend** (React, Flutter, Angular...)

---

## 💡 Cách sử dụng file này

Khi bắt đầu cuộc hội thoại mới với AI, gửi nội dung sau:

```
Tôi đang tiếp tục project MaCodeThanhCong. Đây là context:
[dán nội dung file CONTEXT.md]
Tôi muốn tiếp tục Phase [số].
```

---

*Last updated: 2026-02-17*
