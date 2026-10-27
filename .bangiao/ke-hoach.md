# 📋 KẾ HOẠCH BÀN GIAO TOÀN DIỆN (ke-hoach.md)
**Dự án:** Agency Creative & Engineering AI Orchestrator  
**Phiên bản:** 1.1.0 · Video Enhancement & Antigravity Global Skill Store Sync  
**Ngày cập nhật:** 28/10/2026 · 01:14:00 (GMT+7)  
**Tài liệu điều phối trung tâm:** [`.agent/AGENTS.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/AGENTS.md)  

---

## 1. TỔNG QUAN YÊU CẦU NGHIỆP VỤ (BA BRIEF & ACCEPTANCE CRITERIA)

### 1.1. Yêu cầu của người điều phối (User Request):
1. **Tìm kiếm các skill tối ưu cho việc làm nét / tăng chất lượng video và Adobe After Effects** (`/find-skills`):
   - Tìm kiếm bộ skill chuyên dụng về xử lý chuyển động, hiệu ứng đồ họa và tối ưu hóa Adobe After Effects.
   - Tìm kiếm công nghệ AI Upscaling, làm nét khung hình (Super Resolution), khử nhiễu (Denoise), phục chế video nén/cũ (Topaz Video AI, FFmpeg Cas/Unsharp).
   - Cung cấp giải pháp kỹ thuật cụ thể trực tiếp trên After Effects (Detail-preserving Upscale, Unsharp Mask, Render Queue/AME).
2. **Nạp toàn bộ hệ thống skill của mục `.agent` vào kho skill của Antigravity**:
   - Quét toàn bộ 96+ kỹ năng phân loại theo 6 nhóm vai trò (`Designer`, `UX.UI`, `Engineering`, `BA`, `QC`, `QA`) nằm trong `.agent/skills/`.
   - Nạp vào kho lưu trữ cấu hình toàn cục Antigravity (`C:\Users\nguye\.gemini\config\skills/` và `C:\Users\nguye\.agents\skills/`).
   - Thiết lập liên kết hệ thống `.agents` tại thư mục gốc workspace thông qua NTFS Junction và file cấu hình `skills.json` để kích hoạt nhận diện tự động trên toàn hệ sinh thái Antigravity IDE.

### 1.2. Tiêu chí nghiệm thu (Acceptance Criteria - AC):
- [x] **AC-01 (Discovery)**: Tìm và chọn lọc thành công các skill có lượt cài đặt cao, uy tín từ cộng đồng về After Effects và Video Upscale.
- [x] **AC-02 (Installation)**: Cài đặt và tích hợp trực tiếp các skill: `after-effects` (iart-ai, 2.9K installs), `topaz-video-enhancement` (calesthio, Topaz Labs models), và `ffmpeg` (digitalsamba, 11.8K installs).
- [x] **AC-03 (Global Ingestion)**: 100% skill từ `.agent/skills` (99 skills) được đưa vào `~/.gemini/config/skills` và `~/.agents/skills` với 0 lỗi xung đột tên thư mục hay frontmatter YAML.
- [x] **AC-04 (Workspace Junction)**: Khởi tạo junction `.agents` trỏ về `.agent` và bổ sung `.agent/skills.json` khai báo đa tầng sub-paths.

---

## 2. QUYẾT ĐỊNH KIẾN TRÚC KỸ THUẬT (ENGINEERING ADRs)

| Mã ADR | Quyết định Kiến trúc | Lý do & Hệ quả |
|:---|:---|:---|
| **ADR-06** | Dual-Store Skill Registration (`.gemini/config/skills` + `~/.agents/skills`) | Đảm bảo tương thích kép: Antigravity IDE đọc trực tiếp từ `.gemini/config/skills`, đồng thời `npx skills` và CLI engine đọc từ `~/.agents/skills`. |
| **ADR-07** | Workspace NTFS Directory Junction (`.agents` -> `.agent`) | Giải quyết triệt để sự khác biệt quy ước đặt tên thư mục giữa Antigravity chuẩn (`.agents`) và Agency Designer repo (`.agent`) mà không nhân bản dung lượng ổ đĩa. |
| **ADR-08** | Sub-skill Flattening for Antigravity Loader | Antigravity engine quét 1 cấp độ thư mục con trong `skills/`. Các sub-skill lồng ghép (`gsap-plugins`, `remotion-render`, `figma-use`,...) được phẳng hóa ra thư mục cấp 1 độc lập. |
| **ADR-09** | Triple Video Enhancement Pipeline | Kết hợp 3 tầng công nghệ xử lý: Tầng 1 (Adobe After Effects native + ExtendScript), Tầng 2 (Topaz Video AI models: Proteus, Iris, Gaia), Tầng 3 (FFmpeg open-source: CAS, unsharp, Lanczos). |
