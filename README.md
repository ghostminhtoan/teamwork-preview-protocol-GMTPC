# Universal Teamwork Preview & Multi-Role Review Protocol 🚀

> **Universal Teamwork Preview & Multi-Role Review Protocol cho MỌI dự án và tech stack** (Web, Backend, Mobile, CLI, Desktop, Systems, Microservices). Tối ưu hóa sâu theo kiến trúc **Kỷ luật Kỹ thuật Nguyên lý Đầu tiên (First-Principles Engineering Rigor)** kết hợp **Mô hình Tư duy Phản biện Đa chiều (Claude-Style Extended Thinking)**: Triệt tiêu 100% ảo giác code, chống tái phạm lỗi đã fix qua nhiều máy/phiên chat, chống sửa quẩn lặp lỗi tiêu tốn token, bảo toàn tính nguyên tử chống sập dữ liệu, và quét ngang diệt lỗi diện rộng.

---

## 🌟 Tính Năng Nổi Bật Vừa Nâng Cấp (Claude 3.7 Tier)

- 🎯 **Zero-Assumption Grounding Gate (Diệt trừ ảo giác code)**: 
  - Quy tắc bất biến: *"Không có bằng chứng đọc file = Cấm viết code"*. 
  - Bắt buộc kiểm tra signature thật của các hàm helper/API (`file:line`) trước khi gọi, chấm dứt hoàn toàn việc phỏng đoán tham số.
- 🔄 **Project Memory Recall & Cross-Machine Regression Guard**:
  - Tự động chạy `git log -n 5 --oneline` để nắm bắt các bug đã fix trong các commit gần nhất.
  - Nhận diện khác biệt môi trường đa máy (SDK, line endings CRLF/LF, path separators).
  - Cổng kiểm tra chống hồi quy (Non-Regression Verification Gate), ngăn chặn việc vô tình xóa bỏ giải pháp đã sửa ở phiên trước.
- 🛑 **Anti-Oscillation Circuit Breaker (Chống sửa quẩn con lắc & 5 Whys Pivot)**:
  - Duy trì bảng vết lỗi ngầm (Error Ledger) qua các vòng lặp sửa lỗi.
  - Phát hiện dao động con lắc (sửa A làm nổ B, sửa B làm nổ lại A) ➔ Lập tức **PIVOT** đổi phương án kiến trúc, tuyệt đối không lặp lại cách sửa đã thất bại.
- 🔬 **Hypothesis-Driven Scientific Debugging**:
  - Phát biểu rõ: `[Giả thuyết]` ➔ `[Bằng chứng kiểm chứng]` ➔ `[Biện pháp can thiệp]` trước khi sửa bug phức tạp.
- 🔭 **Sister-Bug Horizontal Scanning (Truy lùng lỗi anh-em)**:
  - Tự động dùng `ripgrep` quét ngang các module lân cận sau khi sửa bug để triệt tiêu các lỗi bị nhân bản do copy-paste code.
- 💾 **Bất biến Ghi Nguyên tử (Atomic Write & Crash-Resilience)**:
  - Lưu file cấu hình/dữ liệu quan trọng qua tệp tạm `.tmp` rồi mới atomic rename, chống hỏng file thành 0 bytes khi phần mềm crash đột ngột.
- 🦎 **Quy tắc Tắc kè hoa (Code Chameleon & Architectural Inertia)**:
  - Giữ vững 100% quán tính kiến trúc, hòa tan tuyệt đối vào phong cách đặt tên, cơ chế ném lỗi và cấu trúc hàm của repo.
- ✂️ **Quản trị Ngân sách Ngữ cảnh (Context Budgeting)**:
  - Bắt buộc dùng lát cắt `StartLine`/`EndLine` (30–50 dòng), cấm đọc tràn lan cả nghìn dòng làm loãng chú ý và hao token.
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
