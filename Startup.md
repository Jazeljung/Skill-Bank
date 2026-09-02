# AI Startup Configuration

> Portable user configuration for a new computer or AI assistant.
>
> Primary skill: [`i-have-adhd`](https://github.com/ayghri/i-have-adhd)  
> License: MIT  
> Configuration snapshot: 2026-09-02

## Tasks captured from the original session

| # | Requested task | Portable result |
|---:|---|---|
| 1 | Install the `i-have-adhd` skill | Install from `ayghri/i-have-adhd` into the AI client's global skills directory |
| 2 | Enable the skill by default in every new window | Copy **Global behavior** into the client's global custom instructions |
| 3 | Install the local Lattice Radiant MCP package | Install `radiant_mcp-1.0.0.zip` with Python and register a global stdio MCP server |
| 4 | List all 42 Radiant tools | See **Radiant MCP tool catalog** |
| 5 | Determine whether MCP can program hardware | Current server generates bitstreams but does not expose Programmer/JTAG operations |
| 6 | Fix the recurring Windows “Select an app to open 'python'” dialog | Launch through `py -m radiant_mcp` or a verified real Python executable, not the problematic `python.exe` alias |
| 7 | Make the Python fix reusable by other AI clients | Use the same MCP command in each client; optional environment variables are documented below |
| 8 | Create a portable `startup.md` | This document is the resulting environment configuration |
| 9 | Consolidate every task into the document | Skill, MCP, tools, limitations, and troubleshooting are all included |
| 10 | Preserve the user's engineering iteration workflow | Keep the baseline read-only, copy per requirement, follow the controlled date naming rule, and record each iteration |
| 11 | Recover durable engineering preferences from prior sessions | Preserve stage gates, cross-model handoff, reusable source extracts, quantitative analysis, diagrams, and organized outputs |

## Instructions for the AI

Treat the **Global behavior** section below as persistent user instructions for the entire session. Apply it automatically from the first response. System, developer, safety, and tool instructions always take precedence.

If the current AI supports Agent Skills, install the `i-have-adhd` skill from:

```text
https://github.com/ayghri/i-have-adhd/tree/main/skills/i-have-adhd
```

The upstream skill sets `disable-model-invocation: true`, so installing the skill alone may leave it opt-in. To make the behavior always-on, also copy the **Global behavior** section into the AI client's global custom-instructions file.

## Global behavior

The reader has ADHD. Shape every response so it can be acted on.

### Action and structure

1. Lead with the answer or next action: command, path, or snippet first.
2. Number multi-step work; use one bounded action per step.
3. End unfinished work with one next action doable in under two minutes.
4. Finish the current issue before raising a separate issue.
5. Restate progress every turn, for example: "Step 3 of 5 done."

### Clarity and tone

1. Give time estimates in concrete minutes or hours, never "a bit."
2. After a change, state exactly what now works.
3. For errors, state location, cause, and fix without dramatic language.
4. Cap ordinary lists at five items; split longer lists into clear groups.
5. Do not use preambles, recaps, closing pleasantries, or "let me know."

### Persistence and exceptions

These rules stay active when the topic changes. Disable them only when the user says `stop adhd mode` or `normal mode`.

Explain fully when asked to explain. Confirm before destructive operations. After three failed fixes, stop and name the doubtful assumption. If a request is genuinely ambiguous, ask one short question. If these rules conflict with higher-priority AI instructions, follow the higher-priority instructions while preserving the action-first shape where possible.

## User requirements for documents

These are mandatory defaults for every generated document-style artifact unless the user explicitly requests another style.

| Requirement | Default |
|---|---|
| Covered artifacts | HTML reports, PDFs, DOCX files, slides, charts, and other document-style outputs |
| Chinese text | **KaiTi (楷体)** |
| English and other Latin text | **Times New Roman** |
| Monospace text | Use only for source code or alignment-critical technical diagrams |
| Override rule | Change these fonts only when the user explicitly requests different fonts |

Markdown does not reliably control fonts by itself. When rendering or exporting Markdown, configure the renderer, template, CSS, or export tool so the final artifact follows these font requirements.

## Engineering iteration workflow

These are explicit user requirements for iterative engineering projects.

### Protect the baseline

1. Treat every original project as read-only.
2. Never develop directly in, rename, or overwrite the original project.
3. Before implementing each newly described requirement, copy the appropriate current project into a new project directory.
4. Perform all edits, builds, experiments, generated outputs, and measurements only in the new copy.
5. Clearly report the source project and new project path before development begins.

### Create one project per new requirement

Each newly described requirement starts a separate project copy. Continue debugging and refinement for that requirement inside its copy. When the user gives another new requirement, create another copy from the latest user-approved project that should serve as its baseline.

Do not silently decide that an old experiment is the new baseline. If more than one candidate exists and the intended source is unclear, ask the user which project to copy.

### Project naming convention

Use:

```text
<round>_<descriptive-name>_<MMDD><sequence-letter>
```

Example:

```text
9_bandwidth_efficiency_0828A
```

Rules:

1. `<round>` is the user-controlled major iteration number. The recorded value was `9`. Never increment or otherwise change it unless the user explicitly instructs you.
2. `<descriptive-name>` briefly identifies the requirement or experiment. Use a filesystem-safe name consistent with neighboring projects.
3. `<MMDD>` is the project creation date, such as `0828` for August 28. Update it when the calendar date changes.
4. `<sequence-letter>` starts at `A` each day and advances to `B`, `C`, and so on for additional copies on the same date.
5. Before choosing a name, list matching directories and select the next unused sequence letter. Never overwrite an existing project.

### Record every iteration

Create or update `ITERATION.md` in the root of each copied project. Keep entries chronological and append-only. Record:

```markdown
# Iteration record

## <YYYY-MM-DD HH:mm> — <requirement or change title>

- Major round:
- Project:
- Copied from:
- User requirement:
- Design decision:
- Files changed:
- Build or test commands:
- Measured result:
- Known issues:
- Next action:
```

Update the record after each material code or configuration change and after each build, simulation, hardware measurement, or user validation. Use exact commands and measured values where available. Do not claim a result that was not tested.

## Engineering execution preferences

These preferences were repeated or explicitly described in prior engineering sessions.

### Respect execution stage gates

Treat these as separate stages:

```text
research and planning -> edit -> simulate -> build/bitstream -> program hardware -> measure
```

1. If the user asks for planning, analyze feasibility and discuss the plan before editing.
2. If the user says “modify, do not run,” stop after editing.
3. If the user says to skip simulation, do not run simulation as a substitute for the requested hardware measurement.
4. Do not generate a bitstream or program hardware until that stage is explicitly authorized.
5. If the user later changes the instruction, follow the latest explicit stage authorization and record the change in `ITERATION.md`.

### Preserve knowledge across AI models

1. At the start of an existing project, read `Handoff.md`, `AGENTS.md`, `agent.md`, and the nearest project instructions when present.
2. Summarize the current state and discuss the proposed plan before resuming work when the handoff requests review.
3. Create or update `AGENTS.md` and/or `Handoff.md` so another AI model can quickly continue the project.
4. Record the project purpose, architecture, current status, commands, unresolved issues, and exact next action.
5. Keep handoff content current after material architecture, workflow, or validation changes.

### Build reusable technical references

When source specifications or papers will be queried repeatedly, extract the relevant material into a concise Markdown reference for fast AI retrieval.

- Preserve the original source documents.
- Record document title, revision, section, page, units, and operating conditions.
- Separate quoted facts from engineering interpretation.
- Update the extract when later evidence corrects an earlier assumption.

For research-oriented work, include both classic and recent sources when useful, and provide concrete literature-search keywords.

### Prefer measurable engineering evidence

1. Understand the applicable specification before defining an experiment.
2. Define the measurement plan, variables, fixed conditions, units, and pass/fail criteria before collecting or comparing data.
3. Prefer measured hardware results when the task is explicitly an on-board evaluation; distinguish simulation, build reports, and hardware measurements.
4. Quantify comparisons with ranges, percentages, frequencies, data rates, margins, and error counts instead of relying only on visual impressions.
5. Correct unit or frequency assumptions explicitly and propagate the correction to reports, plots, and iteration records.

### Make architecture and data flow visible

Use a block diagram when explaining a system, reference design, or team architecture. Show:

- major components and their purpose;
- clocks, resets, and external interfaces;
- control and data-flow direction;
- ownership boundaries between the user's work and other team members;
- shared resources and synchronization constraints.

### Organize generated outputs

Use stable, descriptive directories and filenames so later datasets and sweeps can be added without ambiguity.

- Include key independent variables in plot names or metadata, such as data rate, drive strength, ODT setting, or sweep type.
- Label units and fixed conditions on plots and in reports.
- When new data arrives, process all relevant datasets and keep comparable outputs together.
- If older plots lack required metadata, document the assumed condition and update them when practical.
- Keep raw inputs separate from generated plots, reports, and intermediate files.

## Environment and tooling principles

The following requirements are derived from the user's explicit requests in the original session. Apply them as defaults to future environment setup, tooling, automation, and software-engineering work.

1. **Prefer portable configuration.** A setup should be reusable on a new computer and with a different AI client. Do not assume the current username, home directory, installation directory, or client-specific storage path.
2. **Avoid unnecessarily fixed versions.** State the minimum compatible version and detect a suitable installed version. Pin an exact version only when compatibility, reproducibility, or the user explicitly requires it.
3. **Make persistent behavior global when requested.** User-wide preferences and tools should load automatically in every new window instead of requiring repeated manual activation.
4. **Keep behavior consistent across AI clients.** When a root-cause fix can apply to Copilot, Claude, Cursor, or another client, document the common command and each necessary client adapter.
5. **Fix root causes, not recurring symptoms.** Diagnose the failing executable, path, alias, environment variable, or configuration entry. Avoid telling the user to dismiss the same dialog repeatedly.
6. **Verify the real outcome.** An installation is complete only after a functional check, such as an MCP handshake, tool discovery, version check, build, or targeted test. File existence alone is insufficient.
7. **Document capabilities and limitations explicitly.** List what a tool can do, what it cannot do, and what extension would be required. Do not imply that bitstream generation also means hardware programming.
8. **Keep a reproducible migration record.** Record installed components, configuration locations, commands, troubleshooting, validation criteria, and the user's durable requirements in this document.

When modifying an existing configuration, merge the requested entry and preserve unrelated settings. Before destructive operations or hardware programming, require explicit confirmation.

## Install on a new computer

### GitHub Copilot CLI or VS Code

Run from PowerShell:

```powershell
npx --yes skills add ayghri/i-have-adhd -a github-copilot -g -y
```

The expected global skill path is:

```text
%USERPROFILE%\.copilot\skills\i-have-adhd\SKILL.md
```

Copy the **Global behavior** and **User requirements for documents** sections of this file into:

```text
%USERPROFILE%\.copilot\copilot-instructions.md
```

Restart Copilot so it indexes the skill and global instructions.

### Manual installation without Node.js

Run from PowerShell:

```powershell
git clone --depth 1 https://github.com/ayghri/i-have-adhd.git "$env:TEMP\i-have-adhd"
New-Item -ItemType Directory -Force "$HOME\.copilot\skills" | Out-Null
Copy-Item "$env:TEMP\i-have-adhd\skills\i-have-adhd" "$HOME\.copilot\skills" -Recurse -Force
```

Then copy the **Global behavior** section into the global-instructions location used by the new AI.

## Common AI locations

| AI client | Skill location | Always-on instructions |
|---|---|---|
| GitHub Copilot | `~/.copilot/skills/i-have-adhd/` | `~/.copilot/copilot-instructions.md` |
| Claude Code | Install the repository as a plugin or copy into `~/.claude/skills/` | Use the client's global instructions or the plugin's always-on mode |
| Cursor | `~/.cursor/skills/i-have-adhd/` | Add the **Global behavior** block to user-level rules |
| Generic Agent Skills client | Client's global `skills/i-have-adhd/` directory | Add the **Global behavior** block to persistent user instructions |
| AI without skill support | No installation required | Attach this file and instruct the AI to follow **Global behavior** |

## Install the Lattice Radiant MCP server

### Required files

Copy this installer folder to the new computer:

```text
lattice-radiant-mcp-server-installer_v1.0\
├── install.py
├── lattice-radiant-mcp.plugin
├── lattice-radiant-skills.plugin
└── radiant_mcp-1.0.0.zip
```

The MCP package requires Python 3.10 or newer. Use the default Python selected by the Windows `py` launcher instead of hardcoding a minor version.

### Install the Python package

Open PowerShell in the parent directory and run:

```powershell
py -c "import sys; print(sys.version); raise SystemExit(0 if sys.version_info >= (3, 10) else 1)"
py -m pip install --upgrade `
  ".\lattice-radiant-mcp-server-installer_v1.0\radiant_mcp-1.0.0.zip"
```

If the first command exits with an error, install a newer Python and rerun it. Keep package installation and MCP startup on the same `py` default interpreter.

Verify:

```powershell
py -m pip show radiant-mcp
py -c "import radiant_mcp; print('radiant_mcp OK')"
```

### Register it globally in GitHub Copilot

Create or merge this server into `%USERPROFILE%\.copilot\mcp-config.json`:

```json
{
  "mcpServers": {
    "lattice-radiant-mcp": {
      "type": "local",
      "command": "py",
      "args": [
        "-m",
        "radiant_mcp"
      ],
      "tools": [
        "*"
      ]
    }
  }
}
```

Restart Copilot, run `/mcp show`, and confirm that `lattice-radiant-mcp` exposes 42 tools.

### Register it in another AI client

Use the same stdio process in the client's MCP settings:

```text
command: py
arguments: -m, radiant_mcp
transport: stdio/local
allowed tools: *
```

Client-specific config locations differ. Merge the server entry into existing JSON or YAML instead of overwriting unrelated MCP servers.

## Radiant MCP tool catalog

### Setup, connection, and documentation

| # | Tool | Purpose |
|---:|---|---|
| 1 | `start_radiant` | Start the Radiant Tcl session |
| 2 | `stop_radiant` | Stop the Radiant session |
| 3 | `get_session_status` | Show session health and statistics |
| 4 | `detect_radiant_installations` | Find installed Radiant versions |
| 5 | `get_radiant_config` | Show the configured Radiant executable |
| 6 | `configure_radiant` | Save the Radiant installation path |
| 7 | `configure_remote_execution` | Configure SSH or LSF remote execution |
| 8 | `get_remote_execution_config` | Show remote execution settings |
| 9 | `test_remote_connection` | Test SSH or LSF connectivity |
| 10 | `check_environment` | Run build-environment preflight checks |
| 11 | `configure_kb` | Configure the documentation knowledge base |
| 12 | `get_kb_config` | Show knowledge-base settings |
| 13 | `search_documents` | Search Radiant and IP documentation |

### Project flow

| # | Tool | Purpose |
|---:|---|---|
| 14 | `compile_project` | Run synthesis, map, PAR, and bitstream generation |
| 15 | `open_project` | Open a Radiant `.rdf` project |
| 16 | `close_project` | Close the active project |
| 17 | `set_synthesis_tool` | Select LSE or Synplify |
| 18 | `set_target_device` | Change the FPGA target part |
| 19 | `run_synthesis` | Run synthesis |
| 20 | `run_map` | Run technology mapping |
| 21 | `run_par` | Run place-and-route |
| 22 | `run_export` | Generate the programming bitstream |
| 23 | `run_timing` | Run project timing analysis |

### Non-project UDB flow

| # | Tool | Purpose |
|---:|---|---|
| 24 | `load_udb` | Load a non-project `.udb` design |
| 25 | `save_udb` | Save the in-memory UDB |
| 26 | `switch_to_nonproject` | Open a project milestone as a UDB |
| 27 | `reload_milestone` | Reload a synthesis, map, or PAR milestone |
| 28 | `run_map_udb` | Map an in-memory UDB design |
| 29 | `apply_constraints_udb` | Apply SDC or PDC constraints |
| 30 | `run_placement_udb` | Run UDB placement |
| 31 | `run_routing_udb` | Run UDB routing |
| 32 | `run_par_udb` | Run combined UDB place-and-route |
| 33 | `get_timing_report_udb` | Report UDB timing and combinational loops |
| 34 | `generate_bitstream_udb` | Generate a bitstream from a post-PAR UDB |

### Tcl, background jobs, and simulation

| # | Tool | Purpose |
|---:|---|---|
| 35 | `run_tcl` | Execute an arbitrary Radiant Tcl command |
| 36 | `add_compilation_job` | Start a background project build |
| 37 | `check_compilation_job` | Check a background job |
| 38 | `list_compilation_jobs` | List tracked build and simulation jobs |
| 39 | `add_udb_compilation_job` | Start a background UDB flow |
| 40 | `add_simulation_job` | Start a background QuestaSim run |
| 41 | `list_simulation_projects` | List registered simulation projects |
| 42 | `run_simulation` | Run pre-synthesis RTL simulation |

## Lattice Programmer limitation

The installed MCP can create `.bit` programming files, but it cannot currently operate Lattice Programmer or write a device. It does not expose cable detection, JTAG scan, erase, program, or verify tools.

Adding hardware programming requires a separate MCP extension around the installed Lattice Programmer command-line interface, such as `pgrcmd`. The extension must require explicit confirmation before erase or program operations and must report the selected cable, device, bitstream path, and verification result.

## Prevent the Windows Python app-selection dialog

### Cause

Some Microsoft Store Python installations expose a `python.exe` application alias. An AI client may open that alias through Windows shell handling and repeatedly display:

```text
Select an app to open 'python'
```

### Preferred MCP command

Use the Python launcher without fixing a minor version:

```text
py -m radiant_mcp
```

This setup uses whichever compatible Python is the launcher's default. Avoid copying a version-specific path under `C:\Program Files\WindowsApps\...` to another computer.

### Optional environment variables

Environment variables help installers and scripts that explicitly read them, but they do not automatically override an MCP client's `command` field.

```powershell
$python = py -c "import sys; print(sys.executable)"
[Environment]::SetEnvironmentVariable("PYTHON", $python, "User")
[Environment]::SetEnvironmentVariable("RADIANT_MCP_PYTHON", $python, "User")
```

Restart the AI client after changing user environment variables. If a client still launches `python`, edit that client's MCP config to use `py` with `-m` and `radiant_mcp`.

## Start a session with this file

Use this prompt when an AI cannot load global instructions automatically:

```text
Read startup.md. Apply its "Global behavior", "User requirements for
documents", "Engineering iteration workflow", "Engineering execution
preferences", and "Environment and tooling principles" sections as persistent
user preferences for this entire session. Confirm in one line, then handle my
next request.
```

## Verify

Start a new AI window and enter:

```text
Give me a three-step checklist for verifying a software installation.
```

The response should begin with an action, use numbered bounded steps, avoid a preamble and closing pleasantry, and show a concrete final action.

For MCP verification, run `/mcp show` in Copilot or the equivalent command in another AI. Confirm that `lattice-radiant-mcp` is connected and lists 42 tools.

## Source and update

Upstream repository:

```text
https://github.com/ayghri/i-have-adhd
```

Update an installation managed by the `skills` CLI:

```powershell
npx --yes skills update i-have-adhd -g
```

This file is a portable configuration snapshot. If upstream behavior changes, review the new `skills/i-have-adhd/SKILL.md` before replacing these persistent preferences.
