---
name: doc-api
description: Bootstrap and convert Godot 4 API documentation from XML to compact, LLM-friendly Markdown for all 850+ engine classes.
---

# Godot API Doc Generator

Converts Godot's XML class documentation into compact Markdown files optimized for LLM context windows.

## Tools

- `ensure_doc_api.sh` — Bootstrap script: sparse-clones Godot repo, generates per-class Markdown
- `godot_api_converter.py` — XML-to-Markdown converter with configurable detail levels
- `class_list.py` — Curated class lists for scene generation, script generation, and unified coverage

## Usage

```bash
# Bootstrap doc_api (safe to re-run, skips if already exists)
bash tools/doc-api/ensure_doc_api.sh

# Manual conversion with custom options
python3 tools/doc-api/godot_api_converter.py \
  -i doc_source/godot/doc/classes \
  --split-dir doc_api \
  --class-desc first
```

## Output

- `doc_api/_common.md` — Index of ~128 commonly used Godot classes
- `doc_api/_other.md` — Index of ~730+ remaining classes
- `doc_api/{ClassName}.md` — Full API reference per class
