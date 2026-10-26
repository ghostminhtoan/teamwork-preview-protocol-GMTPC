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
- [ ] **4-State UI Verification**: Mọi view có data phải có đủ 4 trạng thái: ① Loading (spinner/skeleton) ② Empty ("Không có dữ liệu") ③ Success (hiển thị data) ④ Error (thông báo lỗi + retry action).
- [ ] **Error Feedback**: Khi gặp sự cố mạng hoặc lỗi logic, người dùng có nhận được thông điệp lỗi dễ hiểu thay vì màn hình trắng / crash không?
- [ ] **Responsive & Accessibility**: Giao diện có hoạt động ổn định trên nhiều kích thước màn hình không?

### C. Desktop UI Specific (Avalonia / WPF / Qt / Electron)
- [ ] **Threading Affinity**: Mọi UI update chạy trên UI Thread (Dispatcher)? Background task có dùng `InvokeAsync` / `Post` trước khi chạm control?
- [ ] **Data Binding Contract**: ViewModel property có `RaisePropertyChanged`? Collection dùng `ObservableCollection<T>`? Có `[ObservableProperty]` nếu dùng CommunityToolkit?
- [ ] **XAML Binding Error Zero**: Output window không có Binding Error nào?
- [ ] **DataContext Null Guard**: `DataContext as T` có kiểm tra null trước khi dùng?
- [ ] **Component Style Consistency**: Component mới dùng cùng Style/Theme/Brush hiện có? Đã kiểm tra `App.axaml` / `Styles.axaml` trước khi tạo style mới?
- [ ] **Navigation Flow**: Chuyển màn hình logic? Nút Back/Cancel đúng? Dialog không tạo dead-end?
- [ ] **Keyboard & Focus**: Tab order logic? Phím tắt (Ctrl+S, Enter, Esc) hoạt động? `IsDefault`/`IsCancel` cho dialog?
- [ ] **DPI & Multi-Monitor**: Dùng device-independent units? Không hardcode pixel?
- [ ] **Visual Regression**: Sửa container layout có kiểm tra children component không bị vỡ?
- [ ] **Lifecycle & Dispose**: Timer, event subscription, stream được dispose trong `Unloaded` / `OnClosing`?

---

## 5. 🧪 QA & Verification Auditor Checklist

- [ ] **Static Analysis / Lint**: Lệnh lint hoặc typecheck của dự án có trả về `0 errors, 0 warnings` không?
- [ ] **Unit / Integration Tests**: Các bài test hiện có có pass 100% không? Có cần bổ sung bài test biên cho logic mới không?
- [ ] **Reproducible Build**: Lệnh build (compile/bundle) có chạy thành công mà không có cảnh báo nghiêm trọng không?
- [ ] **Clean Commit**: Thông điệp commit có đúng định dạng (`feat: ...`, `fix: ...`, `refactor: ...`) và tóm tắt đúng bản chất thay đổi không?
