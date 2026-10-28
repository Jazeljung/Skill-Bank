# AI Startup Configuration

> Portable user configuration for a new computer or AI assistant.
>
> Primary skill: [`i-have-adhd`](https://github.com/ayghri/i-have-adhd)  
> License: MIT  
> Configuration snapshot: 2026-10-23

## Tasks captured from the original session

| # | Requested task | Portable result |
|---:|---|---|
| 1 | Install the `i-have-adhd` skill | Install from `ayghri/i-have-adhd` into the AI client's global skills directory |
| 2 | Enable the skill by default in every new window | Copy **Global behavior** into the client's global custom instructions |
| 3 | Install the local Lattice Radiant MCP package | Install `radiant_mcp-1.0.0.zip` with Python and register a global stdio MCP server |
| 4 | List all 42 Radiant tools | See **Radiant MCP tool catalog** |
| 5 | Determine whether MCP can program hardware | Current server generates bitstreams but does not expose Programmer/JTAG operations |
| 6 | Fix the recurring Windows “Select an app to open 'python'” dialog | Diagnose every `python` candidate; use `py` or a verified real Python executable instead of a Store alias or extensionless file |
| 7 | Make the Python fix reusable by other AI clients | Update MCP settings and global AI instructions so generated commands never invoke bare `python` or `python3` |
| 8 | Create a portable `startup.md` | This document is the resulting environment configuration |
| 9 | Consolidate every task into the document | Skill, MCP, tools, limitations, and troubleshooting are all included |
| 10 | Preserve the user's engineering iteration workflow | Keep the baseline read-only, copy per requirement, follow the controlled date naming rule, and record each iteration |
| 11 | Recover durable engineering preferences from prior sessions | Preserve stage gates, cross-model handoff, reusable source extracts, quantitative analysis, diagrams, and organized outputs |
| 12 | Enable a high-performance Windows power plan | Create and activate the built-in **High performance** scheme without changing voltage, overclocking, or firmware settings |
| 13 | Add image-based video production | Install the global `remotion-best-practices` skill so Copilot can author locally rendered videos without external generation credits |
| 14 | Avoid external video-generation billing | Do not register Glif; it requires a separate OAuth account and consumes Glif credits |
| 15 | Install a desktop diagram editor | Install the current applicable `JGraph.Draw` package through WinGet and verify the installed version |
| 16 | Install and maintain F2M | Install the complete F2M folder, register its MCP server with automatic board detection, install its three skills, and use the built-in verified updater |
| 17 | Add prose humanization | Install `blader/humanizer` globally and preserve facts, code, commands, paths, metadata, and links when rewriting prose |
| 18 | Preserve repeated FPGA project habits | Confirm top level and interfaces first, use schematic-backed constraints, validate with QuestaSim when authorized, and require explicit permission before hardware programming |
| 19 | Restore the classic Windows 11 context menu | Configure the current user's Explorer context menu to show the full menu directly, without selecting **Show more options** |
| 20 | Reconnect GlobalProtect locally after disconnection | Run a current-user watcher targeting the explicitly selected Taiwan gateway; include pause/resume, bounded retries, and no credential handling |
| 21 | Retry failed Copilot sessions without disturbing healthy sessions | Install a global event-driven extension that sends `retry` only after a fresh root-session `Execution failed` error, with deduplication and at most three consecutive retries |
| 22 | Keep the computer running while allowing the screen to turn off | Keep High performance active; disable automatic sleep, hibernation, and unattended sleep on AC and battery without changing display-off timeouts or critical-battery protection |
| 23 | Enable the company's debugging issue platform (Lattice Atlassian Jira) | Include the Atlassian Rovo MCP Server in environment initialization, sign in with the authorized company account, and verify access to the intended Jira site and project |

## Current computer snapshot

This table records the verified state of the source computer on 2026-10-23. Use it as migration evidence, not as a permanent version pin.

| Component | Verified state | Notes |
|---|---|---|
| Windows Python | Python `3.12.10` through `py`; executable `C:\Users\jzhang11\AppData\Local\Programs\Python\Python312\python.exe` | Bare `python` remains unsafe because `C:\Windows\System32\python` is a zero-byte file |
| Lattice Radiant MCP | `radiant-mcp 1.0.0`; 42 tools | Configured Radiant executable: `C:\lscc\radiant\2026.1\bin\nt64\radiantc.exe` |
| F2M MCP | Running `1.5.2`; 91 tools observed | Installed in-place under the `1.5.1` folder; `1.6.1` was available during this audit but was not installed because this task only updates documentation |
| F2M skills | `f2m-retrofit`, `f2m-debug`, `f2m-check` | Bundled manifests still identify embedded specification `1.4.1`, on-wire protocol `2.0`, and JSON Schema `1.6` |
| General skills | `i-have-adhd`, `remotion-best-practices 4.0.520`, `humanizer 3.1.0` | Installed globally under `%USERPROFILE%\.copilot\skills` |
| draw.io Desktop | `31.4.4.0` | WinGet reported `32.5.5` available during this audit; update separately with user approval |
| Windows power plan | **High performance** active | May increase heat, fan noise, and battery use |
| Glif | Not installed | Deliberately excluded because media generation uses a separate Glif account and credits |

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

For a newly created FPGA project, use a self-checking QuestaSim flow and continue debugging until the requested function passes before moving to build or bitstream generation, provided the user has authorized execution. Report the first real root cause and distinguish design failures from testbench, tool, environment, or license failures. A later instruction such as “modify only,” “do not run,” or “skip simulation” overrides this default.

### Place-and-route timing and Radiant concurrency

User instruction added on 2026-10-23:

1. Timing violations reported during Place and Route are allowed. Do not add fixes or reruns solely to close these violations unless the user later explicitly requests timing closure.
2. Continue to bitstream generation when the tool permits it. Record the actual timing result and available WNS/TNS or slack metrics; never describe a violating design as timing-passed. Do not hide violations by disabling constraints or changing clock targets.
3. This computer may run at most **two Radiant project builds concurrently**. Count project build jobs, not their internal child processes or idle GUI windows. Check active builds before starting another, and do not interrupt unrelated work.
4. Parallel projects must use separate directories. Record the source snapshot and avoid copying mutable build outputs as if they were new results.
5. These rules do not waive build/DRC failures or authorize hardware programming.

### Confirm the top level and interfaces before coding

Before writing implementation code for a design project:

1. Discuss the proposed architecture and responsibility boundaries with the user.
2. Identify the top-level source file and top-level module or entity explicitly.
3. Define every external interaction interface, including signal names, directions, widths, protocols, clocks, resets, timing assumptions, and ownership.
4. Define how the top level connects to existing modules, constraints, software, testbenches, boards, or external devices.
5. Obtain the user's confirmation of the top level and interface contract before writing lower-level implementation code.

If the intended top-level file or interaction interface is ambiguous, stop and ask one focused question rather than guessing. Record the confirmed top level and interface contract in `ITERATION.md` and keep it synchronized with material design changes.

### Use authoritative board constraints

Do not invent FPGA pins, clocks, resets, I/O standards, memory topology, or board connectivity.

1. Derive new constraints from the board schematic, device documentation, or a user-approved working baseline.
2. Confirm the exact board and FPGA device before creating or changing project constraints.
3. Reuse validated constraints when the user identifies them as the approved source.
4. Keep copied baseline constraints unchanged unless the requirement needs a specific, reviewed change.
5. Record the constraint source and any intentional differences in `ITERATION.md`.

### Create and maintain a project Gantt chart

Whenever creating a new engineering project or project copy:

1. Discuss the project phases, deliverables, dependencies, milestones, owners, and target dates with the user.
2. Create an editable Gantt chart in draw.io before implementation begins.
3. Save the source as `docs/project_management/<project>_gantt.drawio` and export a synchronized view as `<project>_gantt.svg` or `<project>_gantt.png`.
4. Include at least planning, interface confirmation, implementation, simulation, build or bitstream, hardware programming when authorized, measurement, documentation, review, and user acceptance when applicable.
5. Mark dependencies, stage gates, critical milestones, current progress, known blockers, and the next actionable task.

Do not invent delivery dates or owners. Ask the user when they are not specified, or label them `TBD` until confirmed. Update the Gantt chart after material scope, schedule, dependency, milestone, blocker, or completion changes, and record each update in `ITERATION.md`.

### Main engineering session and supporting case-research session

At the start of every engineering project, use the main conversation to run the project and make overall decisions, and a coordinated child conversation to collect relevant experience and similar cases that can guide implementation and debugging. This is the user's default division of responsibility across engineering projects, not a request to move project execution into a child.

1. **Main session owns execution and decisions.** Keep the project context, architecture, implementation changes, authorized simulations/builds/hardware operations, measurements, and user communication in the main session. The main session evaluates the research and decides what to try next within the user's existing authorization.
2. **Child session owns supporting research.** Start or reuse one coordinated case-research child for the current project. Give it the current goal, symptoms, relevant device/IP/tool versions, known facts, attempted approaches, and a bounded research question. Search authorized sources such as company Jira cases, existing handoffs, local references, and vendor documentation. Do not duplicate the main session's builds, edits, or hardware operations.
3. **Report evidence, not just suggestions.** For each useful case, report its issue key/link or document revision and page, symptom, environment, root cause, fix or workaround, and verification outcome. Explain similarities and differences from the current project, applicability, uncertainty, and a proposed diagnostic step. Clearly separate source facts from hypotheses; similar symptoms do not prove the same root cause.
4. **Report when findings affect decisions.** Send the main session actionable cases, relevant new evidence, corrections, and blockers as they become available. Do not flood it with repeated status messages. The main session directs further research as debugging evolves and records adopted findings and decisions in the project handoff and iteration record.
5. **Preserve authority and confidentiality.** A child's recommendation is not user approval to change RTL, build, program hardware, or publish a Jira update. Keep project facts within authorized sources and do not upload sensitive code or measurements as part of a search. If no usable evidence or access exists, report the limitation without inventing a case.

Do not create extra research children for the same question or use large multi-agent workflows by default. If the client cannot create coordinated child conversations, state that limitation rather than claiming parallel research is running. A documentation-only request to record this preference does not itself start a project or require a child session.

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

Use draw.io Desktop as the default diagram tool across all tasks. Create a principle block diagram when explaining a system, reference design, architecture, hardware/software partition, or non-trivial control/data flow. Preserve an editable `.drawio` source and export a viewable `.svg` or `.png` beside it. Do not create a diagram when it would add no useful information.

Show:

- major components and their purpose;
- clocks, resets, and external interfaces;
- control and data-flow direction;
- ownership boundaries between the user's work and other team members;
- shared resources and synchronization constraints.

Use stable filenames such as:

```text
docs/diagrams/<topic>_architecture.drawio
docs/diagrams/<topic>_architecture.svg
```

Keep the exported file synchronized with the editable source after each material diagram change.

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
9. **Do not assume command resolution is correct.** On Windows, inspect every candidate returned by `Get-Command <name> -All`; a valid interpreter later in `PATH` does not prevent an earlier invalid file from being selected.

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

## Install local video-production guidance

Use `remotion-best-practices` when uploaded images need to be composed into a deterministic video with captions, transitions, narration, music, or local MP4 export. Copilot authors the Remotion project and the computer performs the render.

This workflow uses Copilot for code generation and local CPU/GPU resources for rendering. It does not provide a Copilot-funded text-to-video model. External media-generation services may still require separate accounts and credits.

Install globally with the Skills CLI:

```powershell
npx --yes skills add remotion-dev/skills `
  --skill remotion-best-practices `
  -a github-copilot -g -y
```

Without Node.js, install from Git:

```powershell
$temp = Join-Path $env:TEMP "remotion-skills"
$target = Join-Path $HOME ".copilot\skills\remotion-best-practices"

git clone --depth 1 https://github.com/remotion-dev/skills.git $temp
New-Item -ItemType Directory -Force (Split-Path -Parent $target) | Out-Null
Copy-Item "$temp\skills\remotion-best-practices" $target -Recurse
Remove-Item $temp -Recurse -Force
```

Verify:

```powershell
Test-Path "$HOME\.copilot\skills\remotion-best-practices\SKILL.md"
```

Do not add `https://glif.app/api/mcp` when the requirement is to avoid third-party generation credits. Glif uses OAuth and charges generation against the signed-in Glif account.

## Install Humanizer

Use Humanizer when editing prose that sounds machine-generated. It must preserve the source meaning and must not invent facts, names, dates, numbers, quotations, citations, or conclusions.

Install globally:

```powershell
npx --yes skills add blader/humanizer --global --agent github-copilot
```

Manual installation without Node.js:

```powershell
$temp = Join-Path $env:TEMP "humanizer"
$target = Join-Path $HOME ".copilot\skills\humanizer"

git clone --depth 1 https://github.com/blader/humanizer.git $temp
New-Item -ItemType Directory -Force $target | Out-Null
Copy-Item "$temp\SKILL.md" $target
Copy-Item "$temp\README.md" $target -ErrorAction SilentlyContinue
Copy-Item "$temp\LICENSE" $target -ErrorAction SilentlyContinue
Remove-Item $temp -Recurse -Force
```

Verify:

```powershell
Select-String "$HOME\.copilot\skills\humanizer\SKILL.md" `
  -Pattern 'name: humanizer|version:'
```

When Humanizer edits a named file, change prose only. Preserve code blocks, inline code, commands, paths, YAML/frontmatter, data, link targets, and technical meaning.

## Install draw.io Desktop

Use the official WinGet package:

```powershell
winget install --id JGraph.Draw --exact --source winget `
  --accept-package-agreements --accept-source-agreements
```

Verify:

```powershell
winget list --id JGraph.Draw --exact --accept-source-agreements
```

Prefer the latest applicable version because draw.io desktop releases may include Electron and local-file security fixes. If WinGet first installs an older user-scoped portable build and reports that the newer MSI uses different installation technology, replace it only with user approval:

```powershell
winget uninstall --id JGraph.Draw --exact --source winget
winget install --id JGraph.Draw --exact --source winget `
  --accept-package-agreements --accept-source-agreements
```

The verified source installation was `31.4.4.0`. Treat this as a recorded result, not a permanent version pin; install the current applicable release on a new computer.

After installation, add the **Engineering diagrams** rule to the AI client's global instructions so future tasks use draw.io consistently. The required default is:

```text
Use draw.io Desktop for principle block diagrams, architecture diagrams,
hardware/software partition diagrams, and control or data-flow diagrams.
Preserve the editable .drawio file and export a viewable .svg or .png.
Do not create a diagram when it adds no useful information.
```

## Enable the Windows high-performance power plan

This setting prioritizes performance over energy efficiency and may increase fan noise, temperature, and battery drain. It does not modify CPU voltage, overclocking, BIOS, or cooling firmware.

Inspect the current schemes:

```powershell
powercfg /list
powercfg /getactivescheme
```

If **High performance** is absent, duplicate the built-in template and activate the returned GUID:

```powershell
$output = powercfg /duplicatescheme 8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c
$guid = [regex]::Match(
  ($output -join "`n"),
  "[0-9a-fA-F]{8}(?:-[0-9a-fA-F]{4}){3}-[0-9a-fA-F]{12}"
).Value

if (-not $guid) {
  throw "Could not determine the new power-scheme GUID"
}

powercfg /changename $guid "High performance"
powercfg /setactive $guid
powercfg /getactivescheme
```

Do not reuse a GUID copied from another computer; Windows creates a new GUID when the scheme is duplicated.

### Allow display-off, but prevent automatic sleep

The user clarified that the screen may turn off, but idle power management must not put the computer to sleep and interrupt background work. Apply this to both plugged-in and battery operation. Selecting High performance alone does not disable sleep.

Inspect and record the existing settings before changing them:

```powershell
powercfg /query SCHEME_CURRENT SUB_VIDEO VIDEOIDLE
powercfg /query SCHEME_CURRENT SUB_SLEEP STANDBYIDLE
powercfg /query SCHEME_CURRENT SUB_SLEEP HIBERNATEIDLE
powercfg /qh SCHEME_CURRENT SUB_SLEEP UNATTENDSLEEP
```

Use the normal current-user power configuration commands; do not request administrator access or modify organization policy unless separately authorized:

```powershell
foreach ($setting in @(
  'standby-timeout-ac', 'standby-timeout-dc',
  'hibernate-timeout-ac', 'hibernate-timeout-dc'
)) {
  powercfg /change $setting 0
  if ($LASTEXITCODE -ne 0) {
    throw "Windows refused the power setting: $setting"
  }
}
foreach ($mode in @('/setacvalueindex', '/setdcvalueindex')) {
  powercfg $mode SCHEME_CURRENT SUB_SLEEP UNATTENDSLEEP 0
  if ($LASTEXITCODE -ne 0) {
    throw "Windows refused the unattended sleep setting: $mode"
  }
}
powercfg /setactive SCHEME_CURRENT
if ($LASTEXITCODE -ne 0) {
  throw 'Could not reactivate the current power plan.'
}
```

Zero means **Never** for these timeouts. Re-read the settings afterward and confirm both AC and DC values are zero, the selected scheme is High performance, and display timeouts are unchanged. Do not disable critical-battery actions, alter lid/power-button behavior, or disable the hibernation feature globally as part of this idle-timeout change.

Recorded on 2026-10-23: the destination computer was already using High performance, but automatic sleep was 600 seconds on AC and 240 seconds on battery. Standard-user commands successfully changed sleep, hibernation, and unattended-sleep timeouts to zero for both power sources. Display-off timeouts remained 600 seconds on AC and 240 seconds on battery.

Exporting the full power plan with `powercfg /export` was refused with privilege error `0x522`; this did **not** mean normal timeout changes also required elevation. The user has no administrator privileges. No elevation or policy override was used.

## Restore the classic Windows 11 context menu

The user prefers the full, Windows 10-style right-click menu for files and folders instead of Windows 11's compact menu. Apply this preference when initializing a Windows 11 environment. This changes only the current user's Explorer menu behavior, not file associations or application-specific menus.

Inspect the override before changing it:

```powershell
$path = 'HKCU:\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}'
if (Test-Path -LiteralPath $path) {
  Get-Item -LiteralPath $path
  Get-ChildItem -LiteralPath $path | Select-Object Name, Property
}
```

If the key already exists, record its values and export a backup before modifying it. Preserve unrelated entries. If permission is denied, report the error rather than changing registry permissions.

Enable the classic menu by creating an explicitly empty default `REG_SZ` value; a missing default value is not equivalent:

```powershell
$ErrorActionPreference = 'Stop'
$subkey = 'Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32'
$key = [Microsoft.Win32.Registry]::CurrentUser.CreateSubKey($subkey)
try {
  $key.SetValue('', '', [Microsoft.Win32.RegistryValueKind]::String)
  if ($key.GetValueNames() -notcontains '' -or $key.GetValue('') -cne '') {
    throw 'Classic context menu setting verification failed.'
  }
} finally {
  $key.Dispose()
}
```

Ask before restarting Windows Explorer: the desktop and taskbar briefly disappear, folder windows may close, and active file operations may be interrupted. Wait for file copies or moves to finish. Restart only Explorer processes belonging to the current Windows session, using their specific process IDs, and confirm Explorer is running again. Alternatively, let the user sign out and back in or restart Windows later.

After Explorer restarts, right-click a file or folder and confirm the full menu appears without **Show more options**. This registry workaround is Windows-version-dependent and does not control menus implemented by individual applications; a saved registry value alone is not proof of the visual result.

Recorded on this computer on 2026-10-23: Windows 11 25H2, build `26200.9711`; the override was absent before setup, the empty default value was saved, and Explorer restarted successfully. Visual confirmation was requested but not recorded.

To undo this change, obtain confirmation and restore the previous values from the backup. If the override was absent before setup, remove only the default value and keys created by this procedure, after confirming no other values or subkeys have since been added. Restart Explorer with permission, or sign out and back in.

## Local GlobalProtect reconnect watcher

The destination computer has a local watcher in `D:\skills\globalprotect-reconnect`. It does not depend on GitHub Copilot or an internet service to run. The user explicitly selected **Taiwan** as the reconnect gateway and authorized current-user PowerShell `RemoteSigned` execution policy and automatic startup.

| File | Purpose |
|---|---|
| `Reconnect.ps1` | Watcher and install, uninstall, check, status, pause, and resume actions |
| `Native.cs` | Read the client's native controls and select the exact gateway row without moving the global mouse cursor |
| `RunHidden.vbs` | Launch the watcher without a visible PowerShell console; wait for it so Task Scheduler tracks its lifetime |
| `Pause.cmd` | Pause automatic reconnection before intentionally disconnecting VPN |
| `Resume.cmd` | Resume automatic reconnection after a pause or after resolving an error |
| `Status.cmd` | Show the scheduled task and last status heartbeat |
| `Test-Reconnect.ps1`, `Test-Native.ps1` | Retry-policy checks and a synthetic Windows list-control interaction test; neither disconnects the real VPN |

The watcher is specific to the observed English GlobalProtect `6.3.3-1016` interface. It checks the current session every 15 seconds, waits for two consecutive explicit disconnected states, and selects Taiwan. If a connection phase stays unchanged for 120 seconds, it restarts only the current user's verified `PanGPA.exe` process, then selects Taiwan when the client is ready. The user explicitly authorized this client-restart recovery method. It does not reconnect merely because a website is unreachable. Reconnects and client restarts share a three-attempt limit per outage and a minimum 60-second retry interval; three consecutive connected samples reset that limit.

Authentication/input prompts cause no click or client restart. An input page that remains open for 180 seconds pauses the watcher; a restarted client that is not ready within 180 seconds also pauses for manual attention. Automation errors and an exhausted retry limit pause it and record the reason. A locked desktop, unavailable client, unknown state, or normally progressing connection causes no click. The script never submits passwords, approves certificate exceptions, restarts the `PanGPS` VPN system service, or changes company VPN policy. Outside a recovery it leaves an already-connected client alone, including one manually connected to a different gateway. During a client-restart recovery, an internal-network status is not treated as proof that the Taiwan tunnel is restored; it selects Taiwan when the dropdown becomes available. A client version change requires rechecking the interface before resuming automation.

The current-user scheduled task is named `GlobalProtect-Reconnect-<user SID>` and runs only in that user's interactive session, without elevated privileges. It starts at login through `wscript.exe //B //NoLogo RunHidden.vbs`; the launcher starts PowerShell with a hidden window and waits for it. Normal monitoring creates no visible console. Logs and the status heartbeat are under `%LOCALAPPDATA%\GlobalProtectReconnect`; `paused.txt` keeps a pause in effect across restarts. Open `Status.cmd` if reconnection stops. Automatic UI operation may briefly bring GlobalProtect itself to the foreground. The `.cmd` controls open a console only when the user deliberately runs them.

To intentionally disconnect VPN, run `Pause.cmd` first: the watcher cannot reliably distinguish a manual disconnection from an unexpected one. Run `Resume.cmd` when automatic reconnection is wanted again. On another computer, confirm the gateway and client UI/version instead of assuming Taiwan or copying control IDs blindly.

Example commands from PowerShell:

```powershell
$toolDir = 'D:\skills\globalprotect-reconnect'
& "$toolDir\Reconnect.ps1" -Action Check
& "$toolDir\Reconnect.ps1" -Action Status
& "$toolDir\Reconnect.ps1" -Action Pause
& "$toolDir\Reconnect.ps1" -Action Resume
```

For a new installation, inspect `Get-ExecutionPolicy -List`. If the default policy blocks local scripts, obtain explicit approval before setting `CurrentUser` to `RemoteSigned`; never override organization policy or use an execution-policy bypass. Run `Reconnect.ps1 -Action Install` once to register and start the task; it refuses to overwrite an existing task.

To remove automatic startup and stop the watcher without disconnecting VPN:

```powershell
& 'D:\skills\globalprotect-reconnect\Reconnect.ps1' -Action Uninstall
```

The uninstall action retains scripts and logs. It does not reset the shared PowerShell execution policy: review other scripts before separately restoring the previous policy (recorded as `Undefined` for this user's scope before installation).

Recorded on 2026-10-23: retry-policy tests and synthetic native selection tests passed; the scheduled task was running and its heartbeat reported `Connected` on Taiwan. An explicitly authorized live disconnect test opened the company's **Enter the passcode to disconnect** prompt. No passcode was entered and no policy was bypassed; no actual disconnected state was observed. The watcher correctly paused on the input prompt, then was resumed after the client returned to its connected page. Actual outage recovery remains unverified; do not treat the connected-state check as proof of end-to-end recovery.

A subsequent user-requested **Best Available** switch reproduced a prolonged `Connecting...` state, not an explicit disconnected state. The user suggested ending the client task. Restarting only `PanGPA.exe` restored access to the gateway selector; selecting Taiwan then reconnected in about 35 seconds. This observed sequence informed the 120-second stalled-phase recovery logic. Retry/stall guards were tested, but a complete unattended reproduction of the revised recovery sequence has not yet been recorded.

## Guarded Copilot Execution failed auto-retry

The user explicitly requested automatic `retry` for Copilot sessions that encounter **Execution failed**, and explicitly prohibited sending it to sessions without that failure. This applies to the Copilot session error banner, not PowerShell command failures or quoted error text in a conversation. The user selected a limit of **three consecutive automatic retries**.

### Installation and scope

The implementation source is `D:\skills\copilot-execution-retry`. Its three files are:

```text
extension.mjs
core.mjs
core.test.mjs
```

The installed user-wide extension is:

```text
%USERPROFILE%\.copilot\extensions\execution-failed-retry\
```

Keep the source folder with this startup document when migrating. The document alone does not include the implementation. From the folder containing `copilot-execution-retry`, install on a new computer with:

```powershell
$source = Join-Path $PWD 'copilot-execution-retry'
$target = Join-Path $HOME '.copilot\extensions\execution-failed-retry'
if (Test-Path -LiteralPath $target) {
  throw 'Existing retry extension found. Inspect and back it up before replacing it.'
}
New-Item -ItemType Directory -Path (Split-Path -Parent $target) -Force | Out-Null
Copy-Item -LiteralPath $source -Destination $target -Recurse
```

Use Copilot's `extensions_reload` tool to activate it in the current session and `extensions_manage` with `inspect` to confirm it is running. New sessions load the user-wide extension automatically. **Already-open sessions need their own extension reload or a restart before they are covered.** Do not interrupt active work or send unsolicited messages to healthy sessions merely to activate it. Each loaded session watches only its own events and sends only to itself.

It runs inside Copilot's extension runtime without a separate PowerShell window, scheduled model prompts, screen scraping, simulated typing, or stored credentials. Copilot must remain running. Automatic retry turns consume the normal model usage allowance.

### Exact trigger and safeguards

1. Trigger only on a fresh root-agent `session.error` event whose `errorType` is `query` and whose message begins with `Execution failed:`. Require an event ID and valid recent timestamp. Ignore child-agent errors, tool failures, ordinary chat text, historical/replayed errors, explicit cancellations, and authentication/authorization/quota cases excluded by the implementation.
2. Deduplicate by error event ID using persistent per-session state. An event is claimed before scheduling, so a crash or extension reload cannot resend it. A failed or ambiguous send pauses instead of blindly resending.
3. Wait **60, 120, then 240 seconds** for successive retry attempts. Immediately before sending, require authoritative runtime checks showing no active/abortable work, no processing turn, no pending permission request, and no queued or steering message. A new user message, normal progress, abort, shutdown, or approval/input gate cancels a pending retry.
4. Send exactly `retry`, through the session API, without changing its mode or approving any tool, plan, login, or permission request. Resume controls never send a message themselves.
5. After three automatic attempts, another failure pauses auto-retry for that session. A successfully completed response or a genuinely new user request starts a new retry budget; another literal `retry` does not reset the cap. An explicit pause remains in effect until resumed.

The controller deliberately observes only failures arriving after it has loaded. It does not revive old failed tasks during installation or restart. If it cannot establish that sending is safe, it skips or pauses and records the reason rather than guessing.

### Status, pause, and resume

Use the extension's `copilot_retry_control` tool with `action: "status"`, `"pause"`, or `"resume"` in the relevant session. Resume clears the retry limit/pause and watches for **future** failures; it does not replay an old error or force a retry.

Per-session state, audit records, and status heartbeats are stored at:

```text
%USERPROFILE%\.copilot\execution-failed-retry\<session-id>\
```

The audit records event IDs, timestamps, retry counts, and outcomes, not full conversation text. The extension runs isolated tests with mock sends on startup; test failures disable loading rather than sending real messages for testing.

Recorded on 2026-10-23: the extension loaded in the initialization session, 43 local assertions passed, and the live runtime guard reported that the current active session was not eligible for sending. No real retry message was sent during setup. Coverage of other already-open sessions is not assumed until they reload the extension.

## Enable the company debugging issue platform (Atlassian Jira)

Include access to Lattice's Atlassian Jira debugging issue platform when initializing the engineering environment. Use the **Atlassian Rovo MCP Server** integration; reuse an existing installation instead of adding a duplicate. Prefer a user-wide installation for access across projects, subject to company policy.

### Setup and access verification

1. Check whether **Atlassian Rovo MCP Server** is installed and enabled. If missing, discover the official integration through the client's supported integration catalog and follow its installation flow. Do not invent a Jira tenant URL, cloud ID, project key, or server endpoint.
2. For a globally installed server in the Copilot desktop app, open **Customize > Installed**, find **Atlassian Rovo MCP Server**, and choose **Sign in**. For a repository-defined server, use **Settings > the project > Repository customizations > MCP servers**. If the server or sign-in action is absent, report that limitation instead of suggesting a CLI-only authentication command.
3. Complete the browser sign-in and any company SSO/MFA approval as the user. Never store passwords, API tokens, browser cookies, or other credentials in this document, scripts, or MCP configuration.
4. Discover the available MCP tool schemas, then call `getAccessibleAtlassianResources` to identify accessible sites. If more than one site could be the intended company site, ask the user to select it. Use the returned site/cloud ID rather than guessing.
5. Verify Jira project access with `getVisibleJiraProjects`, or read a user-specified issue with `getJiraIssue`. Tool availability alone does not prove authentication or permission to the intended project. Report authentication failures separately from missing project permissions or network errors.

### Usage boundaries

Use Jira to search and read debugging issues, track investigation context, and prepare issue updates relevant to the user's work. Creating or editing issues, adding comments or worklogs, linking issues, and changing workflow status require a concrete user request; environment initialization alone does not authorize those writes. Confirm the target site, project, and issue when ambiguous.

Keep RTL, register dumps, credentials, and other sensitive engineering data local unless an explicitly authorized sharing action is permitted by company policy. Access to Jira is not blanket permission to upload project files. Retain Jira issue keys and links in project handoff records only when relevant to the requested task.

Recorded on 2026-10-28: the user requested that Jira enablement be included in this startup document, and the session tool catalog exposed **Atlassian Rovo MCP Server** tools. This documentation update did not perform a sign-in or Jira access check and did not create or modify any Jira issue.

## Common AI locations

| AI client | Skill location | Always-on instructions |
|---|---|---|
| GitHub Copilot | `~/.copilot/skills/i-have-adhd/` | `~/.copilot/copilot-instructions.md` |
| Claude Code | Install the repository as a plugin or copy into `~/.claude/skills/` | Use the client's global instructions or the plugin's always-on mode |
| Cursor | `~/.cursor/skills/i-have-adhd/` | Add the **Global behavior** block to user-level rules |
| Generic Agent Skills client | Client's global `skills/i-have-adhd/` directory | Add the **Global behavior** block to persistent user instructions |
| AI without skill support | No installation required | Attach this file and instruct the AI to follow **Global behavior** |

## Install and update F2M

### Install the complete package

F2M releases from 1.5.x onward are folder applications. Copy the entire extracted directory, including `F2M_MCP.exe`, `_internal/`, `skills/`, `rtl/`, and `doc/`. Copying only the executable causes a startup failure because `_internal\python313.dll` is required.

Recommended stable location:

```text
%USERPROFILE%\.copilot\tools\f2m\<release>\
```

Example:

```powershell
$source = "D:\path\to\F2M_1.5.1"
$release = "1.5.1"
$target = Join-Path $HOME ".copilot\tools\f2m\$release"

if (Test-Path -LiteralPath $target) {
  throw "F2M target already exists: $target"
}

Copy-Item -LiteralPath $source -Destination $target -Recurse

if (-not (Test-Path -LiteralPath "$target\_internal\python313.dll")) {
  throw "Incomplete F2M installation: internal Python runtime is missing"
}
```

Register the server in `%USERPROFILE%\.copilot\mcp-config.json`, preserving unrelated MCP servers:

```json
{
  "mcpServers": {
    "f2m": {
      "type": "local",
      "command": "C:\\Users\\<user>\\.copilot\\tools\\f2m\\<release>\\F2M_MCP.exe",
      "args": [],
      "env": {
        "F2M_SERVER_URL": "http://LSH-F2M.latticesemi.com:8080",
        "F2M_ACCOUNT": ""
      },
      "tools": [
        "*"
      ]
    }
  }
}
```

Keep `args` empty during installation. Do not scan, request, or report COM ports until a bitstream containing an F2M hub is loaded and the selected transport is known. UART boards can be discovered later; JTAG boards do not use a COM port.

Install the bundled skills:

```powershell
$bundle = Join-Path $HOME ".copilot\tools\f2m\<release>\skills"
$skills = Join-Path $HOME ".copilot\skills"

foreach ($name in @("f2m-retrofit", "f2m-debug", "f2m-check")) {
  Copy-Item (Join-Path $bundle $name) (Join-Path $skills $name) -Recurse
}
```

Back up an existing skill directory before replacing it, and compare file counts or hashes after copying.

### Installation record on the destination computer (2026-10-23)

This supplements the earlier source-computer snapshot; it does not replace that historical record.

| Item | Recorded result |
|---|---|
| Source package | `D:\download\F2M_1.6.1\F2M_1.6.1` (the extracted directory has a nested folder) |
| Installed package | `%USERPROFILE%\.copilot\tools\f2m\1.6.1`; all 1,843 copied files matched source SHA-256 hashes |
| Global MCP configuration | `%USERPROFILE%\.copilot\mcp-config.json`; `f2m` uses the installed executable with empty `args` |
| Global skills | `f2m-retrofit`, `f2m-debug`, and `f2m-check`; all copied files matched the bundled versions |
| Startup and connection | `F2M_MCP.exe --help` succeeded; stdio initialization and discovery exposed 93 tools; the Copilot session's F2M tool call also succeeded |
| Release | `check_update` reported `current: 1.6.1`, `latest_for_you: 1.6.1`, and `up_to_date: true`; no update was performed |
| Python | Microsoft Store Python 3.12.10 ran successfully using the executable registered under `HKCU\Software\Python`; `py` was not available in the current terminal |
| Hardware | No serial-port scan, board connection, register access, or FPGA programming was performed |

F2M uses its bundled Python runtime and does not require the separately installed Python or `py` launcher. Do not mistake the MCP initialization `serverInfo.version` (`1.11.0` in this check) for the F2M release: use `check_update` for the release.

### Update F2M safely

Local preview installation on 2026-10-27: the user supplied
`%USERPROFILE%\Downloads\F2M_1.7.0a\F2M_1.7.0a`. The complete package was
installed separately at `%USERPROFILE%\.copilot\tools\f2m\1.7.0a`; all 1,925
package files matched the source copy. `f2m_release.json` identifies version
`1.7.0a`, channel `preview`, targeting `1.7.0`; do not call this a stable release
or infer that it is the server's latest generally available release.

The new executable successfully completed `--help` and an MCP initialization
and tools-list handshake. Its runtime instructions reported `F2M 1.7.0a` and
it exposed 96 tools. The three bundled global skills were updated together
(their manifests identify skill/specification version `1.7.0`, protocol `2.0`,
and JSON Schema `1.6`). The 1.6.1 installation was retained. Existing
`projects`, `shared`, and `.f2m_state.json` data were copied into the new
installation without changing external project files.

The previous MCP configuration and global skills are backed up under
`%USERPROFILE%\.copilot\backups\f2m-before-1.7.0a-20261027-091856`.
The global MCP command now points to the 1.7.0a executable; already-running
sessions may still use 1.6.1 until their F2M server is reloaded or the session
is restarted. Do not terminate another session's server during hardware work.
No FPGA compilation, programming, serial scanning, or register access was
performed during installation. When reverting, restore the old command and
matching skills; reconcile any newer user data before reverting the data
snapshot, rather than overwriting it.

Use F2M's `check_update` tool to identify the running version and available release. Do not infer the running version from the installation folder name because the built-in updater may upgrade files in place.

Only call `self_update(confirm=true)` after the user explicitly authorizes that specific update. The updater verifies the server-provided size and SHA-256, backs up changed files under `_update_backup\<old-version>`, and does not modify FPGA hardware.

After updating:

1. Run the installed `F2M_MCP.exe --help` once and wait for it to exit; endpoint security may delay the first launch.
2. Restart Copilot or reload the F2M MCP server.
3. Call `check_update` again and verify the reported version.
4. Confirm the expected tool count and newly listed tools.
5. Rebuild the FPGA bitstream separately if the release contains required RTL changes; host-tool updates do not reprogram hardware.

### F2M operating rules

- User RTL, register names, addresses, values, and design files stay local.
- Use `advise` only for general expert judgment that can be safely anonymized; use local tools and silicon reads for project-specific facts.
- Ask the user for facts only they know, such as board, device, intended transport, and physical meaning. Do not guess them.
- Use `f2m-retrofit` to add an F2M access layer, then run `f2m-check`.
- Use `f2m-debug` for board bring-up and debugging after the project and transport are established.
- Require explicit authorization before programming hardware or applying potentially hazardous actuation.

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

The MCP package requires Python 3.10 or newer. Use the default Python selected by the Windows `py` launcher instead of bare `python`. Resolve an absolute executable path only when a client or script cannot reliably launch `py`.

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

### Observed causes

Do not assume this dialog is always caused by the Microsoft Store alias. Check command resolution first. Known causes include:

1. a Microsoft Store `python.exe` application alias;
2. an extensionless file named `python` earlier in command resolution;
3. an MCP or generated PowerShell command that still invokes bare `python`;
4. a long-running process started before the configuration was corrected.

The verified issue on the source computer was a zero-byte extensionless file:

```text
C:\Windows\System32\python
```

PowerShell selected that file before the valid Python installations. Windows treated it as a document and repeatedly displayed:

```text
Select an app to open 'python'
```

### Diagnose before changing anything

Run:

```powershell
Get-Command python, python3, py -All |
  Select-Object Name, CommandType, Source, Path

$candidate = Get-Command python -ErrorAction SilentlyContinue
if ($candidate) {
  Get-Item -LiteralPath $candidate.Source -Force |
    Format-List FullName, Length, Attributes, CreationTime, LastWriteTime
}

py -c "import sys; print(sys.executable); print(sys.version)"
```

A valid `python.exe` appearing later in the list does not make bare `python` safe. The first selected candidate must itself be a real executable.

To find an already-running Copilot command that still contains bare `python`, run:

```powershell
Get-CimInstance Win32_Process |
  Where-Object {
    $_.CommandLine -match '(?i)([&|]\s*python\b|\bpython\s+-[cm])'
  } |
  Select-Object ProcessId, ParentProcessId, Name, CommandLine
```

Before terminating a process, identify its owning session and confirm that stopping it will not interrupt synthesis, programming, measurement, or another destructive operation.

### Preferred commands

If `py` is unavailable, inspect Python installation registrations under `HKCU\Software\Python` or `HKLM\Software\Python`. Read the selected installation's `ExecutablePath` value on its `InstallPath` key and verify that executable by absolute path with `-c "import sys; print(sys.executable); print(sys.version)"`. A Store-installed Python can be functional even when the `py` launcher is absent. Do not invoke an unverified alias or persist a versioned WindowsApps package path in portable configuration.

Use the Python launcher without fixing a minor version:

```text
py -m radiant_mcp
```

For generated PowerShell and Python scripts, use `py` instead of bare `python`:

```powershell
py -c "import sys; print(sys.executable)"
Get-Content .\script.py | py -
```

If a specific long-running workflow needs a stable interpreter, resolve and verify it first:

```powershell
$python = py -c "import sys; print(sys.executable)"
if (-not (Test-Path -LiteralPath $python -PathType Leaf)) {
  throw "Python executable not found: $python"
}
& $python -c "import sys; print(sys.executable)"
```

Use that resolved path in the current workflow. Do not copy a username-specific path or a path under `C:\Program Files\WindowsApps\...` into this portable document.

### Persistent AI-client prevention

Add this rule to the AI client's global instructions:

```text
On Windows, never invoke bare `python` or `python3`. Use `py`, or resolve and
verify the real executable with `py -c "import sys; print(sys.executable)"`.
```

Also inspect all active AI sessions. Correcting the MCP configuration does not rewrite commands that another session already started.

### Optional environment variables

Environment variables help installers and scripts that explicitly read them, but they do not automatically override an MCP client's `command` field.

```powershell
$python = py -c "import sys; print(sys.executable)"
[Environment]::SetEnvironmentVariable("PYTHON", $python, "User")
[Environment]::SetEnvironmentVariable("RADIANT_MCP_PYTHON", $python, "User")
```

Restart the AI client after changing user environment variables. If a client still launches `python`, edit that client's MCP config to use `py` with `-m` and `radiant_mcp`.

### Optional root-cause repair

If diagnosis finds an invalid extensionless file such as `C:\Windows\System32\python`, do not silently delete it. With explicit user approval and administrator rights:

1. verify that its size, owner, timestamp, and signature show that it is not a valid interpreter;
2. rename it to a unique backup name such as `python.invalid-backup`;
3. open a new terminal and verify `Get-Command python -All`;
4. run a known-safe Python version check;
5. delete the backup only after the user confirms the repair.

If the user does not approve modifying the system directory, leave the file unchanged and enforce `py` or a verified absolute executable in every AI client and script.

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

For F2M verification, call `check_update` and confirm the running release rather than trusting the directory name. List tools without scanning serial ports or accessing hardware.

For Python verification, start a new AI session and ask it to run a harmless version check. Confirm from the process command line or output that it used `py` or the verified executable, and that no app-selection dialog appeared. Do not use bare `python` as the verification command when the invalid system file remains in place.

## Source and update

Upstream repository:

```text
https://github.com/ayghri/i-have-adhd
```

Update an installation managed by the `skills` CLI:

```powershell
npx --yes skills update i-have-adhd -g
```

Other upstream sources recorded by this configuration:

```text
https://github.com/remotion-dev/skills
https://github.com/blader/humanizer
https://github.com/jgraph/drawio-desktop
```

This file is a portable configuration snapshot. If upstream behavior changes, review the new `skills/i-have-adhd/SKILL.md` before replacing these persistent preferences.
