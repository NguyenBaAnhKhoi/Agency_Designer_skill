# 🎨 How to Connect Adobe Creative Cloud MCP to OpenAI Codex CLI for AI Agents

## 1. Overview & Architecture

Connecting **Adobe Creative Cloud applications (Photoshop, Illustrator, InDesign, After Effects)** to **OpenAI Codex CLI** via the **Model Context Protocol (MCP)** gives your AI agent direct control over your professional design suite. 

Instead of manual layer creation and repetitive adjustments, the AI agent can autonomously:
- Create, inspect, and manipulate complex layer hierarchies.
- Apply non-destructive adjustment layers (Curves, HSL, Color Balance).
- Execute BatchPlay descriptors and ExtendScript routines.
- Automate Generative Fill, Content-Aware Scaling, and Object Selection.
- Export print-ready (CMYK 300 DPI) and web-optimized (Display P3 / sRGB) assets with exact bleeds and crop marks.

### Connection Architecture
```
┌──────────────────┐               ┌───────────────────────────┐               ┌─────────────────────────┐
│ OpenAI Codex CLI │ ── stdio ───▶ │ Adobe MCP Server          │ ── Socket ──▶ │ Adobe Desktop App       │
│ (Agent Brain)    │ ◀── JSON-RPC─ │ (Node.js / Python Bridge) │ (Port 49494)  │ (Photoshop/Illustrator) │
└──────────────────┘               └───────────────────────────┘               └─────────────────────────┘
```

---

## 2. The 3 MCP Connection Methods for Adobe

Depending on your agency workflow, you can choose one or combine multiple methods:

### Method 1: Local Photoshop UXP / Generator WebSocket Bridge (Recommended for Real-time GUI Work)
- Uses Photoshop’s native **Remote Connection (Generator/UXP Engine)** listening locally on port `49494` (or custom port).
- The MCP server connects to Photoshop via WebSocket and issues commands using Photoshop's high-speed **BatchPlay API**.
- You see the actions execute live on your screen in real time.

### Method 2: ExtendScript / JSX Native Scripting Bridge (Recommended for Bulk Prepress & Illustrator)
- Connects through Windows COM automation (`Photoshop.Application` / `Illustrator.Application`).
- Ideal for batch operations, vector tracing in Illustrator, and InDesign book/magazine layout pipelines.

### Method 3: Adobe Firefly & Photoshop Cloud APIs (Headless Mode)
- Connects via official Adobe Developer Console APIs using OAuth credentials.
- Works in headless server environments without requiring Adobe apps installed locally.

---

## 3. Step-by-Step Setup Guide (Method 1: Local Desktop Bridge)

### Step 1: Enable Remote Connections in Adobe Photoshop
1. Open **Adobe Photoshop** (version 2023, 2024, or newer).
2. Go to **Edit > Preferences > Plug-ins...** (or `Ctrl + K` then select *Plug-ins*).
3. Check the box: **"Enable Remote Connections"**.
4. In the **Service Name** field, leave it as default or enter `photoshop-mcp`.
5. Enter a **Password** (e.g. `agentpassword123`).
6. Click **OK** and restart Photoshop.

```
┌────────────────────────────────────────────────────────┐
│ Plug-ins Preferences                                   │
│ [x] Enable Generator                                   │
│ [x] Enable Remote Connections                          │
│     Service Name: [photoshop-mcp                     ] │
│     Password:     [••••••••••••                      ] │
└────────────────────────────────────────────────────────┘
```

---

### Step 2: Install the Adobe MCP Server Package
Open PowerShell and install the Photoshop MCP bridge:
```bash
npm install -g @modelcontextprotocol/server-photoshop
# OR if using an open-source community bridge:
npm install -g photoshop-mcp
```

Alternatively, you can run it on-demand via `npx` without global installation.

---

### Step 3: Configure Codex CLI (`config.toml`)
Open your Codex configuration file at `C:\Users\nguye\.codex\config.toml`:

```toml
[mcp_servers.adobe_photoshop]
command = "npx"
args = [
  "-y",
  "photoshop-mcp",
  "--host", "127.0.0.1",
  "--port", "49494",
  "--password", "agentpassword123"
]
env = { ADOBE_ENV = "production" }
```

If you are using an ExtendScript / COM bridge script:
```toml
[mcp_servers.adobe_extendscript]
command = "python"
args = [
  "C:\\Tools\\adobe-mcp\\bridge.py",
  "--app", "photoshop"
]
```

---

## 4. Available MCP Tools for the AI Agent

Once connected, your Codex AI agent can call the following Adobe automation tools:

| Tool Name | Parameters | Description |
|:---|:---|:---|
| `ps_document_create` | `width`, `height`, `resolution`, `colorMode` | Creates a new artboard or canvas with exact DPI and color profile (CMYK / RGB). |
| `ps_document_open` | `filePath` | Opens existing `.psd`, `.psb`, `.ai`, `.tiff`, or raw camera files. |
| `ps_layer_create` | `name`, `type`, `blendMode`, `opacity` | Creates raster layers, Smart Objects, text layers, or solid color fill layers. |
| `ps_layer_inspect` | `layerId` or `all` | Inspects layer bounds, effects (Drop Shadow, Stroke), masks, and visibility. |
| `ps_apply_adjustment` | `type`, `settings` | Adds non-destructive adjustment layers: Curves, Levels, Selective Color, HSL. |
| `ps_selection_make` | `type`, `bounds`, `feather` | Selects canvas regions (Rectangular, Elliptical, Subject Selection). |
| `ps_generative_fill` | `prompt`, `layerId`, `expandBounds` | Triggers Photoshop Generative Expand or Inpainting via Firefly engine. |
| `ps_batchplay_run` | `descriptorJSON` | Executes any native Photoshop ActionDescriptor directly for zero-limitation control. |
| `ps_export_asset` | `outputPath`, `format`, `quality`, `colorProfile` | Exports deliverables in PNG, WebP, JPEG, TIFF, or print-ready PDF with bleeds. |

---

## 5. Verification & Testing in Codex CLI

### Step 1: Launch Photoshop and Codex CLI
1. Ensure Adobe Photoshop is running with *Remote Connections* enabled.
2. Open PowerShell and start Codex CLI:
   ```bash
   codex
   ```

### Step 2: Verify MCP Tool Registration
In the Codex chat interface, type:
```
/mcp
```
Verify that `adobe_photoshop` appears in the active server list.

### Step 3: Run a Live Test Prompt
Test the live connection by commanding Codex:
```text
@adobe_photoshop Create a new document in Photoshop:
- Dimensions: 1920x1080 px at 300 DPI
- Name: "KV_Stage_Visual"
- Add a new text layer with font "Montserrat Bold", size 72pt, color #FFFFFF, centered, with text "AGENCY DESIGN SYSTEM".
- Add an adjustment layer Curves with slight S-curve contrast.
```

Watch Photoshop execute each step live on your screen!

---

## 6. Real-World Agency Production Workflows

### Scenario 1: Print-Ready Prepress Packaging
```text
@creative-agency @adobe_photoshop
I have an exhibition poster file at "C:\Projects\Poster_Master.psd".
Please:
1. Verify color mode is CMYK (FOGRA39 profile).
2. Ensure 3mm bleeding margins on all 4 edges.
3. Check that text layers have vector anti-aliasing preserved.
4. Export as print-ready PDF/X-1a:2001 with crop marks to "C:\Projects\Print\Poster_PrintReady.pdf".
```

### Scenario 2: Batch Social Adaptation with Smart Objects
```text
@adobe_photoshop Open "C:\Projects\Ad_Template.psd".
Replace the content of Smart Object "Hero_Image" with "C:\Assets\Product_01.png".
Update text layer "Discount_Label" to "SALE 50% OFF".
Export to "C:\Projects\Exports\Ad_Variant_01.jpg" at 85% quality.
Repeat for Product_02 and Product_03.
```

---

## 7. Troubleshooting & Security Best Practices

| Problem | Cause | Solution |
|:---|:---|:---|
| `Connection refused: 127.0.0.1:49494` | Photoshop is not running or Remote Connection is disabled. | Open Photoshop > Preferences > Plug-ins > Check "Enable Remote Connections" and verify the password. |
| `Windows Firewall blocking connection` | Windows Firewall blocked local socket port. | In Windows Security > Firewall, allow `photoshop.exe` on Private Networks. |
| `Font substitution warning` | Target font is missing from the local system. | Install font or instruct agent to use Google Fonts / system fonts explicitly. |
| `Layers get rasterized unintentionally` | Using destructive commands instead of Smart Objects. | Instruct agent: *"Always maintain non-destructive editing: use Smart Objects, Vector Shapes, and Adjustment Layers."* |
| `Slow execution on complex PSD` | Document has 100+ layers or massive resolution (8K+). | Group layers into Smart Objects and close unused background documents to free scratch disk memory. |
