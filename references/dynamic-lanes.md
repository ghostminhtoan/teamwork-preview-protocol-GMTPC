# Dynamic Lane Mapping Guide 🧭

Tài liệu hướng dẫn nhận diện cấu trúc dự án và ánh xạ mã nguồn vào 5 Lane kiến trúc tổng quát cho mọi dạng dự án phần mềm.

---

## 1. Nguyên Tắc Phân Lane Động (Dynamic Lane Principles)

1. **Phân chia theo trách nhiệm (Separation of Concerns)**: Mỗi lane đại diện cho một tầng trách nhiệm rõ ràng trong vòng đời xử lý của phần mềm.
2. **Không phụ thuộc ngược (Dependency Rule)**: Các tầng bên trong (Domain Core) không được phụ thuộc trực tiếp vào tầng bên ngoài (Presentation, Infrastructure).
3. **Phát hiện theo ngữ cảnh**: Không ép buộc cấu trúc thư mục cố định; tự động suy luận vai trò của file dựa trên tên, nội dung và vị trí trong project.

---

## 2. Bảng Ánh Xạ Theo Mô Hình Kiến Trúc Phổ Biến

### A. Mô Hình Web Fullstack / Frontend (React, Vue, Next.js, Svelte, Angular)

| Lane | Trách nhiệm | Các thư mục / Tệp mẫu |
| :--- | :--- | :--- |
| **Lane 1: Presentation** | Components, Layouts, Pages, Hooks giao diện, CSS/Styles | `src/components/`, `app/`, `pages/`, `views/`, `styles/` |
| **Lane 2: Domain Core** | State management, Business services, Custom hooks xử lý | `src/store/`, `src/hooks/use*.ts`, `src/services/` |
| **Lane 3: Infrastructure** | API clients, Local storage helpers, Fetch wrappers, SDKs | `src/api/`, `src/lib/http.ts`, `src/adapters/` |
| **Lane 4: Types & Contracts** | TypeScript interfaces, Zod schemas, DTOs | `src/types/`, `src/schemas/`, `src/models/` |
| **Lane 5: Build & Ops** | Configs đóng gói, linter, tests | `tsconfig.json`, `vite.config.ts`, `tests/` |

---

### B. Mô Hình Backend API & Microservices (Node/Express/Nest, Go, Python/FastAPI, Spring, .NET)

| Lane | Trách nhiệm | Các thư mục / Tệp mẫu |
| :--- | :--- | :--- |
| **Lane 1: Presentation** | HTTP Controllers, Handlers, Middleware, Routers, CLI commands | `controllers/`, `handlers/`, `routes/`, `middleware/` |
| **Lane 2: Domain Core** | UseCases, Domain Entities, Business Services, Business Rules | `usecases/`, `services/`, `domain/`, `core/` |
| **Lane 3: Infrastructure** | Database Repositories, ORM entities, Caching, Message Queues | `repositories/`, `models/`, `db/`, `queue/`, `redis/` |
| **Lane 4: Types & Contracts** | DTOs, Protobuf, Serialization schemas, Migrations | `dto/`, `proto/`, `schemas/`, `migrations/` |
| **Lane 5: Build & Ops** | Dockerfile, CI workflow, Tests, Env configs | `Dockerfile`, `docker-compose.yml`, `tests/` |

---

### C. Mô Hình CLI Tools & Desktop App (Rust, C++, Go, Python, WPF/Avalonia, Electron)

| Lane | Trách nhiệm | Các thư mục / Tệp mẫu |
| :--- | :--- | :--- |
| **Lane 1: Presentation** | CLI Args Parser, Interactive UI, Desktop Windows, XAML | `cli/`, `ui/`, `windows/`, `MainWindow.xaml`, `tui/` |
| **Lane 2: Domain Core** | Execution Engine, File Pipeline, Conversion Logic, Task Queue | `engine/`, `pipeline/`, `tasks/`, `core/` |
| **Lane 3: Infrastructure** | OS Process spawner, File system IO, Network Downloader, SQLite | `storage/`, `http/`, `process/`, `db/` |
| **Lane 4: Types & Contracts** | Structs, Enums, Settings configuration schema | `types/`, `config/`, `models/` |
| **Lane 5: Build & Ops** | Build scripts, Release workflows, Unit tests | `build.sh`, `Makefile`, `tests/` |

---

## 3. Quy Trình Phân Tuyến Nhanh Khi Tiếp Nhận Yêu Cầu (Fast Routing)

Khi nhận một tác vụ từ người dùng:
1. **Quét Root Directory**: Xem các tệp config gốc (`package.json`, `Cargo.toml`, `go.mod`, `pom.xml`, `requirements.txt`, `*.csproj`) để xác định ngôn ngữ & framework.
2. **Xác định Lane bị ảnh hưởng**:
   - Nếu sửa giao diện hoặc API format ➔ Tập trung **Lane 1** & **Lane 4**.
   - Nếu sửa thuật toán hoặc logic tính toán ➔ Tập trung **Lane 2**.
   - Nếu sửa truy vấn DB hoặc kết nối mạng ➔ Tập trung **Lane 3**.
   - Nếu sửa config hoặc build ➔ Tập trung **Lane 5**.
3. **Kiểm tra Ranh giới Tác động (Blast Radius)**:
   - Thay đổi ở **Lane 4 (Types/Contracts)** có nguy cơ gây ảnh hưởng dây chuyền lớn nhất; cần kiểm tra tất cả các Lane đang tham chiếu type đó.
