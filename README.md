# Universal Teamwork Preview & Multi-Role Review Protocol 🚀

> **Universal Teamwork Preview & Multi-Role Review Protocol cho MỌI dự án và tech stack** (Web, Backend, Mobile, CLI, Desktop, Systems, Microservices). Tối ưu hóa sâu theo kiến trúc **Kỷ luật Kỹ thuật Nguyên lý Đầu tiên (First-Principles Engineering Rigor)** kết hợp **Mô hình Tư duy Phản biện Đa chiều (Claude-Style Extended Thinking)**: Triệt tiêu ảo giác code, chống tái phạm lỗi đã fix qua nhiều máy/phiên chat, và chống sửa quẩn lặp lỗi tiêu tốn token.

---

## 🌟 Tính Năng Nổi Bật Vừa Nâng Cấp

- 🎯 **Zero-Assumption Grounding Gate (Diệt trừ ảo giác code)**: 
  - Quy tắc bất biến: *"Không có bằng chứng đọc file = Cấm viết code"*. 
  - Bắt buộc kiểm tra signature thật của các hàm helper/API (`file:line`) trước khi gọi, chấm dứt hoàn toàn việc phỏng đoán tham số.
- 🔄 **Project Memory Recall & Cross-Machine Regression Guard**:
  - Tự động chạy `git log -n 5 --oneline` để nắm bắt các bug đã fix trong các commit gần nhất.
  - Nhận diện khác biệt môi trường đa máy (SDK, line endings CRLF/LF, path separators).
  - Cổng kiểm tra chống hồi quy (Non-Regression Verification Gate), ngăn chặn việc vô tình xóa bỏ giải pháp đã sửa ở phiên trước.
- 🛑 **Anti-Oscillation Circuit Breaker (Chống sửa quẩn con lắc)**:
  - Duy trì bảng vết lỗi ngầm (Error Ledger) qua các vòng lặp sửa lỗi.
  - Phát hiện dao động con lắc (sửa A làm nổ B, sửa B làm nổ lại A) ➔ Lập tức **PIVOT** đổi phương án kiến trúc, tuyệt đối không lặp lại cách sửa đã thất bại.
- 🧩 **Cấu trúc Thẻ XML Ngữ Nghĩa**: Tối ưu hóa hoàn hảo cho các mô hình suy luận sâu (Claude 3.7 Sonnet, Claude 3.5 Sonnet, Gemini 2.5/3.8 Flash, GPT-4o, DeepSeek).
- 🧠 **Extended Cognitive Scaffold**: 
  - **Hàng rào Chesterton (Chesterton's Fence)**: Không bao giờ xóa/sửa code cũ nếu chưa hiểu nguyên nhân tác giả trước đặt nó ở đó.
  - **Self Red-Teaming (Chủ động phản bác chính mình)**: Luôn tìm kịch bản để phương án của mình bị sập trước khi quyết định viết code.
  - **Mental Dry-Run**: Mô phỏng thực thi trong tâm trí với 3 trường hợp: Dữ liệu chuẩn (Happy Path), Ngoại lệ & Dọn dẹp tài nguyên (Failure Path), và Xung đột gọi liên tục (Concurrency/Re-entrancy).
- 🔍 **3 Lăng Kính Nhận Thức (Cognitive Lenses)**:
  - 🛡️ **Adversarial Lens (Kẻ phá hoại)**: Săn tìm rủi ro biên, null/empty, race-condition, timeout, sập runtime.
  - 🧹 **Janitor & YAGNI Lens (Người dọn dẹp)**: Loại bỏ triệt để code thừa, abstraction suy đoán và package phụ thuộc không cần thiết.
  - ⚙️ **Runtime & Invariants Lens (Thời gian thực)**: Giữ vững tính bất biến hệ thống, thread affinity và quản lý tài nguyên.
- ⚡ **Complexity-Aware Tiering & Adaptive Cognitive Depth**:
  - **Tier 1 (Micro)**: Nén tư duy tối đa (Ponyman/Caveman style), sửa thẳng và verify nhanh.
  - **Tier 2 (Standard)**: CoT trọng tâm kiểm tra biên, xuất Compact Preview chuẩn mực.
  - **Tier 3 (Architectural)**: Kích hoạt toàn diện Extended Thinking, đo lường **Bán kính Tác động Định lượng (Quantified Blast Radius)** và lập chiến lược Fallback/Rollback.
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
- `"code preview"`, `"universal preview"`, `"circuit breaker"`, `"chống ảo giác"`, `"chống lặp lỗi"`

---

## 📜 Giấy Phép & Tác Giả

- **Tác giả**: [GMTPC (ghostminhtoan)](https://github.com/ghostminhtoan)
- **Email**: ghostminhtoan@gmail.com
- **Giấy phép**: MIT License
