# Skill Bank

A curated collection of Claude Agent Skills, selected for FPGA / DDR engineering workflows (documentation, spreadsheets, technical spec co-authoring, custom skill development, and MCP tool building).

## Source

All skills below are copied from the official Anthropic repository: [anthropics/skills](https://github.com/anthropics/skills).

| Skill | Purpose |
|---|---|
| [docx](./skills/docx) | Create, read, and edit Word documents (.docx/.dotx) |
| [pdf](./skills/pdf) | Read, merge, split, watermark, fill, and OCR PDF files |
| [pptx](./skills/pptx) | Create and edit PowerPoint presentations (.pptx/.potx) |
| [xlsx](./skills/xlsx) | Create and edit spreadsheets (.xlsx/.csv/.tsv) |
| [doc-coauthoring](./skills/doc-coauthoring) | Structured workflow for co-authoring specs, proposals, and technical docs |
| [skill-creator](./skills/skill-creator) | Create, edit, and evaluate custom Claude skills |
| [mcp-builder](./skills/mcp-builder) | Guide for building high-quality MCP servers to expose internal tools |

Additional community skills for FPGA/RTL work:

| Skill | Source | Purpose |
|---|---|---|
| [claude-skill-verilog](./skills/claude-skill-verilog) | [londey/claude-skill-verilog](https://github.com/londey/claude-skill-verilog) (MIT) | Verilog/SystemVerilog coding style and Verilator testbench workflow guidance (lowRISC/FPGACPU/Project F derived standards) |
| [fpga](./skills/fpga) | [mindrally/skills](https://github.com/mindrally/skills) (Apache 2.0) | FPGA development guidelines: Vivado project organization, SystemVerilog synchronous design, XDC timing closure, AXI interface handshaking |

## Licensing note

Per the upstream repository's README: `docx`, `pdf`, `pptx`, and `xlsx` are **source-available** (not open source) reference implementations of Claude's built-in document skills. `doc-coauthoring`, `skill-creator`, and `mcp-builder` are Apache 2.0 licensed. See [THIRD_PARTY_NOTICES.md](./THIRD_PARTY_NOTICES.md) for full attribution details.

`claude-skill-verilog` is MIT licensed (see [its LICENSE](./skills/claude-skill-verilog/LICENSE)); `fpga` is sourced from the Apache 2.0 `mindrally/skills` repo (see [LICENSE-mindrally-skills.txt](./skills/fpga/LICENSE-mindrally-skills.txt)). Neither includes executable scripts — both are plain-Markdown guidance skills.

## Usage

Each skill folder contains a `SKILL.md` with YAML frontmatter (name, description) and instructions. Point your Claude Code / Claude Agent SDK skill discovery path at this repository, or copy individual skill folders into your project's `.claude/skills/` directory.
