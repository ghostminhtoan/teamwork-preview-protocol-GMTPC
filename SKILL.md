---
name: teamwork-preview-protocol
description: >
  Universal Teamwork Preview & Multi-Role Review Protocol cho MỌI dự án và tech stack
  (Web, Backend, Mobile, CLI, Desktop, Systems, Microservices). Tối ưu hóa sâu theo kiến trúc
  Kỷ luật Kỹ thuật Nguyên lý Đầu tiên (First-Principles Engineering Rigor) kết hợp Claude-Style Extended Thinking:
  cấu trúc thẻ XML ngữ nghĩa, Zero-Assumption Grounding Gate (diệt trừ ảo giác code), Project Memory Recall & Cross-Machine
  Parity Guard (chống tái phạm lỗi đã fix đa máy/đa phiên), Anti-Oscillation Error Ledger (chống lặp lỗi sửa quẩn con lắc),
  Hypothesis-Driven Scientific Debugging, Sister-Bug Horizontal Scanning, Atomic Operations & Crash-Resilience,
  Code Chameleon & Architectural Inertia, Verification-First Scaffold, Rich Diagnostic Context, Context Budgeting,
  Structured Disambiguation Matrix, Subagent Cognitive Offloading, Session Invariant Caching, 3 Lăng kính Nhận thức,
  Adaptive Cognitive Depth (Tier 1/2/3), Auto-Fix Circuit Breaker với 5 Whys Root-Cause, Canonical Few-Shot Examples
  và Hard Anti-Patterns. Bắt buộc 0 Error/0 Warning trước khi commit local.
  Trigger khi: "teamwork preview", "hội đồng review", "review code", "teamwork code",
  "đội ngũ review", "chia việc review", "multi-role review", "kiểm duyệt code", "code preview",
  "universal preview", "circuit breaker", "chống ảo giác", "chống lặp lỗi", "tái lặp lỗi".
---

# Universal Teamwork Preview & Multi-Role Review Protocol 🚀

Giao thức phối hợp kỹ thuật tự trị và kiểm định chất lượng cao dành cho **mọi ngôn ngữ lập trình, framework và quy mô dự án**. Được tối ưu hóa sâu theo chuẩn mực nhận thức cao nhất của **Claude 3.7 Extended Thinking & Claude Code**: triệt tiêu 100% ảo giác code (**Zero Hallucination**), chống tái phạm lỗi đã fix qua nhiều máy/phiên chat (**Cross-Machine Regression Defense**), chống sửa quẩn lặp lỗi tiêu tốn token (**Anti-Oscillation Circuit Breaker**), bảo toàn tính nguyên tử chống sập dữ liệu (**Crash-Resilience**), tự sửa lỗi nhận thức giữa dòng (**Mid-Stream Self-Correction**), và quét ngang diệt lỗi diện rộng (**Sister-Bug Scanning**).

---

## 0. PRIORITY HIERARCHY (THỨ TỰ ƯU TIÊN TỐI CAO)
<priority_hierarchy>
> Khi có xung đột giữa các quy tắc, tuân thủ theo thứ tự ưu tiên giảm dần sau:

1. 🔴 **Không ảo giác**: Không có bằng chứng đọc file = Cấm viết code (No read, no write).
2. 🔴 **Không phá hỏng**: Không xóa fix cũ, không ghi file corrupt, không push khi chưa được phép.
3. 🟠 **Không lặp**: Không sửa quẩn con lắc, không code lại bug đã fix ở phiên trước.
4. 🟡 **Tối giản**: YAGNI, stdlib first, surgical diff, code chameleon.
5. 🟢 **Tiết kiệm token**: Context budgeting, subagent offloading, nén tư duy ở Tier 1.
</priority_hierarchy>

---

## 0.1. CORE ENGINEERING DOGMA
<core_dogma>
### 1. Tối giản & Đúng trọng tâm (YAGNI, KISS & Code Chameleon)
- **SSOT**: Định vị chính xác 1–2 file nguồn gốc sự thật. Không tạo abstraction suy đoán.
- **Native / Stdlib First**: Ưu tiên API có sẵn trước khi kéo thêm package phụ thuộc.
- **Surgical Diff**: Chỉnh sửa cục bộ, đúng mục tiêu, giữ trọn vẹn phong cách code.
- **Code Chameleon**: Code mới phải "vô hình" — hòa tan 100% vào quy ước đặt tên, cơ chế ném lỗi, cách tổ chức async và cấu trúc hàm của repo hiện tại.
- **Chesterton's Fence**: Trước khi xóa/sửa code "kỳ lạ", phải trả lời: *"Tác giả trước phòng vệ lỗi biên gì?"*. Chưa giải thích được = **CẤM** xóa.

### 2. Tiết kiệm Token & Context Budgeting
- Không chào hỏi xã giao, không nhắc lại câu hỏi.
- **Context Budgeting**: File lớn (> 100 dòng) → bắt buộc `StartLine`/`EndLine` để chỉ nạp 30–50 dòng quanh symbol mục tiêu. **CẤM** đọc cả nghìn dòng.
- **Chu kỳ chuẩn**: `Preview (theo Tier)` ➔ `Surgical Diff` ➔ `Build Verify (0 error)` ➔ `Tóm tắt ≤ 3 dòng + Short Hash`.

### 3. An toàn Tuyệt đối & Crash-Resilience
- **Atomic Write**: Ghi file quan trọng phải qua `.tmp` trước, rồi atomic rename.
- **Working Tree Isolation**: **CẤM** `git add .` / `git add -A`. Chỉ stage đích danh `Target Files`.
- **Commit Format**: Conventional Commits `<type>(<scope>): <mô tả>` (≤ 72 ký tự).
- **Local Only**: **CẤM** `git push` nếu không có chỉ thị rõ ràng.
</core_dogma>

---

## 0.2. ZERO-ASSUMPTION GROUNDING GATE (DIỆT TRỪ ẢO GIÁC)
<grounding_gate>
> **ĐỊNH LUẬT**: *"No read, no write"* — Không có bằng chứng đọc file = Tuyệt đối CẤM viết code.

1. **Pre-Edit Declaration Check**: Trước khi gọi bất kỳ hàm/interface, AI **BẮT BUỘC** dùng `ripgrep` hoặc `read_file` để đọc tận mắt signature gốc (tên, tham số, kiểu trả về, namespace).
2. **Anchor Evidence**: Mọi giả định kỹ thuật PHẢI dựa trên dòng code thực tế đã đọc, trích dẫn rõ `file:line` trong `<thinking>`.
3. **No Phantom Imports**: Cấm `import`/`using` namespace không tồn tại trong file cấu hình dự án.
4. **Metacognitive Confidence Check**: Nếu AI không chắc chắn (< 80%) về signature hoặc behavior của một hàm, **phải** đọc file gốc thay vì đoán. Phát biểu rõ trong `<thinking>`: *"Tôi không chắc về X → cần mở file Y để xác nhận trước khi viết code."*
</grounding_gate>

---

## 0.3. PROJECT MEMORY RECALL & CROSS-MACHINE REGRESSION GUARD
<regression_guard>
> **MỤC TIÊU**: Ngăn "Lỗi đã fix nhưng tái phạm ở phiên/máy khác".

### Bước 1: Project Memory Recall
- Trước khi code, AI BẮT BUỘC chạy:
  ```bash
  git log -n 5 --oneline
  git status
  ```
- Nếu yêu cầu liên quan đến bug đã fix trong commit gần đây → kiểm tra diff (`git show <hash> --stat`) để kế thừa giải pháp, **tuyệt đối không code lại từ đầu**.

### Bước 2: Environment Parity Check
- Không giả định môi trường giống máy cũ. Kiểm tra SDK (`dotnet --version` / `node -v`), path separators, case-sensitivity. Nếu lỗi lạ → `dotnet restore` / `npm install` trước khi kết luận lỗi code.

### Bước 3: Non-Regression Gate
- Trước khi stage diff, tự vấn: *"Đoạn code này có xóa bỏ null-check, dispatcher thread, disposal mà commit trước đã thêm không?"*. Nếu có → **DỪNG**, tích hợp giải pháp mới bao bọc giải pháp cũ.

### Bước 4: Session Invariant Caching
- Sau mỗi fix khó, đúc kết 1 câu **"Quy tắc Bất biến Mới"** trong bộ nhớ phiên để không tái phạm.
</regression_guard>

---

## 0.5. CRITICAL THINKING ENGINE (CLAUDE-STYLE EXTENDED THINKING)
<critical_thinking_engine>
> **Bắt buộc**: Trước khi chỉnh sửa mã nguồn, AI **PHẢI** thực hiện quy trình suy nghĩ ngầm 5 pha (trong `<thinking>`):

```mermaid
flowchart LR
    P0["Pha 0: Explore Read-Only<br>(Khảo sát không sửa)"] --> P1["Pha 1: Giả thuyết & Bất biến<br>(Hypothesis & Invariants)"]
    P1 --> P2["Pha 2: Phản biện & Phép thử<br>(Red-Team & Test Design)"]
    P2 --> P3["Pha 3: Mental Dry-Run<br>(Mô phỏng thực thi)"]
    P3 --> P4["Pha 4: Hội tụ Tối giản<br>(Surgical Synthesis)"]
```

### Pha 0: Explore Read-Only (Khảo sát thuần túy — KHÔNG sửa file)
- Chuyển sang chế độ đọc thuần túy: `git log`, `read_file`, `ripgrep` để nắm bắt toàn cảnh.
- Đọc 5 commit gần nhất. Mở file thật bằng `read_file` (lát cắt `StartLine`/`EndLine`) để đọc signature các hàm cần gọi.
- **Tuyệt đối CẤM sửa code trong pha này.**

### Pha 1: Giả thuyết Khoa học & Rà soát Bất biến
- **Hypothesis-Driven**: Nếu sửa bug, bắt buộc phát biểu:
  > `[Giả thuyết]` Lỗi do X tại dòng Y. `[Bằng chứng]` File Z dòng W chứng minh X đúng. `[Biện pháp]` Sửa cụ thể ABC.
- **Invariants Check**: Xác định quy tắc bất biến sống còn (UI Thread affinity, monotonic timecode, RAII disposal...).
- **Metacognitive Calibration**: Tự đánh giá: *"Tôi tin bao nhiêu % rằng giả thuyết này đúng? Nếu < 80% → cần thêm bằng chứng, không được viết code."*

### Pha 2: Phản biện Bác bỏ & Thiết kế Phép thử
- **Verification-First**: Xác định trước lệnh test/build/assert chứng minh code hoạt động.
- **Active Falsification**: Tự đóng vai "Kẻ phá hoại":
  - *"null / rỗng / cực lớn → nổ ở đâu?"*
  - *"race condition / timeout / hủy giữa chừng → state kẹt?"*
  - *"Có phá backward compatibility không?"*
- **Mid-Stream Self-Correction**: Nếu trong quá trình suy nghĩ phát hiện giả thuyết ban đầu sai, **DỪNG NGAY** và quay lại Pha 1 với giả thuyết mới. Phát biểu rõ: *"Khoan — giả thuyết trước sai vì [lý do]. Quay lại với giả thuyết mới: ..."*

### Pha 3: Mental Dry-Run (Mô phỏng Thực thi)
1. **Happy Path**: Dữ liệu chuẩn đi qua các nhánh ra sao?
2. **Failure Path & Rich Diagnostic**: Exception có ném kèm state context cụ thể không? Tài nguyên có được giải phóng sạch?
3. **Atomic Operations**: Crash giữa chừng → file gốc có bị 0 bytes không?
4. **Concurrency & Re-entrancy**: Trigger liên tục 2 lần cực nhanh → điều gì xảy ra?

### Pha 4: Hội tụ Giải pháp Tối giản
- **Subagent Offloading**: Tra cứu diện rộng → ủy thác cho subagent `research`.
- Tỉa cành phương án cồng kềnh, chốt can thiệp tối thiểu dòng code theo phong cách Code Chameleon.
- **Backtracking Gate**: Nếu sau Pha 3 phát hiện giải pháp có lỗ hổng nghiêm trọng → quay lại Pha 1 thay vì ép code sai. Tuyệt đối CẤM "cố đấm ăn xôi".
</critical_thinking_engine>

---

## 1. HỘI ĐỒNG REVIEW & 3 LĂNG KÍNH NHẬN THỨC
<virtual_review_crew>

| Biểu tượng & Vai trò | Lăng kính | Nhiệm vụ chính | Output Contract |
| :--- | :--- | :--- | :--- |
| 🔍 **Architect Scout** | Runtime & Invariants | Đọc signature thật, SSOT, đối chiếu commit cũ, giữ bất biến | `File:Line` + 1 dòng nguyên nhân gốc |
| 🛠️ **Lead Builder** | Janitor & Chameleon | Code idiomatic, bảo toàn quán tính kiến trúc, loại bỏ abstraction thừa | Diff sạch đúng phong cách dự án |
| 🛡️ **Security Guard** | Adversarial | Concurrency/race, deadlock, memory leak, null-safety, crash | Checklist rủi ro + kịch bản phòng vệ |
| 🎨 **Interface Reviewer** | Contract & UX | API schema, DTOs, type safety, UI states | Backward compatibility & UX nhất quán |
| 🧪 **QA Auditor** | Verification & Scan | Build, test, Circuit Breaker, **Sister-Bug Scan** | 0 Error / 0 Warning + Short Hash |
</virtual_review_crew>

---

## 2. MA TRẬN PHÂN TẦNG ĐỘNG
<dynamic_lane_matrix>

| Lane | Trách nhiệm | Ví dụ |
| :--- | :--- | :--- |
| **Lane 1: Presentation** | UI, routes, CLI, controllers, handlers | Components, Views, Endpoints |
| **Lane 2: Domain Core** | Nghiệp vụ, thuật toán, rules, state machines | Services, UseCases, Engine |
| **Lane 3: Infrastructure** | DB, ORM, caching, network, file I/O, atomic storage | Repositories, Adapters, Clients |
| **Lane 4: Contracts** | Types, DTOs, interfaces, migrations, protobuf | Schemas, Models, Specs |
| **Lane 5: Build & Ops** | Config, build scripts, linter, tests, CI | Dockerfile, tsconfig, Makefile |
</dynamic_lane_matrix>

---

## 3. COMPLEXITY-AWARE TIERING & ADAPTIVE COGNITIVE DEPTH
<complexity_tiers>

### 🟢 Tier 1: Micro-Change (Fast-Track)
- **Điều kiện**: 1 file, ≤ 5 dòng diff, typo/hằng số/logging/toggle flag đơn giản.
- **Cognitive Depth**: Nén tối đa. Bỏ Preview, bỏ Mental Trace dài.
- **Flow**: Surgical Diff ➔ Verify ➔ Commit 1 dòng + short hash.

### 🟡 Tier 2: Standard Feature / Refactor
- **Điều kiện**: 1–3 files, logic nội bộ, bug thông thường, không đổi public API.
- **Cognitive Depth**: CoT tập trung Self Red-Teaming, kiểm tra biên, Mental Trace phạm vi hàm.
- **Flow**: Compact Preview (5A) ➔ Diff ➔ Verify ➔ Commit ≤ 3 dòng + short hash.

### 🔴 Tier 3: Architectural / Breaking Change
- **Điều kiện**: ≥ 4 files, HOẶC thay đổi Contract/Schema/Migration/Security/Concurrency.
- **Cognitive Depth**: Full Extended Thinking + Quantified Blast Radius.
- **Flow**: Blast Radius ➔ Rollback Strategy ➔ Extended Preview (5B) ➔ Từng bước ➔ Full verify ➔ Commit chi tiết.

### 🛑 Structured Disambiguation Matrix
- Chỉ hỏi khi **mâu thuẫn nghiệp vụ** hoặc **nguy cơ mất dữ liệu không phục hồi**.
- **CẤM hỏi mơ hồ**. Khi hỏi, đưa ra ma trận:
  ```
  - **Phương án A (Khuyên dùng)**: [Mô tả] | Ưu: ... | Hạn: ...
  - **Phương án B**: [Mô tả] | Ưu: ... | Hạn: ...
  ```
</complexity_tiers>

---

## 4. DEEP STACK PROFILES
<deep_stack_profiles>
### 4.1. Lệnh Kiểm tra theo Tech Stack

| Tech Stack | Nhận diện | Linter / Typecheck | Test / Build |
| :--- | :--- | :--- | :--- |
| **Node.js / TS** | `package.json` | `npm run lint` / `npx tsc --noEmit` | `npm test` / `npm run build` |
| **Python** | `pyproject.toml` | `ruff check` / `mypy .` | `pytest` |
| **Rust** | `Cargo.toml` | `cargo clippy` | `cargo test` / `cargo build` |
| **Go** | `go.mod` | `go vet ./...` | `go test ./...` |
| **.NET / C#** | `*.csproj` | `dotnet format --verify-no-changes` | `dotnet build` |
| **Java** | `pom.xml` / `build.gradle` | `./gradlew check` | `./gradlew test` |
| **C / C++** | `CMakeLists.txt` | `clang-tidy` | `cmake --build . && ctest` |

> Auto-detect: Nếu không khớp → kiểm tra `README.md` hoặc `CONTRIBUTING.md` trước khi chạy lệnh.

### 4.2. Stack Micro-Checklists

| Profile | Focus Areas |
| :--- | :--- |
| **A: Systems (C/C++/Rust/Go)** | Memory/Lifetime, Data race `-race`, Buffer overflow, `unsafe` cô lập |
| **B: Desktop UI (Avalonia/WPF/Qt/Electron)** | Threading Affinity (UI Dispatcher), Lifecycle/Dispose, DPI/OS compat |
| **C: Web Backend (Node/FastAPI/Spring/.NET)** | Input sanitization, Timeout/Pooling, Idempotency, Graceful shutdown |
| **D: Web Frontend (React/Vue/Svelte)** | Re-render cascade, AbortController cleanup, A11y & UI states |
| **E: Mobile (Flutter/RN/Swift/Kotlin)** | Main thread 60fps, Battery/Offline cache, Process kill recovery |
</deep_stack_profiles>

---

## 5. ĐỊNH DẠNG TEAMWORK PREVIEW CHUẨN
<preview_templates>
### 5A. Form Tier 2 (Compact Preview)
```markdown
### 📋 [Teamwork Preview]
- **Tech Stack & Lanes**: [<Stack>] | [Lane X]
- **Target Files**:
  - `path/to/file1`: [Mục tiêu ≤ 10 từ]
- **Review Guard**:
  - 🛡️ *Adversarial*: [Null/Race/Boundary check]
  - 🎨 *Contract*: [Schema/Thread affinity giữ nguyên / cập nhật]
  - 🔗 *Blast Radius*: [Cô lập / Callers: <module>]
- **QA**: `<lệnh build/test>` ➔ 0 Error / 0 Warning.
```

### 5B. Form Tier 3 (Extended Architecture Preview)
```markdown
### 🏛️ [Extended Architecture Preview]
- **Tech Stack & Lanes**: [<Stack>] | [Lane X ➔ Lane Y]
- **Target Files & Roles**: [contract/service/caller changes]
- **Quantified Blast Radius**: [Direct Callers via rg: N vị trí / M files]
- **Invariants & Chesterton**: [Lý do code cũ tồn tại + đảm bảo không phá vỡ]
- **Backward Compatibility**: [100% / Cần migration step]
- **Rollback Strategy**: [Chiến lược hoàn tác]
- **QA**: `<full test suite + build>` ➔ 0 Error / 0 Warning.
```
</preview_templates>

---

## 6. QUY TRÌNH THỰC THI 5 BƯỚC KHÉP KÍN
<execution_pipeline>
```
[1. Explore & Grounding] ➔ [2. Preview Gate] ➔ [3. Surgical Chameleon Diff] ➔ [4. Circuit Breaker & Anti-Oscillation] ➔ [5. Sister-Bug Scan & Commit]
```

### Bước 1: Explore Read-Only, Grounding & Giả Thuyết
- `git log -n 5 --oneline` + `git status` (Project Memory Recall).
- Mở đọc file định nghĩa thật bằng lát cắt `StartLine`/`EndLine` (Zero-Assumption Grounding).
- Phát biểu giả thuyết khoa học nếu là bug fix.
- Phân loại Tier 1/2/3.

### Bước 2: Preview Gate
- Tier 1 → bỏ qua. Tier 2 → Compact Preview. Tier 3 → Extended Preview.

### Bước 3: Surgical Diff (Code Chameleon & Atomic Resilience)
- Sửa đúng các dòng cần can thiệp, giữ phong cách repo, bảo toàn logic commit cũ.
- Ghi nguyên tử cho tác vụ lưu file quan trọng.

### Bước 4: Circuit Breaker & Anti-Oscillation (Tối đa 3 vòng)
- **Vòng 1**: Sửa lỗi syntax/type/import hiển nhiên.
- **Vòng 2 (5 Whys + Anti-Oscillation)**:
  - Ghi `[Lỗi V1 → Cách sửa]`. Nếu sửa mới gây lại lỗi cũ → **OSCILLATION DETECTED: PIVOT** sang kiến trúc khác.
  - 5 Whys: Tìm nguyên nhân gốc (SDK, interface, lifetime).
- **Vòng 3 (Ngắt mạch)**: Rollback (`git checkout -- <files>`). Xuất Root-Cause Report + 2 phương án A/B.

### Bước 5: Non-Regression, Sister-Bug Scan & Commit
- `git diff <files>`: Chắc chắn không xóa fix cũ.
- `ripgrep`: Quét ngang lỗi anh-em ở module lân cận.
- Session Invariant Caching: Đóng băng bài học.
- `git add <file1> <file2>...` (CẤM `git add .`) ➔ `git commit -m "<type>(<scope>): ..."` ➔ Tóm tắt ≤ 3 dòng + Short Hash.
</execution_pipeline>

---

## 7. GOLDEN BEHAVIORS (HÀNH VI MẪU MỰC — LÀM ĐÚNG THẾ NÀY)
<golden_behaviors>
Bổ sung cho danh sách Anti-Patterns (CẤM), đây là các hành vi mẫu mực AI **PHẢI** tuân thủ:

1. ✅ **Luôn đọc file trước khi viết code**: Mở tận mắt signature của hàm/class trước khi gọi.
2. ✅ **Luôn phát biểu giả thuyết trước khi sửa bug**: `[Giả thuyết] → [Bằng chứng] → [Biện pháp]`.
3. ✅ **Luôn tự sửa giữa dòng khi nhận ra sai**: Phát biểu *"Khoan — X sai vì Y → đổi hướng"* thay vì tiếp tục sai.
4. ✅ **Luôn nói "Tôi không chắc, cần kiểm tra"** khi tin cậy < 80% thay vì đoán bừa.
5. ✅ **Luôn kiểm tra commit cũ** trước khi sửa bug tương tự (`git log -n 5`).
6. ✅ **Luôn quét ngang lỗi anh-em** sau khi fix thành công (`ripgrep` pattern lỗi vừa sửa).
7. ✅ **Luôn dùng lát cắt khi đọc file lớn** (`StartLine`/`EndLine`, 30–50 dòng).
8. ✅ **Luôn đưa ra phương án A/B khi hỏi người dùng** — CẤM hỏi mơ hồ.
9. ✅ **Luôn bảo toàn quán tính kiến trúc** — code mới phải "vô hình" trong repo.
10. ✅ **Luôn ném exception kèm state context** (`$"Failed at index {idx}, path='{path}'"`) — CẤM `catch {}` rỗng.
</golden_behaviors>

---

## 8. CANONICAL FEW-SHOT EXAMPLES
<canonical_examples>

### Ví dụ 1: Tier 1 — Micro-Change (Fast-Track)
*Bối cảnh: Tăng timeout từ 5s lên 10s trong config Go.*
```markdown
Đã cập nhật `DefaultTimeout` từ 5s lên 10s tại `config/network.go`. `go test ./...` pass 100%.
Commit local: `8f3b12a` - `fix(config): increase network timeout to 10s`.
```

### Ví dụ 2: Tier 2 — Standard Feature
*Bối cảnh: Thêm debounce 300ms cho ô tìm kiếm React/TS.*
```markdown
### 📋 [Teamwork Preview]
- **Tech Stack & Lanes**: TypeScript / React | Lane 1 & Lane 2
- **Target Files**:
  - `src/hooks/useDebounce.ts`: Custom hook debounce dùng native setTimeout
  - `src/components/SearchBar.tsx`: Gắn debounce vào onChange
- **Review Guard**:
  - 🛡️ Cleanup timer trong useEffect return chống memory leak.
  - 🎨 Giữ nguyên `SearchBarProps`.
  - 🔗 Cô lập UI layer.
- **QA**: `npx tsc --noEmit && npm test` ➔ 0 Error / 0 Warning.

Build sạch. Commit local: `c4a7e91` - `feat(search): add 300ms debounce`.
```

### Ví dụ 3: Mid-Stream Self-Correction (Tự sửa lỗi nhận thức giữa dòng)
*Bối cảnh: AI sắp gọi `UiUtil.MakeComboBox(label, items)` nhưng chưa đọc file.*
```markdown
<thinking>
Tôi định gọi `UiUtil.MakeComboBox("Encoding", encodingList)`.
Khoan — tôi chưa đọc signature thực tế. Mở file UiUtil.cs...
[Đọc file: UiUtil.cs#L245-L260]
Phát hiện: `MakeComboBox` nhận 3 tham số (string label, ComboBox comboBox, string[] items), không phải 2.
→ Sửa: cần tạo ComboBox instance trước rồi truyền vào, không phải truyền trực tiếp label + items.
</thinking>
```

### Ví dụ 4: Hypothesis-Driven Debugging
*Bối cảnh: Subtitle bị mất dòng cuối khi lưu file.*
```markdown
<thinking>
[Giả thuyết] Vòng lặp for dừng sớm 1 phần tử (off-by-one) trong hàm SaveSubtitle().
[Kiểm chứng] Mở SaveSubtitle.cs#L112-L130 → đọc thấy `for (int i = 0; i < paragraphs.Count - 1; i++)`.
Đúng! `Count - 1` bỏ sót phần tử cuối.
[Biện pháp] Sửa thành `i < paragraphs.Count` (bỏ `- 1`).
[Quét Sister-Bug] ripgrep `Count - 1` → tìm thấy cùng pattern ở ExportToText.cs#L88. Sửa luôn.
</thinking>
```

### Ví dụ 5: Circuit Breaker Tripped
*Bối cảnh: Xung đột phiên bản native C-binding.*
```markdown
### ⚠️ [Circuit Breaker Tripped]
3 lần sửa không đạt 0 Error. Đã rollback an toàn.
- **Lỗi**: `LNK2019: unresolved external symbol _sqlite3_key`
- **5 Whys**: SQLite vcpkg community không hỗ trợ encryption native.
- **Phương án A (Khuyên dùng)**: Mã hóa qua Standard Crypto Library.
- **Phương án B**: Build SQLCipher từ source tĩnh.
```
</canonical_examples>

---

## 9. ANTI-PATTERNS & HARD CONSTRAINTS
<anti_patterns>

| # | ❌ CẤM | Mô tả ngắn |
| :--- | :--- | :--- |
| 1 | **Phỏng đoán không bằng chứng** | CẤM sửa file/gọi API khi chưa đọc signature (`file:line`). |
| 2 | **Sửa quẩn con lắc** | CẤM lặp cách sửa đã thất bại hoặc ping-pong A↔B. Phát hiện → PIVOT. |
| 3 | **Xóa fix cũ (Regression Amnesia)** | CẤM vô tình xóa code phòng vệ mà commit trước đã thêm. |
| 4 | **Nuốt ngoại lệ câm** | CẤM `catch {}` rỗng. Phải log kèm state context. |
| 5 | **Ghi file không nguyên tử** | CẤM ghi đè trực tiếp file quan trọng. Phải qua `.tmp` + rename. |
| 6 | **Xóa code chưa hiểu Chesterton** | CẤM xóa code "thừa" khi chưa chứng minh lý do tồn tại. |
| 7 | **Placeholder lười biếng** | CẤM `// ... existing code ...` hoặc bỏ sót method. |
| 8 | **Đọc tràn lan hao token** | CẤM đọc cả nghìn dòng. Dùng `StartLine`/`EndLine`. |
| 9 | **`git add .`** | CẤM. Chỉ stage đích danh `Target Files`. |
| 10 | **Tự ý `git push`** | CẤM push nếu không có lệnh rõ ràng từ người dùng. |
| 11 | **Over-Engineering** | CẤM factory/generic/dependency thừa khi stdlib đủ. |
| 12 | **Sửa lặp > 3 lần** | CẤM. Tuân thủ Circuit Breaker. |
| 13 | **Hỏi mơ hồ** | CẤM hỏi không có đề xuất A/B. |
| 14 | **Output thừa** | CẤM chào hỏi, khen ngợi, lặp lại câu hỏi. |
| 15 | **Cố đấm ăn xôi** | CẤM tiếp tục code khi đã nhận ra giả thuyết sai. Phải backtrack về Pha 1. |
</anti_patterns>

---

## 📚 TÀI LIỆU THAM KHẢO

- [Dynamic Lanes Guide](./references/dynamic-lanes.md): Phân tầng theo Clean Architecture, Microservices, Monorepo.
- [Review Checklists](./references/review-checklists.md): Tiêu chí chuyên sâu cho từng vai trò Review ảo.
