# Virtual Review Crew Checklists 🛡️

Bộ tiêu chí chi tiết cho từng vai trò trong **Hội đồng Review Ảo** nhằm đảm bảo mã nguồn đạt chất lượng sản xuất (production-ready).

---

## 1. 🔍 Architect & Lane Scout Checklist

- [ ] **Single Source of Truth (SSOT)**: Logic này đã tồn tại ở nơi khác trong dự án chưa? Đã tái sử dụng tối đa hàm/module hiện có chưa?
- [ ] **Boundary Check**: Thay đổi có vi phạm ranh giới giữa các module/layer không (ví dụ: Domain Core có đang import nhầm UI component hay Database driver không)?
- [ ] **Minimal Blast Radius**: Số lượng file cần sửa có được thu nhỏ tối đa không? (Mục tiêu: ≤ 2-3 files cho tác vụ thông thường).
- [ ] **Coupling & Cohesion**: Module mới thêm vào có tính kết dính cao và ghép nối lỏng lẻo (high cohesion, loose coupling) không?

---

## 2. 🛠️ Lead Builder / Implementer Checklist

- [ ] **YAGNI & Simplicity**: Có thêm tham số thừa, generic không cần thiết, hoặc lớp trừu tượng sớm không?
- [ ] **Idiomatic Code**: Code có viết đúng phong cách chuẩn của ngôn ngữ (Python PEP8, Go idiomatic error handling, Rust borrow checker patterns, Modern TypeScript) không?
- [ ] **Standard Library First**: Có cài thêm thư viện ngoài cho việc mà Standard Library đã giải quyết tốt không?
- [ ] **Clean Diff**: Diff có chứa khoảng trắng thừa, format file không cần thiết làm nhiễu lịch sử git không?

---

## 3. 🛡️ Security & Edge-Case Guard Checklist

### A. An Toàn Dữ Liệu & Bộ Nhớ
- [ ] **Null / Undefined Safety**: Mọi truy cập thuộc tính sâu đã có optional chaining / null check chưa?
- [ ] **Resource Cleanup**: Stream, socket, database connection, file handle đã được đóng qua `defer`, `using`, `try-finally` hoặc RAII chưa?
- [ ] **Memory Leaks**: Có event listener, observer hoặc interval nào chưa được `cleanup` / `unsubscribe` không?

### B. Bất Đồng Bộ & Concurrency
- [ ] **Race Conditions**: Có 2 luồng/hàm async nào ghi đè dữ liệu lên cùng 1 biến trạng thái mà không có lock/mutex không?
- [ ] **Deadlocks / Unhandled Rejections**: Mọi Promise/Async đều có error handling hoặc `catch` chưa?
- [ ] **Cancellation**: Các tác vụ tốn thời gian dài có hỗ trợ `AbortSignal` hoặc `CancellationToken` khi người dùng hủy bỏ không?

### C. Bảo Mật (Security)
- [ ] **Input Sanitization**: Dữ liệu người dùng nhập có được validate trước khi đưa vào SQL query, HTML template, hoặc Command execution không?
- [ ] **Secrets & Tokens**: Không hardcode password, API key, token bí mật trong mã nguồn.

---

## 4. 🎨 Contract, Type & UX Reviewer Checklist

### A. Types & API Contracts
- [ ] **Type Soundness**: Tránh dùng `any`, `interface{}` hay kiểu lỏng lẻo; định nghĩa rõ ràng kiểu trả về.
- [ ] **Backward Compatibility**: Thay đổi có làm hỏng các client hoặc component cũ đang gọi không?
- [ ] **Serialization / Schema**: JSON field names, camelCase / snake_case có nhất quán giữa frontend và backend không?

### B. User Experience & Giao Diện
- [ ] **Loading & Empty States**: Khi dữ liệu đang tải hoặc danh sách rỗng, UI có hiển thị thông báo rõ ràng không?
- [ ] **Error Feedback**: Khi gặp sự cố mạng hoặc lỗi logic, người dùng có nhận được thông điệp lỗi dễ hiểu thay vì màn hình trắng / crash không?
- [ ] **Responsive & Accessibility**: Giao diện có hoạt động ổn định trên nhiều kích thước màn hình không?

---

## 5. 🧪 QA & Verification Auditor Checklist

- [ ] **Static Analysis / Lint**: Lệnh lint hoặc typecheck của dự án có trả về `0 errors, 0 warnings` không?
- [ ] **Unit / Integration Tests**: Các bài test hiện có có pass 100% không? Có cần bổ sung bài test biên cho logic mới không?
- [ ] **Reproducible Build**: Lệnh build (compile/bundle) có chạy thành công mà không có cảnh báo nghiêm trọng không?
- [ ] **Clean Commit**: Thông điệp commit có đúng định dạng (`feat: ...`, `fix: ...`, `refactor: ...`) và tóm tắt đúng bản chất thay đổi không?
