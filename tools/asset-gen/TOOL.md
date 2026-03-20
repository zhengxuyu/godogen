---
name: asset-gen
description: Generate PNG images (Gemini), sprite sheets, remove backgrounds, and convert to GLB 3D models (Tripo3D) for Godot game assets.
---

# Asset Generator

CLI toolkit for generating game assets: images, sprite sheets, background removal, and 3D models.

## Tools

- `asset_gen.py` — Main CLI: `image` (PNG via Gemini), `spritesheet` (4x4 grid), `glb` (3D via Tripo3D), `set_budget`
- `rembg_matting.py` — Remove solid-color backgrounds with alpha matting
- `spritesheet_slice.py` — Process sprite sheets: crop grid lines, split, remove backgrounds
- `spritesheet_template.py` — Generate numbered 4x4 grid templates
- `tripo3d.py` — Tripo3D API client for image-to-3D model conversion

## Requirements

- Python 3 with packages listed in `requirements.txt`
- `GOOGLE_API_KEY` environment variable (for Gemini image generation)
- `TRIPO3D_API_KEY` environment variable (for 3D model conversion)

## Usage

```bash
# Generate an image
python3 tools/asset-gen/asset_gen.py image --prompt "..." -o output.png

# Generate a sprite sheet
python3 tools/asset-gen/asset_gen.py spritesheet --prompt "..." --bg "#4A6741" -o output.png

# Remove background
python3 tools/asset-gen/rembg_matting.py input.png -o output.png

# Convert to 3D model
python3 tools/asset-gen/asset_gen.py glb --image input.png --quality medium -o output.glb
```
