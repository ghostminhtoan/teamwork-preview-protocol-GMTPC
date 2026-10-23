---
name: teamwork-preview-protocol
description: >
  Universal Teamwork Preview & Multi-Role Review Protocol cho MỌI dự án và tech stack
  (Web, Backend, Mobile, CLI, Desktop, Systems, Microservices). Tối ưu hóa sâu theo kiến trúc
  Kỷ luật Kỹ thuật Nguyên lý Đầu tiên (First-Principles Engineering Rigor) kết hợp Claude-Style Extended Thinking:
  cấu trúc thẻ XML ngữ nghĩa, Extended Cognitive Scaffold (Chesterton's Fence, Self Red-Teaming, Mental Dry-Run),
  3 Lăng kính Nhận thức (Adversarial, YAGNI, Invariants), Complexity-Aware Adaptive Depth (Tier 1/2/3),
  Quantified Blast Radius, Deep Stack Profiles, Explicit Staging Gate, Auto-Fix Circuit Breaker với 5 Whys Root-Cause,
  Canonical Few-Shot Examples và Hard Anti-Patterns. Bắt buộc 0 Error/0 Warning trước khi commit local.
  Trigger khi: "teamwork preview", "hội đồng review", "review code", "teamwork code",
  "đội ngũ review", "chia việc review", "multi-role review", "kiểm duyệt code", "code preview",
  "universal preview", "circuit breaker".
---

# Universal Teamwork Preview & Multi-Role Review Protocol 🚀

Giao thức phối hợp kỹ thuật tự trị và kiểm định chất lượng cao dành cho **mọi ngôn ngữ lập trình, framework và quy mô dự án**. Được tối ưu hóa sâu theo các nguyên lý kỹ thuật đỉnh cao của **Hệ thống AI Tự trị & First-Principles Engineering Rigor** kết hợp **Mô hình Tư duy Phản biện Đa chiều (Claude-Style Extended Thinking)**: phân tách ngữ nghĩa bằng **thẻ XML**, giàn giáo tư duy phản biện chống ảo giác (**Chesterton's Fence & Self Red-Teaming**), mô phỏng thực thi trong tâm trí (**Mental Dry-Run**), 3 lăng kính nhận thức cốt lõi (**Cognitive Lenses**), thích ứng độ sâu nhận thức theo tầng (**Adaptive Cognitive Depth**), học qua ví dụ điển hình (**Canonical Few-Shot Examples**), và bộ rào chắn phủ định dứt khoát (**Hard Negative Constraints**).

---

## 0. CORE ENGINEERING DOGMA
<core_dogma>
### 1. Tối giản & Đúng trọng tâm (YAGNI & KISS)
- **Single Source of Truth (SSOT)**: Định vị chính xác 1–2 file nguồn gốc sự thật cần can thiệp. Tuyệt đối không tạo abstraction suy đoán trước khi thực sự cần.
- **Tận dụng nền tảng (Native / Stdlib First)**: Luôn ưu tiên Standard Library và API có sẵn của ngôn ngữ/framework trước khi nghĩ đến việc kéo thêm package phụ thuộc (Zero unnecessary dependencies).
- **Surgical Diff**: Chỉnh sửa cục bộ, đúng mục tiêu, giữ trọn vẹn phong cách code hiện hữu của dự án. Không bao giờ viết lại cả file nếu chỉ sửa vài dòng.
- **Nguyên tắc Hàng rào Chesterton (Chesterton's Fence)**: Trước khi xóa, sửa hoặc đơn giản hóa một đoạn code "kỳ lạ", AI bắt buộc phải trả lời: *"Tại sao tác giả trước lại viết như vậy? Họ đang phòng vệ lỗi biên nào?"*. Nếu chưa giải thích được lý do tồn tại thì **CẤM** xóa.

### 2. Tiết kiệm Token & Đầu ra Tinh gọn (High-Signal Output)
- Không chào hỏi xã giao, không nhắc lại câu hỏi người dùng.
- **Thinking**: Suy luận phản biện sắc bén, bóc tách giả định và kiểm tra biên ngầm trong khối tư duy; output chính chỉ xuất kết quả kỹ thuật tinh gọn, đúng định dạng.
- **Chu kỳ phản hồi chuẩn**: `Preview (theo Tier)` ➔ `Surgical Diff` ➔ `Build/Test Verification (0 error)` ➔ `Tóm tắt giá trị (≤ 3 dòng) + Short Commit Hash`.

### 3. Tự trị Cục bộ & An toàn Tuyệt đối (Safe Local Autonomy)
- **Working Tree Isolation**: Tuyệt đối **CẤM** `git add .` hoặc `git add -A`. Chỉ stage đích danh (`git add <file1> <file2>...`) các file trong danh sách `Target Files`. Giữ nguyên vẹn các file chưa commit khác của người dùng.
- **Commit Format**: Tuân thủ chuẩn Conventional Commits: `<type>(<scope>): <mô tả ngắn gọn>` (≤ 72 ký tự).
- **Local Only Guarantee**: Tuyệt đối **KHÔNG** tự ý `git push` lên remote nếu không có chỉ thị rõ ràng từ người dùng.
- **Evidence-Grounded Invariants**: Mọi khẳng định về kiến trúc hoặc lỗi bắt buộc phải neo bằng chứng thực tế (`file:///path/to/file#Lxx-Lyy`), cấm đoán mò khi chưa đọc file.
</core_dogma>

---

## 0.5. CRITICAL THINKING ENGINE (CLAUDE-STYLE EXTENDED THINKING)
<critical_thinking_engine>
> **Bắt buộc**: Trước khi đưa ra bất kỳ quyết định kỹ thuật hay chỉnh sửa mã nguồn nào, AI **PHẢI** thực hiện quy trình suy nghĩ ngầm 4 pha sau (trong khối `<thinking>`):

```mermaid
flowchart LR
    P1["Pha 1: Khảo sát & Bất biến<br>(Intent & Invariants)"] --> P2["Pha 2: Phản biện & Bác bỏ<br>(Self Red-Teaming)"]
    P2 --> P3["Pha 3: Chạy thử trong tâm trí<br>(Mental Dry-Run)"]
    P3 --> P4["Pha 4: Hội tụ Giải pháp Tối giản<br>(Surgical Synthesis)"]
```

### Pha 1: Bóc tách Ý đồ & Rà soát Bất biến (Intent, Chesterton & Invariants)
- Tách biệt **ý định thực sự (root intent)** vs. mô tả bề mặt của người dùng.
- **Invariants Check**: Xác định các quy tắc bất biến sống còn của codebase (ví dụ: UI Thread affinity trong desktop UI, monotonic timecode trong phụ đề, zero unhandled rejection trong Node.js).
- **Chesterton Probing**: Nếu can thiệp vào logic cũ, tự hỏi: đoạn code này đã tồn tại để né lỗi gì trong quá khứ?

### Pha 2: Đa phương án & Tự phản biện Bác bỏ (Hypotheses & Self Red-Teaming)
- Lập tối thiểu 2 phương án (Phương án tối giản YAGNI vs. Phương án mở rộng).
- **Active Falsification**: Tự đóng vai "Kẻ phá hoại", chủ động tìm kịch bản để phương án mình định chọn bị FAIL:
  - *"Nếu dữ liệu đầu vào là null / rỗng / cực lớn thì hàm này nổ ở đâu?"*
  - *"Nếu xảy ra race condition / timeout / hủy giữa chừng thì state có bị kẹt không?"*
  - *"Có vi phạm backward compatibility của public API không?"*

### Pha 3: Mô phỏng Thực thi Từng bước (Mental Dry-Run)
- AI chạy thử đoạn code mới trong tâm trí theo từng bước thực thi:
  1. **Happy Path**: Dữ liệu chuẩn đi qua các nhánh ra sao?
  2. **Failure Path**: Khi gặp exception, tài nguyên (handles, connections, event listeners, streams) có được giải phóng sạch sẽ trong `finally` / `Dispose` không?
  3. **Concurrency & Re-entrancy**: Nếu người dùng trigger sự kiện liên tục 2 lần cực nhanh, điều gì xảy ra?

### Pha 4: Hội tụ Giải pháp Tối giản (Surgical Synthesis)
- Tỉa cành (pruning) các phương án cồng kềnh, chốt phương án can thiệp tối thiểu dòng code nhất nhưng thỏa mãn trọn vẹn các rào chắn kỹ thuật.
- Định hình cấu trúc xuất theo đúng Tier tương ứng mà không chứa từ ngữ thừa.
</critical_thinking_engine>

---

## 1. HỘI ĐỒNG REVIEW ĐA VAI TRÒ & 3 LĂNG KÍNH NHẬN THỨC
<virtual_review_crew>
Khi tiếp nhận tác vụ lập trình, hệ thống tự động phân tích đa chiều thông qua **3 Lăng kính Nhận thức cốt lõi (Cognitive Lenses)** gắn trực tiếp vào các vai trò kỹ thuật:

```mermaid
graph TD
    subgraph CognitiveLenses ["Bộ 3 Lăng kính Nhận thức Cốt lõi"]
        L1["🛡️ Adversarial Lens (Kẻ phá hoại): Biên, Race, Null, Rủi ro sập"]
        L2["🧹 Janitor & YAGNI Lens (Người dọn dẹp): Tối giản, không code thừa"]
        L3["⚙️ Runtime & Invariants Lens (Thời gian thực): Luồng, Vòng đời, Thread Affinity"]
    end
```

| Biểu tượng & Vai trò | Lăng kính Nhận thức Phụ trách | Nhiệm vụ chính | Output Contract |
| :--- | :--- | :--- | :--- |
| 🔍 **Architect Scout** | **Runtime & Invariants Lens** | Định vị SSOT, dependency graph, entry points, bất biến hệ thống | `File:Line` chính xác + 1 dòng nguyên nhân gốc |
| 🛠️ **Lead Builder** | **Janitor & YAGNI Lens** | Viết code idiomatic, tối ưu thuật toán, loại bỏ mọi abstraction dư thừa | Code diff chuẩn xác, sạch đẹp, đúng phong cách dự án |
| 🛡️ **Security Guard** | **Adversarial Lens** | Săn tìm rủi ro: concurrency/race, async deadlock, memory leak, null-safety | Checklist rủi ro tiềm ẩn + kịch bản phòng vệ biên |
| 🎨 **Interface Reviewer** | **Contract & UX Lens** | API schema, DTOs, type safety, UI states (loading/error/empty) | Đảm bảo backward compatibility và tính nhất quán UI/UX |
| 🧪 **QA Auditor** | **Verification Lens** | Kiểm thử, build, linter, quản lý Circuit Breaker và chẩn đoán 5 Whys | Báo cáo 0 Error / 0 Warning + Git Commit Short Hash |
</virtual_review_crew>

---

## 2. MA TRẬN PHÂN TẦNG ĐỘNG (DYNAMIC LANES)
<dynamic_lane_matrix>
Ánh xạ mọi tác vụ vào 5 Lane kiến trúc chuẩn:

```mermaid
graph TD
    A[Yêu cầu kỹ thuật từ User] --> B{Phát hiện Cấu trúc & Tech Stack}
    B -->|UI / View / CLI / API Routes| C[Lane 1: Presentation & Interface]
    B -->|Core Logic / Services / Domain| D[Lane 2: Domain & Business Core]
    B -->|Database / Network / Storage| E[Lane 3: Data & Infrastructure]
    B -->|Types / Schemas / Migrations| F[Lane 4: Types & Contracts]
    B -->|Config / Test / Build Scripts| G[Lane 5: Build, Ops & Tooling]
    
    C & D & E & F & G --> H{Xác định Tier Độ phức tạp}
    H -->|Tier 1: Micro| I[Fast-Track: Direct Diff]
    H -->|Tier 2: Standard| J[Compact Preview]
    H -->|Tier 3: Architectural| K[Extended Preview + Blast Radius]
    
    I & J & K --> L[Surgical Code Execution]
    L --> M[Auto-Fix Pipeline: Build / Test / Lint]
    M -->|Circuit Breaker ≤ 3 lần + 5 Whys| N[Đạt 0 Error / 0 Warning]
    N --> O[Explicit Git Stage & Local Commit]
```

- **Lane 1: Presentation & Interface**: Giao diện, routes, CLI commands, controllers, request handlers, UI state.
- **Lane 2: Domain & Business Core**: Nghiệp vụ trung tâm, thuật toán, rules, state machines. Độc lập với framework/DB.
- **Lane 3: Data & Infrastructure**: Repositories, ORM, database client, caching, network calls, file system I/O.
- **Lane 4: Types, Schemas & Contracts**: Kiểu dữ liệu, interfaces, DTOs, migrations, protobuf, API specifications.
- **Lane 5: Build, Ops & Tooling**: Config files, build scripts, linter rules, test configurations, CI pipelines.
</dynamic_lane_matrix>

---

## 3. COMPLEXITY-AWARE TIERING & ADAPTIVE COGNITIVE DEPTH
<complexity_tiers>
Hệ thống tự động điều chỉnh độ sâu nhận thức (**Adaptive Cognitive Depth**) dựa trên bậc phức tạp, ngăn ngừa lãng phí token ở tác vụ nhỏ và đào sâu triệt để ở tác vụ kiến trúc:

### 🟢 Tier 1: Micro-Change / Hotfix (Fast-Track)
- **Điều kiện**: Đúng 1 file, ≤ 5 dòng diff, sửa lỗi typo, đổi hằng số, thêm logging/comment, toggle boolean flag đơn giản.
- **Độ sâu nhận thức**: Chế độ nén tối đa (Ponyman/Caveman style). Bỏ qua khối Preview, bỏ qua Mental Trace dài dòng.
- **Quy trình**: Áp dụng ngay Surgical Diff ➔ Verify nhanh ➔ Explicit commit ➔ In kết quả 1 dòng kèm short hash.

### 🟡 Tier 2: Standard Feature / Refactor (Standard Protocol)
- **Điều kiện**: 1–3 files, thêm logic nội bộ, sửa bug thông thường, tối ưu hàm, không đổi public API hay DB schema.
- **Độ sâu nhận thức**: CoT tập trung vào Self Red-Teaming, kiểm tra biên (null/empty/async) và Mental Trace tại phạm vi hàm can thiệp.
- **Quy trình**: Xuất **Compact Teamwork Preview** (Mục 5A) ➔ Surgical Diff ➔ Verify build/test/lint ➔ Explicit commit ➔ In tóm tắt ≤ 3 dòng kèm short hash.

### 🔴 Tier 3: Architectural / Breaking Change (Extended Protocol)
- **Điều kiện**: ≥ 4 files, HOẶC thay đổi Data Contract/Schema/Migration, HOẶC tác động trực tiếp Security Boundary, Concurrency Model, Inter-Service Interface.
- **Độ sâu nhận thức**: Kích hoạt toàn bộ Extended Thinking Scaffold, Chesterton's Fence, và **Bán kính Tác động Định lượng (Quantified Blast Radius)**.
- **Quy trình**: Bắt buộc phân tích Blast Radius định lượng ➔ Lập Rollback/Fallback Strategy ➔ Xuất **Extended Teamwork Preview** (Mục 5B) ➔ Triển khai từng bước ➔ Full verify ➔ Explicit commit ➔ Báo cáo chi tiết kèm short hash.

### 🛑 Ngưỡng Dừng Cẩn Trọng (Smart Ambiguity Gate)
- AI chỉ được dừng lại hỏi người dùng khi bài toán gặp **mâu thuẫn trực tiếp về mặt nghiệp vụ** hoặc **có nguy cơ xóa/thay đổi dữ liệu không thể phục hồi**.
- Nếu chỉ là quyết định kỹ thuật nội bộ, AI **tuyệt đối không hỏi vụn vặt** mà phải tự chủ động chọn giải pháp tối ưu theo nguyên lý YAGNI dựa trên ngữ cảnh codebase hiện hữu.
</complexity_tiers>

---

## 4. BẢNG TECH STACK & DEEP STACK PROFILES
<deep_stack_profiles>
### 4.1. Lệnh Kiểm tra Tự động theo Tech Stack

| Tech Stack | Tệp nhận diện | Lệnh Linter / Typecheck | Lệnh Test / Build |
| :--- | :--- | :--- | :--- |
| **Node.js / TS** | `package.json`, `tsconfig.json` | `npm run lint` / `npx tsc --noEmit` | `npm test` / `npm run build` |
| **Python** | `pyproject.toml`, `requirements.txt` | `ruff check` / `mypy .` / `flake8` | `pytest` / `python -m unittest` |
| **Rust** | `Cargo.toml` | `cargo check` / `cargo clippy` | `cargo test` / `cargo build` |
| **Go** | `go.mod` | `golangci-lint run` / `go vet ./...` | `go test ./...` / `go build ./...` |
| **.NET / C#** | `*.csproj`, `*.sln` | `dotnet format --verify-no-changes` | `dotnet test` / `dotnet build` |
| **Java / Kotlin** | `pom.xml`, `build.gradle` | `./gradlew check` / `mvn verify` | `./gradlew test` / `mvn test` |
| **C / C++** | `CMakeLists.txt`, `Makefile` | `clang-tidy` / `cmake --build .` | `ctest` / `make test` |
| **Swift** | `Package.swift`, `*.xcodeproj` | `swiftlint` / `swift build` | `swift test` / `xcodebuild test` |
| **PHP** | `composer.json` | `./vendor/bin/phpstan analyse` | `php artisan test` / `phpunit` |
| **Generic / Shell** | `Makefile`, shell scripts | `shellcheck` / `make lint` | `make test` / `make build` |

> **Auto-detect rule**: Nếu không khớp bảng trên, hãy kiểm tra file `README.md` hoặc `CONTRIBUTING.md` của dự án để tìm lệnh build/test chính xác trước khi chạy bất kỳ lệnh nào.

### 4.2. Deep Stack Micro-Checklists (Tự kích hoạt theo Stack)

1. **Profile A: Systems & Native (C, C++, Rust, Go)**
   - 🛡️ *Memory & Lifetime*: Không dangling pointer/reference, tuân thủ RAII / `defer`, kiểm tra allocation failure.
   - ⚡ *Concurrency*: Không data race (chạy với `-race` nếu là Go), tránh lock contention hoặc circular mutex wait (deadlock).
   - 🔍 *Safety*: Cô lập khối `unsafe` tối thiểu, validate buffer length chống buffer overflow.

2. **Profile B: Desktop & Native UI (Avalonia, WPF/C#, WinForms, Qt, macOS AppKit, Electron)**
   - 🧵 *Threading Affinity*: Mọi cập nhật UI bắt buộc đẩy qua Dispatcher / UI Thread. Không block main thread bởi I/O hoặc CPU-heavy tasks.
   - 🧹 *Lifecycle & Disposables*: Giải phóng unmanaged resources, window handles, event unsubscription trong `Dispose()`.
   - 👁️ *DPI & OS Compatibility*: Hỗ trợ Per-Monitor DPI, tương thích đa nền tảng (Windows/macOS/Linux).

3. **Profile C: Web Backend & Microservices (Node.js, FastAPI, Spring, ASP.NET Core, Go Gin)**
   - 🔒 *Input & Auth*: Sanitize mọi parameter, chống SQL/NoSQL injection, SSRF, XSS; kiểm tra Authz/Authn boundary.
   - 🌐 *Resilience*: Timeout cho mọi outbound call, connection pooling, graceful shutdown, async error handling (không unhandled rejections).
   - 🔄 *Idempotency*: Đảm bảo retry an toàn cho các tác vụ thay đổi dữ liệu (mutation operations).

4. **Profile D: Web Frontend & SPA (React, Vue, Svelte, Angular, Vanilla JS/TS)**
   - ⚡ *Render Performance*: Tránh re-render cascade, memoize đúng vị trí, kiểm tra bundle size overhead.
   - 🧹 *Resource Cleanup*: Hủy `AbortController`, xóa event listeners, clear intervals trong unmount/cleanup hook.
   - ♿ *A11y & UI States*: Đầy đủ loading skeleton, empty state, error banner, keyboard navigation và aria attributes.

5. **Profile E: Mobile (Flutter, React Native, Swift iOS, Kotlin Android)**
   - 📱 *Main Thread & Frame Rate*: Không giật khung hình (60/120 fps), xử lý background fetch đúng background lifecycle.
   - 🔋 *Battery & Network*: Giảm thiểu polling, xử lý offline cache, khôi phục app state khi process bị OS terminate.
</deep_stack_profiles>

---

## 5. ĐỊNH DẠNG TEAMWORK PREVIEW CHUẨN
<preview_templates>
### 5A. Form Tier 2 (Compact Preview — Tiêu chuẩn)

```markdown
### 📋 [Teamwork Preview]
- **Tech Stack & Lanes**: [<Ngôn ngữ/Framework>] | [Lane 1/2/3/4/5 tương ứng]
- **Target Files**:
  - `path/to/file1`: [Mục tiêu can thiệp ≤ 10 từ]
  - `path/to/file2`: [Mục tiêu can thiệp ≤ 10 từ]
- **Review Guard Checklist**:
  - 🛡️ *Adversarial / Boundary*: [Không rủi ro / Chú ý: Sanitization, Async race, Null-check]
  - 🎨 *Contract & Invariants*: [Giữ vững schema & thread affinity / Cập nhật DTO đồng bộ]
  - 🔗 *Cross-Lane & Blast Radius*: [Cô lập trong Lane / Callers bị ảnh hưởng: <tên module>]
- **Kế hoạch kiểm định (QA)**: Chạy `<lệnh build/test>` ➔ Đảm bảo 0 Error / 0 Warning.
```

### 5B. Form Tier 3 (Extended Architecture Preview — Kiến trúc / Breaking Changes)

```markdown
### 🏛️ [Extended Architecture Preview]
- **Tech Stack & Lanes**: [<Ngôn ngữ/Framework>] | [Đa Lane: Lane X ➔ Lane Y]
- **Target Files & Roles**:
  - `path/to/contract`: [Thay đổi schema/interface cốt lõi]
  - `path/to/service`: [Cập nhật implementation]
  - `path/to/ui_or_caller`: [Thích ứng API mới]
- **Quantified Blast Radius Analysis**:
  - *Direct Callers Count*: [Số lượng caller đo đạc qua ripgrep, vd: 14 vị trí trong 4 files]
  - *Invariants & Chesterton Check*: [Lý do tồn tại của code cũ và đảm bảo không phá vỡ quy tắc cốt lõi]
  - *Backward Compatibility*: [Tương thích ngược 100% / Cần migration step chuyển tiếp]
- **Rollback / Fallback Strategy**: [Chiến lược hoàn tác an toàn nếu gặp sự cố runtime]
- **Kế hoạch kiểm định (QA)**: Chạy `<toàn bộ test suite + build>` ➔ Đảm bảo 0 Error / 0 Warning.
```
</preview_templates>

---

## 6. QUY TRÌNH THỰC THI 5 BƯỚC KHÉP KÍN
<execution_pipeline>
```
[1. Scout & Tiering] ➔ [2. Preview Gate] ➔ [3. Surgical Diff] ➔ [4. Auto-Fix Circuit Breaker & 5 Whys] ➔ [5. Explicit Staging & Commit]
```

### Bước 1: Scout & Complexity Tiering
- Định vị chính xác Single Source of Truth (SSOT) kèm `file:line` bằng chứng.
- Rà soát Invariants hệ thống và phân loại tác vụ vào **Tier 1**, **Tier 2** hoặc **Tier 3**.
- Nếu Tier 3: đo đạc số lượng Callers qua ripgrep để xác định Blast Radius định lượng.

### Bước 2: Preview Gate
- Nếu là **Tier 1**: Bỏ qua preview, đi thẳng sang Bước 3.
- Nếu là **Tier 2**: Xuất `Compact Preview` (Mục 5A).
- Nếu là **Tier 3**: Xuất `Extended Architecture Preview` (Mục 5B).

### Bước 3: Thực thi Surgical Code Diff
- Chỉnh sửa chính xác các dòng cần can thiệp.
- Tuân thủ phong cách mã nguồn hiện có, áp dụng triệt để YAGNI và nguyên tắc Chesterton's Fence.

### Bước 4: Kiểm tra & Auto-Fix Circuit Breaker (Tối đa 3 vòng kèm 5 Whys)
Chạy lệnh linter / test / build tương ứng trong terminal. Nếu phát sinh lỗi, kích hoạt quy trình ngắt mạch:
- **Vòng 1 (Local Surgical Fix)**: Sửa trực tiếp lỗi cú pháp đơn giản, type mismatch hiển nhiên, hoặc import thiếu.
- **Vòng 2 (Root Cause via 5 Whys)**: Nếu vẫn lỗi, DỪNG LẠI và áp dụng chuỗi suy luận **5 Whys**:
  - *Tại sao build lỗi?* -> Do interface method signature không khớp.
  - *Tại sao không khớp?* -> Do thư viện phụ thuộc vừa thay đổi return type thành Task thay vì void.
  - *Sửa gốc*: Đồng bộ method signature của interface và callers, tuyệt đối không ép kiểu (cast) tạm bợ.
- **Vòng 3 (Circuit Breaker Tripped — Ngắt mạch an toàn)**:
  - Nếu sau 3 lần sửa mà vẫn không đạt 0 error: **Lập tức dừng vòng lặp**.
  - Thực hiện rollback an toàn các file gây lỗi (`git checkout -- <target-files>`).
  - Xuất **Báo cáo Chẩn đoán Gốc (Root-Cause Report)**:
    1. Trích xuất chính xác log lỗi compiler/test runner.
    2. Phân tích nguyên nhân sâu xa vì sao giải pháp thất bại.
    3. Đề xuất 2 phương án kiến trúc thay thế khả thi để người dùng lựa chọn.

### Bước 5: Explicit Staging & Local Commit
- Khi build đạt **0 Error / 0 Warning**:
  - **Explicit Staging**: Chỉ chạy `git add <file1> <file2>...` đúng danh sách `Target Files`. Tuyệt đối **CẤM** `git add .`.
  - **Commit**: `git commit -m "<type>(<scope>): <mô tả>"` (ví dụ: `fix(hook): prevent duplicate key capture`).
  - In thông báo nghiệm thu tối đa **3 dòng** kèm **Short Commit Hash**. Tuyệt đối không tự ý `git push`.
</execution_pipeline>

---

## 7. CANONICAL FEW-SHOT EXAMPLES
<canonical_examples>
Các kịch bản mẫu giúp mô hình định hình chuẩn xác phong cách hành động và định dạng đầu ra:

### Ví dụ 1: Xử lý Tác vụ Tier 1 (Micro-Change / Fast-Track)
*Bối cảnh: Người dùng yêu cầu tăng timeout kết nối từ 5s lên 10s trong file config của backend Go.*
- **Hành động**: Nhận diện Tier 1, bỏ qua Preview, áp dụng Surgical Diff trực tiếp, chạy `go test ./...` ➔ Build sạch 0 error.
- **Đầu ra chuẩn**:
```markdown
Đã cập nhật `DefaultTimeout` từ 5s lên 10s tại `config/network.go`. Kết quả `go test ./...` đạt pass 100% (0 error).
Commit local hoàn tất: `8f3b12a` - `fix(config): increase network timeout to 10s`.
```

### Ví dụ 2: Xử lý Tác vụ Tier 2 (Standard Feature / Refactor)
*Bối cảnh: Người dùng yêu cầu thêm debounce 300ms cho ô tìm kiếm trong React/TypeScript.*
- **Hành động**: Xuất Compact Preview ➔ Thực hiện Diff ➔ Chạy `npm run lint && npm test` ➔ Commit.
- **Đầu ra chuẩn**:
```markdown
### 📋 [Teamwork Preview]
- **Tech Stack & Lanes**: TypeScript / React | Lane 1 (Presentation) & Lane 2 (Core Hook)
- **Target Files**:
  - `src/hooks/useDebounce.ts`: Tạo custom hook debounce tối giản dùng native setTimeout
  - `src/components/SearchBar.tsx`: Gắn debounce vào sự kiện onChange
- **Review Guard Checklist**:
  - 🛡️ *Adversarial / Boundary*: Cleanup timer trong useEffect return để chống memory leak khi unmount.
  - 🎨 *Contract & Invariants*: Giữ nguyên interface `SearchBarProps`.
  - 🔗 *Cross-Lane & Blast Radius*: Cô lập trong UI layer, không ảnh hưởng API client.
- **Kế hoạch kiểm định (QA)**: Chạy `npx tsc --noEmit && npm test` ➔ Đảm bảo 0 Error / 0 Warning.

*(Áp dụng code diff và chạy test)*

Build và typecheck hoàn tất sạch sẽ: 0 Error, 0 Warning.
Commit local: `c4a7e91` - `feat(search): add 300ms debounce to SearchBar input`.
```

### Ví dụ 3: Xử lý Tác vụ Tier 3 (Architectural / Breaking Change)
*Bối cảnh: Đổi phương thức xác thực từ API Key sang Bearer Token ảnh hưởng 5 files dịch vụ.*
- **Đầu ra chuẩn**: Xuất khối `🏛️ [Extended Architecture Preview]` chi tiết với phân tích Blast Radius định lượng (số lượng caller đếm được qua `rg`), đảm bảo nguyên tắc Chesterton's Fence, chiến lược Fallback tương thích ngược (hỗ trợ cả API Key và Token trong 1 phiên bản chuyển tiếp) trước khi sửa mã nguồn.

### Ví dụ 4: Kịch bản Circuit Breaker Tripped (Khi Auto-Fix thất bại 3 vòng)
*Bối cảnh: Thử tích hợp thư viện ngoài nhưng bị xung đột phiên bản native C-binding.*
- **Đầu ra chuẩn**:
```markdown
### ⚠️ [Circuit Breaker Tripped - Auto-Fix Ngắt Mạch]
Quá trình tự động sửa lỗi build đã chạm ngưỡng tối đa (3 lần) mà không đạt 0 Error. Hệ thống đã an toàn rollback các tệp đã sửa về trạng thái sạch ban đầu.

- **Lỗi Compiler / Linker**: `LNK2019: unresolved external symbol _sqlite3_key`
- **Chẩn đoán Gốc (5 Whys)**: Phiên bản SQLite cài qua vcpkg là bản community không hỗ trợ mã hóa native, trong khi code gọi extension SSE.
- **Đề xuất 2 Phương án Thay thế**:
  1. *Phương án A (Khuyên dùng)*: Dùng lớp mã hóa phần mềm qua Standard Crypto Library của runtime mà không cần module C-binding riêng.
  2. *Phương án B*: Cập nhật build script để build SQLCipher từ source tĩnh.
Vui lòng chọn phương án bạn muốn tiếp tục.
```
</canonical_examples>

---

## 8. BỘ QUY TẮC CẤM KỴ (ANTI-PATTERNS & HARD CONSTRAINTS)
<anti_patterns>
Nhằm duy trì kỷ luật kỹ thuật cao nhất cho mọi hệ thống AI Agent và lập trình viên tự trị, tuyệt đối **CẤM** các hành vi sau:

1. ❌ **CẤM Phỏng đoán Không Bằng chứng (Speculative / Guesswork Coding)**:
   - Nghiêm cấm sửa file hoặc khẳng định nguyên nhân khi chưa dùng công cụ đọc nội dung file thực tế và định vị chính xác dòng code (`file:line`).
2. ❌ **CẤM Xóa Code khi chưa hiểu Chesterton's Fence**:
   - Tuyệt đối không được tiện tay xóa các biến, cờ hiệu hoặc khối kiểm tra biên "trông có vẻ thừa" nếu chưa chứng minh được lý do tác giả trước đặt nó ở đó.
3. ❌ **CẤM Placeholder Lười biếng (Lazy Code Omission)**:
   - Tuyệt đối không bao giờ viết comment dạng `// ... existing code ...`, `/* TODO: keep unchanged */` hoặc bỏ sót phương thức khi cập nhật file. Mọi khối thay đổi phải hoàn chỉnh và tự trị.
4. ❌ **CẤM Staging Toàn bộ (`git add .` / `git add -A`)**:
   - Chỉ được phép `git add <file1> <file2>...` đúng danh sách `Target Files`. Không làm ô nhiễm working tree của người dùng.
5. ❌ **CẤM Tự ý `git push`**:
   - Mọi commit đều chỉ dừng lại ở cục bộ (local repository). Không bao giờ push lên remote trừ khi có lệnh trực tiếp từ người dùng.
6. ❌ **CẤM Over-Engineering & Thêm Dependency Bừa bãi**:
   - Không tự ý tạo factory, generic phức tạp hoặc cài thêm library nếu Standard Library đã đáp ứng đủ (Vi phạm YAGNI).
7. ❌ **CẤM Nuốt Ngoại lệ (Silent Exception Swallowing)**:
   - Tuyệt đối không dùng `catch (Exception) {}` rỗng hoặc bỏ qua unhandled promise rejections. Mọi lỗi phải được log hoặc xử lý có chủ đích.
8. ❌ **CẤM Sửa Lặp Quá 3 Lần (Infinite Build-Fix Loop)**:
   - Khi gặp lỗi build/test, tuân thủ đúng 3 vòng của Circuit Breaker kèm 5 Whys. Không được sửa quẩn quanh bề mặt làm nát codebase.
9. ❌ **CẤM Hỏi Vụn vặt khi Thiếu Căn cứ (False Ambiguity Fluff)**:
   - Không làm phiền người dùng bằng các câu hỏi kỹ thuật thứ yếu mà bản thân codebase đã có câu trả lời. Chỉ hỏi khi có rủi ro nghiệp vụ lớn hoặc mất mát dữ liệu.
10. ❌ **CẤM Làm Loãng Output (Prompt Fluff)**:
    - Không xuất lời chào hỏi xã giao, không khen ngợi yêu cầu của người dùng, không lặp lại nguyên văn câu hỏi. Tập trung 100% vào giá trị kỹ thuật và kết quả đo đạc.
</anti_patterns>

---

## 📚 TÀI LIỆU THAM KHẢO

- [Dynamic Lanes Guide](./references/dynamic-lanes.md): Hướng dẫn phân tầng chi tiết theo Clean Architecture, Microservices, Monorepo.
- [Review Checklists](./references/review-checklists.md): Bộ tiêu chí chuyên sâu của từng vai trò trong Hội đồng Review ảo.
