# 🔄 BẢN GHI THAY ĐỔI & CODEGRAPH (thay-doi.md)
**Cơ chế:** Sliding Window (Cửa sổ trượt 3 Prompt gần nhất: Prompt N, N-1, N-2)  
**Công nghệ giám sát:** CodeGraph AST Analysis & Blast Radius Detection  
**Dự án:** Agency Creative & Engineering AI Orchestrator  
**Cập nhật lần cuối:** 19/10/2026 · 00:59:30 (GMT+7)  

---

## 🟢 PROMPT [N] — HIỆN TẠI (19/10/2026 · 00:59:30)
**Nội dung yêu cầu:** Kiểm toán toàn bộ hệ thống skill, chạy test kiểm tra đạt đủ yêu cầu cho Designer Đồ họa Agency, viết tài liệu README hoàn chỉnh và đẩy toàn bộ lên GitHub.

### 1. Phân tích CodeGraph & AST Blast Radius:
- **Tập tin tạo mới:**
  - [`.agent/.bangiao/visual-dna.json`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/.bangiao/visual-dna.json): Khóa Seed DNA, token màu CMYK, Rich Black, Mascot Specs, SVG `<defs>`.
  - [`.agent/.bangiao/ke-hoach.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/.bangiao/ke-hoach.md): Kế hoạch kết hợp BA + Engineering + Designer.
  - [`.agent/.bangiao/thay-doi.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/.bangiao/thay-doi.md): Cửa sổ trượt ghi nhận thay đổi AST.
  - [`.agent/.bangiao/danh-gia.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/.bangiao/danh-gia.md): Đánh giá QA/QC & hiệu năng.
  - [`.agent/.bangiao/ket-qua-test.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/.bangiao/ket-qua-test.md): Biên bản nghiệm thu Acceptance Criteria.
  - [`tests/test_agency_system.py`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/tests/test_agency_system.py): Bộ kiểm thử tự động toàn diện cho hệ thống 81 skills và nghiệp vụ Designer.
  - [`README.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/README.md): Bản tài liệu kiến trúc kỹ thuật cấp cao và hướng dẫn vận hành toàn diện.
  - [`.gitignore`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.gitignore): Loại trừ file tạm, cache, `.scratch`.
- **Phạm vi tác động (Blast Radius):**
  - Cấp độ an toàn: **Cô lập tuyệt đối (Zero side-effects)**.
  - Toàn bộ 81 kỹ năng trong `.agent/skills/` được giữ nguyên vẹn 100%, bảo lưu toàn bộ docstring và cấu trúc YAML frontmatter.
  - Đồng bộ hóa hoàn hảo với cấu trúc 3 tài liệu định tuyến: `AGENTS.md`, `CODEX.md`, `CLAUDE.md`.

---

## 🟡 PROMPT [N-1] — LIỀN KỀ TRƯỚC (19/10/2026 · 00:20:00)
**Nội dung yêu cầu:** Tích hợp bộ kỹ năng đồ họa chuyên sâu (Mascot IP, Event Merch, Prepress ExtendScript, IMC Campaign Architect) và thiết lập cấu trúc Fast Dispatch 81 Skills.

### 1. Phân tích CodeGraph & AST Blast Radius:
- **Tập tin tạo/cập nhật:**
  - `.agent/skills/Designer/imc-campaign-architect/SKILL.md`
  - `.agent/skills/Designer/brand-motif-engine/SKILL.md`
  - `.agent/skills/Designer/event-merch-and-artcraft/SKILL.md`
  - `.agent/skills/Designer/mascot-sheet/SKILL.md`
  - `.agent/skills/Designer/adobe-prepress-bridge/SKILL.md`
  - `.agent/skills/UX.UI/experiential-festival-web/SKILL.md`
  - `.agent/AGENTS.md`, `.agent/CODEX.md`, `.agent/CLAUDE.md`
- **Ký hiệu AST bổ sung:** 6 core skills mở rộng chuyên biệt cho Agency sáng tạo, giải quyết triệt để lỗi "Lazy Overview" và thiếu sót vật phẩm in ấn thực tế.

---

## ⚪ PROMPT [N-2] — QUÁ KHỨ (18/10/2026 · 05:46:00)
**Nội dung yêu cầu:** Xây dựng quy chuẩn tài liệu hướng dẫn kỹ thuật cho các tính năng: Socratic Grilling, CodeGraph MCP, Adobe MCP và Artcraft MCP.

### 1. Phân tích CodeGraph & AST Blast Radius:
- **Tập tin tạo mới trong `.agent/Feature/`:**
  - `.agent/Feature/How to execute Socratic Grilling and Bangiao 4-step loop.md`
  - `.agent/Feature/How to use codegraph for codex.md`
  - `.agent/Feature/How to connect MCP of codex for app Adobe for AI agent.md`
  - `.agent/Feature/How to connect MCP of codex for app Artcaft for AI agent.md`
- **Tác động:** Chuẩn hóa quy trình kết nối MCP Socket cổng 49494 và BatchPlay API cho Adobe Photoshop & Illustrator.
