# 🔄 How to Execute Socratic Grilling & The 4-Step Continuous Bangiao Loop

## 1. Overview & Objectives

This document establishes the official operational protocol for AI Agents running under the **Agency Creative & Engineering AI Orchestrator**.

Whenever the coordinator (user) issues a prompt, the system executes two integrated phases:
1. **Phase A: Socratic Reverse-Grilling ("Hỏi Xoáy Vặn Ngược")**:
   - Instead of guessing or hallucinating ambiguous requirements, the agent invokes skills from **Matt Pocock** (`grill-me`, `grilling`, `grill-with-docs`) and **Business Analysis** (`interview-me`, `ask-questions-if-underspecified`) to interrogate the coordinator, surface unstated trade-offs, and isolate the exact 1-2 skills needed.
2. **Phase B: Continuous 4-Step Bangiao Lifecycle (`.agent/.bangiao/`)**:
   - `ke-hoach.md`: Synthesizes BA specifications, Engineering architecture (ADRs), and Designer token systems.
   - `thay-doi.md`: Tracks CodeGraph AST modifications using a **Rolling 3-Prompt Window** (Prompt N, N-1, N-2).
   - `danh-gia.md`: Evaluates performance, token efficiency, anti-AI rules, and QA/QC quality gates.
   - `ket-qua-test.md`: BA acceptance verification comparing actual results against `ke-hoach.md` with 100% test pass.

---

## 2. Phase A: Socratic Reverse-Grilling Protocol

### When to Trigger:
- When a prompt is ambiguous, underspecified, or lacks critical parameters (e.g. dimensions, color profiles, deadlines, constraints).
- Before committing to significant architectural, refactoring, or design decisions.

### Skills Applied:
- `Engineering/grill-me`: Relentless technical inquiry challenging performance, edge cases, and scalability.
- `Engineering/grilling`: Adversarial questioning to stress-test architecture decisions.
- `Engineering/grill-with-docs`: Simultaneously conducts the interview while outputting ADRs in `docs/adr/` and glossary terms in `GLOSSARY.md`.
- `BA/ask-questions-if-underspecified`: Presents 1-3 targeted, concise multiple-choice questions.
- `BA/interview-me`: Explores business domain intent and target audience.

---

## 3. Phase B: The 4-Step Continuous Bangiao Lifecycle

```
 ┌────────────────────────────────────────────────────────┐
 │ BƯỚC 1: KẾ HOẠCH (ke-hoach.md)                         │
 │ Kết hợp: BA (Brief/AC) + Engineering (ADR) + Designer  │
 └───────────────────────────┬────────────────────────────┘
                             │
                             ▼
 ┌────────────────────────────────────────────────────────┐
 │ BƯỚC 2: THAY ĐỔI & CODEGRAPH (thay-doi.md)             │
 │ Cửa sổ trượt 3 Prompt gần nhất (Prompt N, N-1, N-2)   │
 └───────────────────────────┬────────────────────────────┘
                             │
                             ▼
 ┌────────────────────────────────────────────────────────┐
 │ BƯỚC 3: ĐÁNH GIÁ (danh-gia.md)                         │
 │ Kiểm toán: QA (Hiệu năng/Token) + QC (Quy chuẩn/Anti-AI)│
 └───────────────────────────┬────────────────────────────┘
                             │
                             ▼
 ┌────────────────────────────────────────────────────────┐
 │ BƯỚC 4: KẾT QUẢ CUỐI (ket-qua-test.md)                 │
 │ BA đối chiếu Acceptance Criteria so với Kế hoạch ban đầu│
 └────────────────────────────────────────────────────────┘
```

### The 3-Prompt Rolling Changelog Mechanism (`thay-doi.md`):
- **Current Prompt [N]:** Documents the most recent modifications, files changed, and CodeGraph AST blast radius.
- **Previous Prompt [N-1]:** Moves down to the second position.
- **Oldest Tracked Prompt [N-2]:** Moves down to the third position.
- **Prompts [N-3 and older]:** Automatically roll off the sliding window to maintain document compactness and readability.

---

## 4. Multi-Model Enforcement Across Codex CLI
All OpenAI Codex models adhere strictly to this protocol:
- **`gpt-5-codex` / `codex-1`:** Autonomous parallel subagents execution.
- **`o3-mini`:** Deep deductive reasoning for Socratic grilling.
- **`gpt-4o`:** Rapid document synchronization and Markdown synthesis.
- **`gpt-4.5`:** Flawless Vietnamese diacritics retention.
- **`gpt-6.1-sol`:** Strict anti-AI design rule enforcement.
