# 🌌 How to Use Matt Pocock Engineering Skills in Google Antigravity IDE

## 1. Overview & Clean Workspace Architecture

In **Google Antigravity IDE**, the workspace is kept completely clean without requiring temporary junction folders (`.agents/skills/` or `.codex/skills/`).

Instead, Antigravity loads the central orchestrator [`.agent/AGENTS.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/AGENTS.md) and routes user prompts through its **Autonomous Reasoning & Intent Routing Engine**:
- **75 Skills in Canonical Hierarchy:** Stored permanently under [`.agent/skills/<Role>/<SkillName>/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills).
- **Prompt-Driven Intelligence:** The user simply prompts what they need in Vietnamese or English. Antigravity's thinking algorithm scores the request against the Fast Dispatch Table and opens the exact skill.
- **Zero-Waste Token Economics:** Keeps the context window minimal and clean by activating only 1-2 skills per task.

---

## 2. Autonomous Prompt Routing in Antigravity

You do not need to type `@skill-name`. Natural language triggers the appropriate skill workflow:

| Bạn yêu cầu (Tiếng Việt hoặc English) | Thuật toán suy nghĩ của AI | Skill được kích hoạt |
|:---|:---|:---|
| *"Viết test trước rồi code hàm tính tỷ lệ co giãn cho ảnh 9:16"* | Intent: Test-Driven Development | [`.agent/skills/Engineering/tdd/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills/Engineering/tdd/SKILL.md) |
| *"Kiểm tra code nhánh này xem có vi phạm quy chuẩn thiết kế deep module không"* | Intent: Code Review & Standards | [`.agent/skills/Engineering/code-review/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills/Engineering/code-review/SKILL.md) |
| *"Debug lỗi memory leak khi export video hàng loạt bằng Remotion"* | Intent: Systematic Bug Diagnosis | [`.agent/skills/Engineering/diagnosing-bugs/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills/Engineering/diagnosing-bugs/SKILL.md) |
| *"Phản biện giúp tôi quyết định kiến trúc state management này và viết ADR"* | Intent: Socratic Grilling with Docs | [`.agent/skills/Engineering/grill-with-docs/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills/Engineering/grill-with-docs/SKILL.md) |
| *"Tạo các ticket việc nhỏ từ tài liệu đặc tả để chuẩn bị sprint"* | Intent: Ticket Decomposition | [`.agent/skills/Engineering/to-tickets/SKILL.md`](file:///c:/Users/nguye/Downloads/Agency_Designer_skill/.agent/skills/Engineering/to-tickets/SKILL.md) |

---

## 3. Integration with Antigravity Native Capabilities

1. **Reactive Wakeup:** When running TDD test suites with `run_command`, Antigravity runs the tests in the background and reactively wakes up upon test completion.
2. **CodeGraph MCP:** When analyzing codebase architecture or bug blast radius, Antigravity uses `codegraph_explore` to inspect callers and dependencies in 1 round trip.
3. **Artifact Delivery (`.bangiao/`):** All finished milestones are recorded across the 4 steps in `.agent/.bangiao/`:
   - `ke-hoach.md`
   - `danh-gia.md`
   - `thay-doi.md`
   - `ket-qua-test.md`
