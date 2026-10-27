# 🔄 BẢN GHI THAY ĐỔI & CODEGRAPH (thay-doi.md)
**Cơ chế:** Sliding Window (Cửa sổ trượt 3 Prompt gần nhất: Prompt N, N-1, N-2)  
**Công nghệ giám sát:** CodeGraph AST Analysis & Blast Radius Detection  
**Dự án:** Agency Creative & Engineering AI Orchestrator  
**Cập nhật lần cuối:** 28/10/2026 · 01:14:30 (GMT+7)  

---

## 🟢 PROMPT [N] — HIỆN TẠI (28/10/2026 · 01:14:30)
**Nội dung yêu cầu:** /find-skills kiếm những skill phù hợp để làm nét video hoặc tăng chất lượng video của adobe after effect và nạp toàn bộ skill của mục agent vào kho skill của antigravity.

### 1. Phân tích CodeGraph & AST Blast Radius:
- **Kỹ năng mới tìm thấy và tích hợp (3 skills):**
  - [`.agent/skills/Designer/after-effects/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills/Designer/after-effects/SKILL.md): Cẩm nang chuyên sâu về Adobe After Effects (Expressions, Rigging, Detail-preserving Upscale, Export ProRes/H.264 qua AME, Performance Triage, ExtendScript).
  - [`.agent/skills/Designer/topaz-video-enhancement/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills/Designer/topaz-video-enhancement/SKILL.md): Công nghệ phục chế AI cho video (Topaz Video AI models: Proteus, Iris, Gaia, Artemis; deinterlace, motion deblur, khử nhiễu, phóng to SD->HD, HD->4K/8K).
  - [`.agent/skills/Designer/ffmpeg/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills/Designer/ffmpeg/SKILL.md): Xử lý video dòng lệnh công suất cao (Lanczos scaling, CAS contrast adaptive sharpening, unsharp mask, de-noising hqdn3d).
- **Cấu hình & Đồng bộ Kho Kỹ Năng Toàn Cục Antigravity:**
  - Đồng bộ **99 kỹ năng** từ `.agent/skills/` sang thư mục cấu hình toàn cục Antigravity: `C:\Users\nguye\.gemini\config\skills/`.
  - Đồng bộ **175 kỹ năng** vào kho skills.sh toàn cục: `C:\Users\nguye\.agents\skills/`.
  - Tạo liên kết thư mục NTFS Junction: `c:\Users\nguye\Downloads\Agency_Designer_skill\.agents` <<===>> `.agent`.
  - Tạo tệp cấu hình [`.agent/skills.json`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills.json) khai báo danh mục các nhóm vai trò cho Antigravity JSON loader.
- **Phạm vi tác động (Blast Radius):**
  - Cấp độ an toàn: **Cô lập tuyệt đối (Zero side-effects)**.
  - Không thay đổi mã nguồn các skill hiện có trong `.agent/skills/`.
  - Tương thích 100% với toàn bộ IDE (Antigravity IDE, Cursor, Claude Code, OpenAI Codex).

---

## 🟡 PROMPT [N-1] — LIỀN KỀ TRƯỚC (19/10/2026 · 00:59:30)
**Nội dung yêu cầu:** Kiểm toán toàn bộ hệ thống skill, chạy test kiểm tra đạt đủ yêu cầu cho Designer Đồ họa Agency, viết tài liệu README hoàn chỉnh và đẩy toàn bộ lên GitHub.

### 1. Phân tích CodeGraph & AST Blast Radius:
- **Tập tin tạo mới:**
  - `.agent/.bangiao/visual-dna.json`: Khóa Seed DNA, token màu CMYK, Rich Black, Mascot Specs, SVG `<defs>`.
  - `.agent/.bangiao/ke-hoach.md`: Kế hoạch kết hợp BA + Engineering + Designer.
  - `.agent/.bangiao/thay-doi.md`: Cửa sổ trượt ghi nhận thay đổi AST.
  - `.agent/.bangiao/danh-gia.md`: Đánh giá QA/QC & hiệu năng.
  - `.agent/.bangiao/ket-qua-test.md`: Biên bản nghiệm thu Acceptance Criteria.
  - `README.md`: Bản tài liệu kiến trúc kỹ thuật cấp cao và hướng dẫn vận hành toàn diện.
- **Phạm vi tác động:** Bảo lưu 100% docstring và frontmatter YAML.

---

## ⚪ PROMPT [N-2] — QUÁ KHỨ (19/10/2026 · 00:20:00)
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
- **Ký hiệu AST bổ sung:** 6 core skills mở rộng chuyên biệt cho Agency sáng tạo.
