# 🕸️ How to Install, Configure and Use CodeGraph for OpenAI Codex CLI

## 1. Overview & Architecture

**CodeGraph** is a high-performance code intelligence and knowledge graph system designed specifically for AI coding agents. Instead of forcing AI agents to run expensive, blind, multi-round search/grep/read loops, CodeGraph builds a rich SQLite-backed symbol and dependency graph of the entire repository.

When an AI agent (such as OpenAI Codex CLI) needs to understand a function, refactor a module, or trace a bug, CodeGraph provides:
- **Verbatim Source Code in One Round-Trip:** Returns exact line-numbered source code of relevant symbols and their direct caller/callee paths.
- **Blast Radius & Impact Analysis:** Maps all dependent callers and test files across the repository before editing.
- **Zero-Waste Token Economics:** Eliminates redundant file scans, cutting context consumption by **80%–95%**.
- **Dynamic Call Graph Resolution:** Traces method invocations and dynamic hops that regex/grep cannot follow.

### Architecture Diagram
```
┌────────────────────────────────────────────────────────┐
│                   OpenAI Codex CLI                     │
│               (Agent Reasoning Engine)                 │
└───────────────────────────┬────────────────────────────┘
                            │
                   Model Context Protocol
                        (MCP / stdio)
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│                   CodeGraph Server                     │
│               (Background MCP Daemon)                  │
└───────────────────────────┬────────────────────────────┘
                            │
               Fast AST & Relationship Queries
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│       Local Knowledge Graph (.codegraph/)              │
│ ├── codegraph.db (SQLite with Write-Ahead Logging WAL) │
│ ├── Symbol Nodes (functions, classes, interfaces)      │
│ ├── Relationship Edges (calls, imports, heritage)      │
│ └── File Hashes (Incremental zero-latency sync)        │
└────────────────────────────────────────────────────────┘
```

---

## 2. How to Download & Install (Cách tải & Cài đặt)

### Prerequisites
- **Node.js** ≥ 18.0.0 or bun/deno runtime.
- **OpenAI Codex CLI** installed on the workstation.
- Operating System: Windows (PowerShell), macOS, or Linux.

### Installation Steps

#### Step 1: Install CodeGraph CLI Globally
Install the CodeGraph package globally via npm:
```bash
npm install -g @codegraph/cli
# OR using yarn/pnpm:
pnpm add -g @codegraph/cli
```

Verify installation:
```bash
codegraph --version
```

#### Step 2: Initialize CodeGraph in the Project Directory
Navigate to your repository and initialize the graph index:
```bash
cd c:\Users\nguye\Downloads\Agency_Designer_skill
codegraph init .
```
This parses all source files (TypeScript, JavaScript, Python, YAML, JSON), builds the AST symbols, and generates `.codegraph/codegraph.db`.

#### Step 3: Install MCP Server into Codex CLI
CodeGraph features an automated MCP installer for major AI agents:
```bash
codegraph install --agent codex
```
This automatically registers the CodeGraph MCP server inside Codex CLI's MCP configuration.

---

## 3. Configuration for OpenAI Codex CLI (Cách Cấu hình)

### 3.1 Manual MCP Configuration
If configuring Codex CLI manually, add the CodeGraph server to your Codex MCP configuration file (e.g. `~/.codex/config.json` or project-level `agents/openai.yaml`):

```json
{
  "mcpServers": {
    "codegraph": {
      "command": "codegraph",
      "args": ["daemon", "--stdio"],
      "env": {
        "CODEGRAPH_PROJECT_PATH": "c:\\Users\\nguye\\Downloads\\Agency_Designer_skill"
      }
    }
  }
}
```

### 3.2 Codex Rule Injection (`.agent/CODEX.md`)
To enforce that the AI agent reaches for CodeGraph before falling back to blind searches, ensure this mandatory rule is present in `.agent/CODEX.md` and `.agent/AGENTS.md`:

```markdown
<!-- CODEGRAPH_START -->
## CodeGraph

In repositories indexed by CodeGraph (a `.codegraph/` directory exists at the repo root), reach for it BEFORE grep/find or reading files when you need to understand or locate code:

- **MCP tool** (when available): `codegraph_explore` answers most code questions in one call — the relevant symbols' verbatim source plus the call paths between them, including dynamic-dispatch hops grep can't follow.
- **Shell** (always works): `codegraph explore "<symbol names or question>"` prints the same output.
- **Impact check**: `codegraph impact "<symbol>"` before refactoring to verify blast radius.
<!-- CODEGRAPH_END -->
```

---

## 4. How to Use for AI Agents (Cách sử dụng cho AI Agent)

### 4.1 Key CodeGraph Capabilities

| Capability | MCP Tool / CLI Command | Description | Token Efficiency |
|:---|:---|:---|:---:|
| **Area Exploration** | `codegraph_explore` / `codegraph explore` | Verbatim source of relevant symbols + call paths in 1 shot. | 🟢 **95% Savings** |
| **Blast Radius Analysis** | `codegraph impact <symbol>` | Lists all callers, tests, and dependents affected by a change. | 🟢 **90% Savings** |
| **Call Chain Tracing** | `codegraph callers` / `callees` | Traces callers upstream and callees downstream across files. | 🟢 **92% Savings** |
| **Symbol Inspection** | `codegraph node <symbol>` | Inspects one symbol's declaration and incoming/outgoing edges. | 🟢 **98% Savings** |
| **Index Synchronization** | `codegraph sync` | Incrementally updates database with modified files since last index. | ⚡ **<500ms** |

---

### 4.2 Practical Agent Workflows & Prompt Examples

#### Workflow 1: Exploring Architecture Before Editing
```
User Prompt:
"Dùng codegraph khám phá cách module typefully trong social-media-content hoạt động và gọi API nào."

Codex Agent Action:
Calls MCP tool:
codegraph_explore(query="typefully apiRequest cmdSetup")

Codex Receives:
- Exact line-numbered source of cmdSetup, apiRequest, and writeConfig.
- Call path: cmdSetup -> parseArgs -> writeConfig.
- Blast radius: 2 callers in typefully.js.
- Zero need to read the entire 2,500-line file!
```

#### Workflow 2: Safe Refactoring with Impact Analysis
```
User Prompt:
"Tôi muốn sửa hàm `render_preview` trong photoshop-bridge. Hãy kiểm tra blast radius xem những đâu bị ảnh hưởng."

Codex Agent Action:
Runs shell command:
codegraph impact "render_preview"

Codex Receives:
- Affected callers: 4 functions across 2 files.
- Affected tests: tests/test_photoshop_bridge.py.
- Recommended test run command: pytest tests/test_photoshop_bridge.py.
```

#### Workflow 3: Investigating Hard Bugs with Call Paths
```
User Prompt:
"Hàm `createSemanticTokens` bị lỗi undefined khi tạo variable collection trong Figma. Hãy điều tra nguyên nhân."

Codex Agent Action:
Calls MCP tool:
codegraph_explore(query="createSemanticTokens createVariableCollection")

Codex Traces:
The dynamic assignment chain from `createVariableCollection.js` to `createSemanticTokens.js`, pinpointing missing return payload without trial-and-error.
```

---

## 5. Maintenance & Index Management

### Checking Index Health
Run `codegraph status` in PowerShell:
```bash
codegraph status
```
Output:
```
CodeGraph Status
Project: C:\Users\nguye\Downloads\Agency_Designer_skill
Index Statistics:
  Files:     160
  Nodes:     2,914
  Edges:     5,169
  DB Size:   15.39 MB
  Backend:   node:sqlite - built-in (full WAL)
```

### Syncing After File Changes
Whenever new skills or source files are added:
```bash
codegraph sync
```

### Unlocking Database if Daemon Crashes
If a crash or unexpected kill leaves a lock file:
```bash
codegraph unlock
# OR manually delete the lock file:
Remove-Item -Path .codegraph\codegraph.lock -Force -ErrorAction SilentlyContinue
```

---

## 6. Summary Comparison: CodeGraph vs Traditional Grep

| Feature | Traditional Grep / Find | CodeGraph for Codex |
|:---|:---:|:---:|
| **Discovery Mechanism** | String pattern matching | AST Symbol Parsing & Semantic Graph |
| **Token Cost per Query** | 10,000 – 40,000 tokens | 1,000 – 2,500 tokens |
| **Call Path Detection** | ❌ Cannot trace hops | ✅ Full upstream & downstream trails |
| **Refactoring Safety** | ❌ High risk of missed callers | ✅ Exhaustive blast radius analysis |
| **Cross-Language Support** | Plain text only | TS, JS, Python, YAML, JSON |
