# 🛠️ How to Connect Artcraft (PhotoCraft) MCP to OpenAI Codex CLI for AI Agents

## 1. Overview & Architecture

**Artcraft (PhotoCraft)** is a professional desktop raster/vector graphic editor with a native **Model Context Protocol (MCP)** interface. Connecting Artcraft to **OpenAI Codex CLI** allows AI agents to pilot the image editor directly—automating canvas creation, layer composition, batch slicing, filter adjustments, and rendering visual previews in real-time.

### Connection Architecture
```
┌──────────────────┐               ┌───────────────────────────┐               ┌─────────────────────────┐
│ OpenAI Codex CLI │ ── stdio ───▶ │ photocraft-cli.exe (MCP)  │ ── Bridge ──▶ │ Artcraft Desktop Window │
│ (Agent Brain)    │ ◀── JSON-RPC─ │ (Local Server Process)    │ (Port 8089)   │ (Canvas & GPU Engine)   │
└──────────────────┘               └───────────────────────────┘               └─────────────────────────┘
```

- **Client:** OpenAI Codex CLI (`codex`)
- **Server Binary:** `C:\Program Files\PhotoCraft\photocraft-cli.exe`
- **Protocol:** Model Context Protocol (stdio transport)
- **Local Bridge Port:** `127.0.0.1:8089` (WebSocket communication with the active GUI window)
- **Control Token:** `C:\Users\nguye\.photocraft-token`

---

## 2. Configuration for Codex CLI

Codex CLI manages its MCP servers in the global configuration file located at `~/.codex/config.toml` (or inside your workspace at `.codex/config.toml`).

### Step 1: Open or Create `config.toml`
Open `C:\Users\nguye\.codex\config.toml` in your editor.

### Step 2: Add the `photocraft` MCP Server Block
Add the following configuration block to `~/.codex/config.toml`:

```toml
[mcp_servers.photocraft]
command = "C:\\Program Files\\PhotoCraft\\photocraft-cli.exe"
args = [
  "mcp",
  "--bridge", "127.0.0.1:8089",
  "--control-token-file", "C:\\Users\\nguye\\.photocraft-token",
  "--automation-read-root", "C:\\",
  "--automation-write-root", "C:\\"
]
```

> [!NOTE]
> - Double backslashes (`\\`) are required in TOML format for Windows file paths.
> - `--automation-read-root` and `--automation-write-root` define the allowed filesystem boundaries for file open/save operations.

---

## 3. Tool Catalog & Available MCP Capabilities (24 Tools)

Once connected, your Codex AI agent gains access to the following 24 granular design tools:

### 3.1 Document Lifecycle & File Management
| Tool Name | Parameters | Purpose |
|:---|:---|:---|
| `doc_new` | `width`, `height`, `dpi`, `color_mode`, `fill` | Creates a new canvas/document with exact dimensions and color space. |
| `doc_open` | `path` | Opens an existing `.pcraft`, `.psd`, `.png`, or `.jpg` project file. |
| `doc_save` | `path` | Saves the active document to native `.pcraft` or format specified by extension. |
| `doc_close` | `save_changes` | Closes the current active document tab. |
| `doc_inspect` | `include_layers`, `include_artboards` | Reads complete layer tree, masks, blend modes, opacity, and dimensions. |

### 3.2 Canvas & Layer Manipulation
| Tool Name | Parameters | Purpose |
|:---|:---|:---|
| `doc_place` | `path`, `x`, `y`, `scale`, `link` | Places an external raster/vector asset as a Smart Layer on canvas. |
| `doc_select` | `layer_id` or `bounds` | Selects specific layers or marquee regions. |
| `doc_export` | `path`, `format`, `quality`, `color_space` | Exports the full canvas (PNG, WebP, JPEG, TIFF). |
| `doc_export_layers` | `output_dir`, `selected_only`, `format` | Batch exports layers or asset slices into individual asset files. |
| `doc_import_data_sets` | `csv_path` | Imports variable datasets for automated template generation. |
| `doc_export_data_sets` | `output_dir`, `naming_template` | Renders and exports batch variations based on dataset records. |

### 3.3 Command Pipeline & Macro Execution
| Tool Name | Parameters | Purpose |
|:---|:---|:---|
| `command_list` | *(none)* | Queries the live dictionary of all internal filters, transforms, and adjustments. |
| `command_run` | `command_id`, `params` | Executes a single editing action (adds 1 history step to undo stack). |
| `command_batch` | `commands: [...]` | Executes an array of commands sequentially in a **single undo step**. |

### 3.4 Visual Inspection & UI Interaction (Bridge Mode)
| Tool Name | Parameters | Purpose |
|:---|:---|:---|
| `render_preview` | `max_width`, `max_height` | Generates a quick low-resolution preview image for LLM visual reasoning. |
| `ui_screenshot` | *(none)* | Captures a high-resolution screenshot of the editor workspace. |
| `ui_inspect` | *(none)* | Reads current viewport zoom, tool palette state, and active selection. |
| `ui_menu_invoke` | `menu_path` | Triggers native application menu actions (e.g. `Filter > Blur > Gaussian Blur`). |
| `ui_pointer` | `action`, `x`, `y` | Sends direct mouse pointer movements or clicks to the canvas. |

### 3.5 Live State Resources
Codex can stream the editor's live memory state via MCP resources:
- `photocraft://document` — Returns real-time JSON metadata of the open document.
- `photocraft://commands` — Returns the live list of supported filters, transforms, and tool IDs.

---

## 4. Verification & Testing

### Step 1: Launch Artcraft (PhotoCraft)
Start the Artcraft desktop application and make sure it is running on your machine.

### Step 2: Test in Codex CLI
Open PowerShell or Terminal and start Codex:
```bash
codex
```

Check MCP tool registration by typing:
```
/mcp
```
You should see `photocraft` listed with 24 available tools.

### Step 3: Run a Verification Prompt
Prompt Codex with an automated design task:
```text
Using photocraft MCP, please:
1. Create a new document: 1080x1080 px at 300 DPI named "social_post".
2. Fill the background with deep dark slate #0B0F19.
3. Call render_preview and show me the result.
```

Codex will:
1. Call `photocraft.doc_new(width=1080, height=1080, dpi=300)`.
2. Call `photocraft.command_run(command_id="fill", params={"color": "#0B0F19"})`.
3. Call `photocraft.render_preview()` to visually confirm the canvas.

---

## 5. Practical Agency Workflows with Codex + Artcraft

### Scenario A: Batch Social Media Resizing (Multi-Format Rollout)
```text
@creative-agency @photocraft
Take the master Key Visual at "C:\Assets\KV_Master.pcraft" and export:
- 1:1 Square (1080x1080) for Instagram Feed -> output/ig_feed.png
- 9:16 Story (1080x1920) for TikTok/Reels -> output/story.png
- 16:9 Banner (1920x1080) for YouTube Header -> output/yt_banner.png
Ensure safe margins and export preview for each.
```

### Scenario B: Automated Layer Slicing for UI/UX Handoff
```text
@photocraft Open "C:\Projects\MobileApp_Mockup.pcraft".
Inspect all layers, find the layer group "Icons_Export", and export each child layer as an individual 32-bit transparent PNG @2x into "C:\Projects\Exports\Icons".
```

---

## 6. Troubleshooting & Common Pitfalls

| Issue | Cause | Solution |
|:---|:---|:---|
| `Connection refused: 127.0.0.1:8089` | Artcraft desktop GUI is closed or bridge is offline. | Launch the Artcraft application before starting Codex CLI. |
| `Control token invalid or missing` | `~/.photocraft-token` does not match the active session. | Ensure the token file at `C:\Users\nguye\.photocraft-token` exists and has read permissions. |
| `Path outside automation root` | File path attempted is outside `--automation-read-root`. | Set `--automation-read-root` and `--automation-write-root` to `C:\\` or your project drive in `config.toml`. |
| `JSON-RPC timeout on large render` | Document has very large canvas size (e.g. 10000px). | Use `render_preview` with `max_width=1280` instead of full document exports during drafting. |
