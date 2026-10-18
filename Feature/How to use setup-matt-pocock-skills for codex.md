# 🚀 How to Install, Configure and Use Matt Pocock Engineering Skills for OpenAI Codex CLI

## 1. Overview & Pure Autonomous Architecture

**Matt Pocock's Engineering Skills** (`mattpocock/skills`) is a suite of 38 battle-tested, prompt-driven skills designed for modern AI coding agents.

### Pure Zero-Junction Architecture
Unlike legacy setups that required polluting the workspace root with duplicate folders or 75 symlink junctions (`.agents`, `.codex`), the modern **OpenAI Codex CLI** operates via an **Autonomous Reasoning & Intent Routing Engine**:
- **Zero Root Pollution:** The workspace root remains clean (only `.agent/` and `.codegraph/`).
- **Autonomous Prompt Decomposition:** When a client provides any prompt (in natural language, Vietnamese or English), Codex's reasoning loop analyzes the intent, consults the Fast Dispatch Table in `.agent/CODEX.md`, and dynamically activates only the relevant `SKILL.md` in `.agent/skills/Engineering/<SkillName>/SKILL.md`.
- **Zero-Waste Token Economics:** Avoids loading unused skills into context, preserving 97.6% of context tokens.

### Codex CLI Autonomous Execution Flow
```
┌────────────────────────────────────────────────────────┐
│                   OpenAI Codex CLI                     │
│    (gpt-5-codex / codex-1 / o3-mini / gpt-4o)          │
└───────────────────────────┬────────────────────────────┘
                            │
               Receives Natural Prompt
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│  Layer 1: Central Router (.agent/CODEX.md)             │
│  Autonomous Reasoning Engine:                          │
│  • Extract Domain (Design / TDD / Review / Bug / Arch) │
│  • Match against Fast Dispatch Table (75 Skills)       │
└───────────────────────────┬────────────────────────────┘
                            │
            Loads ONLY Target Skill (Zero-Waste)
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│ Canonical Skill Source:                                │
│ .agent/skills/Engineering/<SkillName>/SKILL.md         │
└───────────────────────────┬────────────────────────────┘
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│ Project Infrastructure:                                │
│ ├── Local Tracker (.scratch/<feature>/)                │
│ ├── Triage Vocabulary (.agent/docs/agents/labels.md)   │
│ └── Domain Docs (GLOSSARY.md + docs/adr/)              │
└────────────────────────────────────────────────────────┘
```

---

## 2. How to Download & Setup (Cách tải & Cấu trúc)

### 2.1 Canonical Directory Placement
All engineering skills are housed permanently in:
```
.agent/skills/Engineering/<skill-name>/
```
Total: 38 Engineering skills (alongside 17 Designer, 9 UX.UI, 5 BA, 2 QC, and 4 QA skills, totaling 75 skills).

### 2.2 Download & Update Methods
- **Via npm/npx:**
  ```bash
  npx skills add mattpocock/skills
  ```
  Move downloaded skills into `.agent/skills/Engineering/`.
- **Via Git Clone:**
  Clone `https://github.com/mattpocock/skills.git` and place the contents of `skills/` into `.agent/skills/Engineering/`.

---

## 3. Autonomous Usage for AI Agents (Không cần gõ @skill)

You do **NOT** need to remember or type `@skill-name`. The agent's thinking algorithm automatically detects your intent from natural conversation:

### 3.1 Prompt Matching Examples

| Client Prompt (Natural Language) | Internal Reasoning | Activated Skill |
|:---|:---|:---|
| *"Tôi muốn xây dựng tính năng giỏ hàng, hãy viết test trước bằng pytest"* | Phân tích: Test-First, TDD | `.agent/skills/Engineering/tdd/SKILL.md` |
| *"Review lại toàn bộ code commit vừa rồi xem có chuẩn coding standard và đúng spec không"* | Phân tích: Dual-axis review | `.agent/skills/Engineering/code-review/SKILL.md` |
| *"Tại sao khi render PDF ở độ phân giải 300 DPI thì ứng dụng bị crash bộ nhớ?"* | Phân tích: Bug diagnosis | `.agent/skills/Engineering/diagnosing-bugs/SKILL.md` |
| *"Tôi có ý tưởng làm kiến trúc micro-frontend, hãy phản biện và chỉ ra các rủi ro"* | Phân tích: Socratic grilling | `.agent/skills/Engineering/grill-me/SKILL.md` |
| *"Tạo tài liệu đặc tả và chia nhỏ thành các ticket có dependency rõ ràng"* | Phân tích: Ticket breakdown | `.agent/skills/Engineering/to-tickets/SKILL.md` |
| *"Cấu hình issue tracker và domain docs ban đầu cho dự án"* | Phân tích: Repo engineering bootstrap | `.agent/skills/Engineering/setup-matt-pocock-skills/SKILL.md` |

---

## 4. Multi-Phase End-to-End Workflow

```
 ┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
 │ 1. Grilling  │ ──▶ │ 2. Tickets   │ ──▶ │ 3. TDD Loop  │ ──▶ │ 4. Review    │
 │ (grill-me)   │     │ (to-tickets) │     │ (tdd)        │     │ (code-review)│
 └──────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
```

1. **Grill & Refine Intent:** Client gives a high-level goal. Codex probes unstated assumptions and records decisions in `docs/adr/`.
2. **Decompose to Tickets:** Codex breaks the plan into tracer-bullet tickets in `.scratch/<feature>/ticket-*.md`.
3. **Implement via TDD:** Codex writes failing tests first (Red), implements minimal code (Green), and refactors.
4. **Dual-Axis Code Review:** Codex spawns subagents to evaluate both Standards and Spec Compliance side-by-side.

---

## 5. Model Coverage & Codex Optimizations

All Codex-supported models seamlessly utilize this autonomous reasoning routing:
- **`gpt-5-codex` / `codex-1`:** Fully autonomous multi-subagent delegation.
- **`o3-mini`:** Deep reasoning for hard bug diagnosis and adversarial grilling.
- **`gpt-4o`:** High-speed synthesis for ticket decomposition and spec writing.
- **`gpt-4.5`:** Flawless Vietnamese diacritic retention without glyph clipping.
- **`gpt-6.1-sol`:** Strict deterministic adherence to design constraints and Anti-AI rules.
