# 📋 KẾ HOẠCH BÀN GIAO TOÀN DIỆN (ke-hoach.md)
**Dự án:** Agency Creative & Engineering AI Orchestrator  
**Phiên bản:** 1.0.0 · Production Ready  
**Ngày lập:** 19/10/2026 · 00:59:00 (GMT+7)  
**Tài liệu điều phối trung tâm:** [`.agent/AGENTS.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/AGENTS.md)  

---

## 1. TỔNG QUAN YÊU CẦU NGHIỆP VỤ (BA BRIEF & ACCEPTANCE CRITERIA)

### 1.1. Yêu cầu của người điều phối (User Request):
1. **Kiểm toán toàn diện hệ thống 81 Skills**: Đảm bảo phân loại đúng 6 vai trò (`Designer`, `UX.UI`, `Engineering`, `BA`, `QC`, `QA`), 100% tệp `SKILL.md` có đầy đủ YAML frontmatter hợp lệ (`name`, `description`).
2. **Kiểm tra mức độ đáp ứng năng lực Đồ họa & Sáng tạo Agency (Graphic Designer Readiness)**:
   - Kiến trúc chiến dịch 360 IMC (`imc-campaign-architect`) phân tách 3 giai đoạn (Tease, Launch, Sustain) và Ma trận vật phẩm BOM 5 Production Packs.
   - Bộ Gen Họa Tiết Vector & Pattern liền mạch (`brand-motif-engine`) với thư viện `<defs>`/`<symbol>` chống trôi dạt thị giác.
   - Thiết kế vật phẩm sự kiện & Artcraft (`event-merch-and-artcraft`): Vé VIP/GA có đường cấn răng cưa `DIE_CUT`, ép kim hologram, Lightstick phát quang, Vòng tay RFID, Sơ đồ điểm ảnh màn hình LED đa tỷ lệ (32:9, 9:16, 4:1).
   - Thiết kế Linh vật & IP Nhân vật (`mascot-sheet`): Bảng xoay 4 hướng trực giao (Turnaround 0°, 45°, 90°, 180°), Ma trận 6 sắc thái cảm xúc, Thư viện tư thế hành động cùng đạo cụ.
   - Cầu nối Prepress & ExtendScript Adobe Illustrator (`adobe-prepress-bridge`): Script `.jsx` tự động hóa artboard, chuẩn hóa 7 lớp layer in ấn, chuẩn màu CMYK ISO Coated v2/FOGRA39, Rich Black (`40/30/30/100`) và Pure Black (`0/0/0/100`).
   - Thiết kế Web Trải nghiệm Lễ hội phi SaaS (`experiential-festival-web`): Cấm card/bảng SaaS cứng nhắc, kích hoạt Hero kinetic typography, GSAP scrollytelling, và bộ chọn vé 3D tương tác.
   - Bộ quy chuẩn thiết kế UI/UX 67 phong cách & 96 bảng màu (`ui-ux-pro-max`), Lưới đồ họa Thụy Sĩ (`canvas-design`), Vùng an toàn mạng xã hội 4:5 và 9:16 (`social-media-content`).
3. **Thực thi bộ kiểm thử tự động (Automated Test Suite)**: Phủ 100% các tiêu chí hệ thống, AST, cấu trúc tệp, biên dịch Python, phân tích cú pháp JSON, và kiểm tra tính toàn vẹn Fast Dispatch.
4. **Khởi tạo và đồng bộ Quy chuẩn Bàn giao 4 Bước & Visual DNA**:
   - `visual-dna.json`: Single Source of Truth cho token màu, cmyk, font, mascot, và motif vector.
   - `ke-hoach.md`: Kế hoạch chi tiết kết hợp BA + Engineering + Design.
   - `thay-doi.md`: Cửa sổ trượt 3 Prompt ghi nhận AST thay đổi qua CodeGraph.
   - `danh-gia.md`: Đánh giá hiệu năng, chất lượng, WCAG và an toàn tiếng Việt.
   - `ket-qua-test.md`: Biên bản nghiệm thu Acceptance Criteria đạt 100% PASS.
5. **Biên soạn README.md toàn diện**: Mô tả chi tiết cấu trúc kiến trúc, thuật toán Zero-Waste Router, chu trình Bàn giao 4 bước, và hướng dẫn sử dụng đa nền tảng (OpenAI Codex, Claude Code, Antigravity IDE, Cursor, Windsurf, Gemini CLI).
6. **Khởi tạo Git và Đẩy lên Repository**: Đẩy toàn bộ mã nguồn lên [GitHub: NguyenBaAnhKhoi/Agency_Designer_skill](https://github.com/NguyenBaAnhKhoi/Agency_Designer_skill).

---

## 2. QUYẾT ĐỊNH KIẾN TRÚC KỸ THUẬT (ENGINEERING ADRs)

| Mã ADR | Quyết định Kiến trúc | Lý do & Hệ quả |
|:---|:---|:---|
| **ADR-01** | Zero-Waste Progressive Disclosure | Chỉ nạp Layer 1 Router (`AGENTS.md`), chỉ mở Layer 2 (`SKILL.md`) khi khớp trigger, tiết kiệm 80%-95% context token. |
| **ADR-02** | Visual DNA Single Source of Truth (`visual-dna.json`) | Mô phỏng cơ chế IP-Adapter & Seed Locking của ComfyUI, đảm bảo toàn bộ vật phẩm phái sinh không bị lệch màu hay thay đổi style. |
| **ADR-03** | Multi-Pack Campaign Decomposition | Tuyệt đối cấm tạo file overview sơ sài; phân rã thành 5 gói sản xuất chuyên sâu thực hiện tuần tự. |
| **ADR-04** | Dual-Layer Prepress Bridge (.jsx + SVG) | Kết hợp mã ExtendScript chạy thẳng trong Adobe Illustrator với SVG chuẩn XML để nhà in xuất phim/kẽm chính xác tuyệt đối. |
| **ADR-05** | Python PyTest & AST Validation Suite | Viết kịch bản kiểm thử độc lập kiểm tra cú pháp, schema, tính toàn vẹn registry và khả năng phủ của Fast Dispatch. |

---

## 3. THÔNG SỐ TOKEN THỊ GIÁC & QUY CHUẨN DESIGNER (DESIGN SPECS)

- **Chuẩn màu CMYK**: ISO Coated v2 (ECI) / FOGRA39.
  - Rich Black cho tiêu đề ≥36pt: `C:40 M:30 Y:30 K:100` (`#0A0A0C`).
  - Pure Black cho văn bản <14pt: `C:0 M:0 Y:0 K:100` (`#000000`, Overprint bật).
  - Vạch bế Die-cut: `C:0 M:100 Y:0 K:0` (Magenta 100%, Non-printing, 0.5pt).
  - Vạch cấn gập Crease: `C:100 M:0 Y:0 K:0` (Cyan 100%, nét đứt 2pt/2pt).
- **Hệ Thống Phông chữ & Tiếng Việt**:
  - Display: Cabinet Grotesk / Syne / Clash Display (Bold 900, -0.04em).
  - Body: Plus Jakarta Sans / Inter Display (100% chuẩn dấu Unicode tiếng Việt dựng sẵn).
- **Vùng An toàn & Tỷ lệ Mạng Xã hội**:
  - Feed: 1080 × 1350 px (Tỷ lệ 4:5, căn trung tâm khung vuông 1080 × 1080).
  - Story / Reel / TikTok: 1080 × 1920 px (Tỷ lệ 9:16, chừa lề trên 250px và lề dưới 350px cho UI overlay).
