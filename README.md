# Universal Teamwork Preview & Multi-Role Review Protocol 🚀

> **Universal Teamwork Preview & Multi-Role Review Protocol cho MỌI dự án và tech stack** (Web, Backend, Mobile, CLI, Desktop, Systems, Microservices). Tối ưu hóa sâu theo kiến trúc **Kỷ luật Kỹ thuật Nguyên lý Đầu tiên (First-Principles Engineering Rigor)** kết hợp **Mô hình Tư duy Phản biện Đa chiều (Claude-Style Extended Thinking)**: Giúp bất kỳ mô hình AI nào (Gemini, Claude, GPT, DeepSeek) đều có thể suy luận sắc bén, gỡ lỗi chính xác và tự trị tuyệt đối như Claude 3.7.

---

## 🌟 Tính Năng Nhận Thức Đỉnh Cao (Claude 3.7 Thinking Tier)

- 👑 **Thứ Tự Ưu Tiên Tối Cao (Priority Hierarchy)**:
  - Phân tầng ranh giới khi có xung đột: `1. Không ảo giác` ➔ `2. Không phá hỏng` ➔ `3. Không lặp` ➔ `4. Tối giản (YAGNI)` ➔ `5. Tiết kiệm token`.
- 🔍 **Pha Khảo Sát Thuần Túy (Explore Read-Only Phase)**:
  - Bắt buộc vào chế độ chỉ đọc để khảo sát toàn diện codebase trước khi chạm vào bất kỳ file nào. Tuyệt đối cấm vừa đọc vừa sửa mò mẫm.
- 🎯 **Zero-Assumption Grounding Gate (Diệt trừ ảo giác code)**: 
  - Quy tắc bất biến: *"Không có bằng chứng đọc file = Cấm viết code" (No read, no write)*. 
  - Bắt buộc kiểm tra signature thật của hàm/API (`file:line`) trước khi gọi.
- 🔄 **Tự Sửa Lỗi Nhận Thức Giữa Dòng (Mid-Stream Self-Correction & Backtracking)**:
  - Phát hiện giả thuyết sai ngay trong quá trình suy nghĩ ➔ Lập tức **dừng lại và quay lui (backtrack)** về Pha 1 thay vì cố đấm ăn xôi.
- 🛑 **Anti-Oscillation Circuit Breaker (Chống sửa quẩn con lắc & 5 Whys Pivot)**:
  - Duy trì bảng vết lỗi ngầm (Error Ledger).
  - Phát hiện dao động con lắc (sửa A làm nổ B, sửa B làm nổ lại A) ➔ Lập tức **PIVOT** đổi phương án kiến trúc, tuyệt đối không lặp lại cách sửa đã thất bại.
- 🔬 **Hypothesis-Driven Scientific Debugging**:
  - Phát biểu rõ: `[Giả thuyết]` ➔ `[Bằng chứng kiểm chứng]` ➔ `[Biện pháp can thiệp]` trước khi sửa bug phức tạp.
- 🔭 **Sister-Bug Horizontal Scanning (Truy lùng lỗi anh-em)**:
  - Tự động dùng `ripgrep` quét ngang các module lân cận sau khi sửa bug để triệt tiêu các lỗi bị nhân bản do thói quen copy-paste code.
- 💾 **Bất biến Ghi Nguyên tử (Atomic Write & Crash-Resilience)**:
  - Lưu file cấu hình/dữ liệu quan trọng qua tệp tạm `.tmp` rồi mới atomic rename, chống hỏng file thành 0 bytes khi phần mềm crash đột ngột.
- 🦎 **Quy tắc Tắc kè hoa (Code Chameleon & Architectural Inertia)**:
  - Giữ vững 100% quán tính kiến trúc, hòa tan tuyệt đối vào phong cách đặt tên, cơ chế ném lỗi và cấu trúc hàm của repo.
- ✂️ **Quản trị Ngân sách Ngữ cảnh (Context Budgeting)**:
  - Bắt buộc dùng lát cắt `StartLine`/`EndLine` (30–50 dòng), cấm đọc tràn lan cả nghìn dòng làm loãng chú ý và hao token.
- 🌟 **Bộ 10 Hành Vi Mẫu Mực Tích Cực (Golden Behaviors)**:
  - Định hình rõ ràng những gì AI **PHẢI LÀM** bên cạnh danh sách những điều **CẤM**, giúp các LLM tuân thủ tự nhiên và chuẩn xác 100%.
- 📊 **Ma Trận Giải Quyết Mơ Hồ Có Cấu Trúc (Structured Disambiguation Matrix)**:
  - Không hỏi mơ hồ; cung cấp phương án so sánh A vs B kèm trade-off cụ thể khi cần người dùng ra quyết định.
- 🔒 **Rào Chắn Working Tree**: Tuyệt đối cấm `git add .`, chỉ stage đích danh `Target Files`. Bắt buộc 0 Error / 0 Warning trước khi commit local.

---

## 📂 Cấu Trúc Dự Án

```
teamwork-preview-protocol/
├── SKILL.md                          # Tệp hướng dẫn giao thức cốt lõi (Core Protocol)
├── README.md                         # Tài liệu giới thiệu tổng quan
└── references/
    ├── dynamic-lanes.md              # Hướng dẫn phân tầng 5 Lane kiến trúc
    └── review-checklists.md          # Bộ tiêu chí chi tiết cho Hội đồng Review ảo
```

---

## 🚀 Hướng Dẫn Sử Dụng

### 1. Cài đặt vào Agent / Skill System
Đặt thư mục `teamwork-preview-protocol` vào thư mục skills của dự án hoặc hệ sinh thái agent của bạn:
- Antigravity / Claude Code: `.agents/skills/teamwork-preview-protocol`
- Gemini / Local Config: `~/.gemini/config/skills/teamwork-preview-protocol`

### 2. Từ khóa kích hoạt (Triggers)
Skill tự động kích hoạt khi xuất hiện các cụm từ:
- `"teamwork preview"`, `"hội đồng review"`, `"review code"`, `"teamwork code"`
- `"đội ngũ review"`, `"chia việc review"`, `"multi-role review"`, `"kiểm duyệt code"`
- `"code preview"`, `"universal preview"`, `"circuit breaker"`, `"chống ảo giác"`, `"chống lặp lỗi"`, `"tái lặp lỗi"`

---

## 📜 Giấy Phép & Tác Giả

- **Tác giả**: [GMTPC (ghostminhtoan)](https://github.com/ghostminhtoan)
- **Email**: ghostminhtoan@gmail.com
- **Giấy phép**: MIT License
