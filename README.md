# LichtFeld Studio + COLMAP Pipeline

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/opsabove)

A complete **3D Gaussian Splatting** workflow — from raw footage to a fully trained 3DGS scene — packaged in a single Windows installer.

This bundle includes:

- **LichtFeld Studio** — 3DGS training and viewer
- **COLMAP Pipeline** — a GUI tool for running COLMAP photogrammetry, built by [OpsAbove](https://www.opsabove.com), bundled alongside LichtFeld Studio for a seamless one-click experience

---

## What's inside the installer

| Component | Description |
|---|---|
| LichtFeld Studio | 3D Gaussian Splatting training app |
| COLMAP (via LichtFeld) | Photogrammetry engine (bundled with LichtFeld Studio) |
| COLMAP Pipeline | GUI tool for running COLMAP — feature extraction, matching, reconstruction |

---

## Workflow

```
Video footage
      ↓
Frame export tool  →  frames (GPS EXIF optional)
      ↓
COLMAP Pipeline  →  sparse reconstruction  (colmap_work/)
      ↓
LichtFeld Studio  →  3D Gaussian Splatting
```

---

## Features (COLMAP Pipeline)

- **GPS-aware reconstruction** — `pose_prior_mapper` with spatial matching when GPS EXIF is present
- **Sequential matching** — for indoor scenes or GPS-denied environments
- **Flat / Perspective and Raw Fisheye** camera model support
- **Stop & Resume** — safely interrupt and continue from the last completed step
- **Auto-resume detection** — picks up automatically from the last completed step
- **Images junction** — links your images folder inside the workspace so LichtFeld Studio resolves them without manual setup
- **Config persistence** — remembers your last paths and settings

---

## Requirements

- Windows 10 / 11 (64-bit)
- NVIDIA GPU (recommended for 3DGS training)

---

## Installation

Download the latest release from the [Releases](../../releases) page and run **LichtFeld_Studio_Setup.exe**.

The installer will:
- Install LichtFeld Studio
- Place COLMAP Pipeline alongside it
- Create **Desktop shortcuts** for both LichtFeld Studio and COLMAP Pipeline

---

## Usage

### Step 1 — Extract frames

Export frames from your video footage using any frame export tool. For best results, export perspective (flat) frames with GPS EXIF metadata when available.

### Step 2 — Run COLMAP Pipeline

Open **COLMAP Pipeline** and set:

| Field | Description |
|---|---|
| **LichtFeld Studio folder** | Root folder of your LichtFeld Studio installation |
| **Images folder** | Folder containing your exported frames |
| **Work folder** | Output directory for COLMAP results |

Choose your frame type and GPS setting, then click **Run COLMAP**.

### Step 3 — Train in LichtFeld Studio

Drag the work folder into **LichtFeld Studio** to start 3DGS training. The `images` link is created automatically by COLMAP Pipeline so LichtFeld finds your frames without any extra setup.

---

## License

MIT — see [LICENSE](LICENSE)

---

## Credits

- **[LichtFeld Studio](https://lichtfeld.io)** — 3D Gaussian Splatting training app by the LichtFeld team
- **[COLMAP](https://colmap.github.io)** — open-source photogrammetry and 3D reconstruction (ETH Zürich)
- **COLMAP Pipeline** — GUI tool built by [OpsAbove](https://www.opsabove.com)

---

<p align="center">
  COLMAP Pipeline built with ☕ by <a href="https://www.opsabove.com">OpsAbove</a> ·
  <a href="https://ko-fi.com/opsabove">Support on Ko-fi</a>
</p>
