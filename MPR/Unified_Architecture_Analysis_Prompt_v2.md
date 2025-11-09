# UNIFIED SYSTEM ARCHITECTURE ANALYSIS PROMPT
## Comprehensive README‑First, Modular‑Before‑Plugin Report Template

---

## TASK
Analyze the provided system/framework/application and produce **one unified architecture report** in this order:
1. **README.md** — Ensure a usable repository entry point (use existing README or create one if missing)
2. **Modular Architecture** — Complete module hierarchy with Core/Plugin/Support tiers
3. **Plugin Architecture** — Extensibility model, lifecycle, hooks, and contracts

## INPUT
[Paste system documentation, codebase description, architecture docs, plugin guides, or project description here]

## OUTPUT REQUIREMENTS
Follow this exact section order and structure. If the repository lacks `README.md`, create it as part of the report.

---

# TEMPLATE: UNIFIED ARCHITECTURE ANALYSIS REPORT

## Title Format
# [SYSTEM_NAME]: Complete Architecture Analysis (Modular Structure & Plugin System)

---

# PART R: README.md (Repository Entry Point)

> **Goal:** Use the current `README.md` in the repository as the canonical entry point. If `README.md` does not exist, **author one** that accurately reflects the system as analyzed below.

### R1. README Source & Status
- **Repo Path:** `[path to repo root or URL]`
- **README.md Exists?** `[Yes/No]`
- **If No:** Create a new README in this report and mark as **Proposed README.md**.

### R2. Minimum Required README Contents
Include (or confirm presence of) the following blocks:
- **System Overview:** 2–4 sentences (what it is, who it’s for, scope)
- **Architecture at a Glance:** One diagram or bullet map (Core, Plugin, Support)
- **Quickstart:** install + run + test (copy/paste ready commands)
- **Repository Guide:** folders, config, scripts, CI status (badges optional)
- **Extensibility Overview:** how plugins are discovered, configured, and tested (link to Plugin section)
- **Versioning & Docs:** link to docs site (if any), SemVer policy, CHANGELOG/ledger
- **Security & Policies:** least‑privilege note, telemetry/logging, contribution guidelines

### R3. Proposed README.md (only if missing or insufficient)
```markdown
# [SYSTEM_NAME]
[One‑paragraph overview.]

## Architecture at a Glance
- **Core:** [brief]
- **Plugins:** [brief]
- **Support:** [brief]

## Quickstart
```bash
[install commands]
[run commands]
[test commands]
```

## Repository Guide
```
[repo root]/
├─ src/                 # core & modules
├─ plugins/             # extension modules
├─ docs/                # architecture docs, specs
├─ tests/               # unit & integration tests
└─ tools/               # dev scripts and helpers
```

## Extensibility
- Discovery: [how]
- Loading: [when]
- Contracts: [link to interfaces]
- Validation: [how to validate]

## Versioning & Docs
- SemVer policy: [link/summary]
- Changelog/Ledger: [path]
- Docs: [URL or path]

## Security & Policies
- Permissions model summary
- Telemetry/logging overview
- Contribution guidelines
```

> If a README already exists, **do not overwrite**; instead, include a **diff‑style checklist** of missing items (by section) and suggested patches.

---

# PART A: COMPLETE MODULAR ARCHITECTURE (Tiered Overview)

## Section A1: TIER 1 — CORE MODULES (Sacred/Privileged)

For each core module, provide:

### Module N: **[Module Name]**
**Purpose:** [One‑sentence description]

**Deliverables:**
- `[filepath/component1]` — [Brief description]
- `[filepath/component2]` — [Brief description]
- `[filepath/component3]` — [Brief description]
- [Data files, configs, schemas created/managed]
- [Generated artifacts]
- [Integration points or interfaces]

**Key Contracts:**
```python
# 3–5 critical functions/methods or API endpoints
method_name(param1: Type, param2: Type) -> ReturnType
another_method(param: Type) -> ReturnType
```

**Core Module Identification Criteria:**
- Privileged ops (filesystem, secrets, DB, security)
- Removing it breaks the system
- Other modules depend on it
- Handles critical state/data
- Enforces global rules/policies

[Repeat for ~8–12 core modules]

---

## Section A2: TIER 2 — PLUGIN/EXTENSION MODULES (Extensible/Evolvable)

### Module N: **[Module Name]**
**Purpose:** [What this plugin/extension accomplishes]

**Deliverables:**
- `[plugin files/components]`
- [Configuration files]
- [Templates/schemas]
- [Integration artifacts]

**Trigger/Hook:** **[Hook/Event Name]** — [What triggers it]

**Input Contract:**
```json
{
  "event": "[EventName]",
  "inputs": { "expected": "structure", "parameters": "..." }
}
```

**Output Contract:**
```json
[
  { "action": "action_name", "payload": { "returned": "data" } }
]
```

**Identification Criteria:**
- Optional, extendable, replaceable
- Implements a specific capability
- Multiple implementations possible
- User‑configurable

[Repeat for ~6–10 plugin modules]

---

## Section A3: TIER 3 — SUPPORT MODULES (Cross‑Cutting)

### Module N: **[Module Name]**
**Purpose:** [Utility/supporting function]

**Deliverables:**
- `[utility files/components]`
- [Config data]
- [Supporting artifacts]

**Key Contracts (if applicable):**
```[language]
[method signatures or interfaces]
```

**Identification Criteria:**
- Utilities/helpers used widely
- Not part of core domain logic
- Logging, config, testing, scaffolding

[Repeat for ~3–6 support modules]

---

## Section A4: DELIVERABLES SUMMARY TABLE
| Module | Core Files | Generated Artifacts | Config Files | Tests |
|--------|------------|---------------------|--------------|-------|
| **[Module 1]** | [file1, file2] | [artifact1, artifact2] | [config.json] | [test.ext] |
| **[Module 2]** | [file] | [output] | - | [test.ext] |
| … | … | … | … | … |

---

## Section A5: MODULE DEPENDENCIES (Tree)
```
[Root/Orchestrator]
├─ [Dependent Module 1] (provides …)
├─ [Dependent Module 2] (provides …)
│  └─ [Sub‑dependency] (relationship)
└─ [Dependent Module 3] (provides …)

[Plugin Family]
├─ [Shared deps]
└─ [Integration points]
```

---

## Section A6: INTEGRATION POINTS & DATA FLOWS

**External Tool Integration**
- **[Tool/Service]** — [Integrated by modules X/Y], [pattern]
- **[Tool/Service]** — [Purpose], [caller modules]
- **[Tool/Service]** — [Auth/IO/limits]

**Data Flows** (3–5 scenarios)
1. **[Scenario]** → [Step 1] → [Step 2] → [Step 3] → [Outcome]
2. **[Scenario]** → [Flow steps]
3. **[Scenario]** → [Flow steps]

---

# PART B: PLUGIN SYSTEM ARCHITECTURE (Extensibility Model)

## Section B1: OVERVIEW

**System Type:** [Event‑driven / Hook‑based / Interface‑based / Service‑oriented]  
**Plugin Discovery:** [Directory scan / Manifest / API registration]  
**Loading Strategy:** [Startup / Lazy / On‑demand]  
**Isolation Level:** [Process / Namespace / Same‑process / Sandboxed]  
**Communication Pattern:** [Direct / Event bus / MQ / RPC]  
**Core‑Plugin Boundary:** [Core controls X; plugins control Y]

## Section B2: PLUGIN LIFECYCLE

**Stages:**
1. **Discovery** — [how found]
2. **Validation** — [checks]
3. **Loading** — [init procedure]
4. **Registration** — [declare capabilities]
5. **Activation** — [start handling]
6. **Deactivation** — [disable/unload]
7. **Cleanup** — [resource disposal]

**Lifecycle Events/Hooks:**
- `[event_name]` — [when & purpose]
- `[event_name]` — [when & purpose]
- …

## Section B3: EXTENSION POINTS (Hooks/Events)

| Hook/Event | Trigger | Plugin Receives | Plugin Returns | Can Block? | Examples |
|------------|---------|-----------------|----------------|------------|----------|
| **[Event]** | [When] | [Input] | [Output] | Yes/No | [Use case] |
| **[Event]** | [When] | [Input] | [Output] | Yes/No | [Use case] |
| … | … | … | … | … | … |

**Priority & Ordering**
- Control: [priority numbers / dependency graph / registration order]
- Default ordering: [rule]
- Conflict resolution: [tie‑breaks]
```[language]
# Example: setting priority
register(plugin, hook="on_event", priority=20)
```

## Section B4: PLUGIN STRUCTURE & MANIFEST

**Required Artifacts**
- `[filename]` — [purpose]
- `[filename]` — [purpose]

**Directory Layout**
```
[plugin-name]/
├─ [file1]   # [purpose]
├─ [file2]   # [purpose]
└─ [dir]/
   └─ [file] # [purpose]
```

**Manifest Format:** [JSON / YAML / TOML / Annotations]

**Required Fields:**
```[format]
{
  "[field]": "[purpose and type]",
  "[field]": "[purpose and type]"
}
```

**Minimal Plugin Example:**
```[language]
[Smallest viable plugin]
```

**Full‑Featured Example:**
```[language]
[Multiple hooks + config + lifecycle]
```

## Section B5: CONTRACTS, PERMISSIONS & CORE SERVICES

**Core Contracts per Interface**
```[language]
# InterfaceName
method(params) -> return  # purpose
```

**Communication Protocols**
- **Plugin → Core:** APIs/services, permissions
- **Core → Plugin:** invocation, errors, timeouts
- **Plugin → Plugin:** direct comms? shared state?

**Permission Model**
- Levels & scopes
- Capability declarations
- Restrictions (❌ do‑nots)
- Sandboxing/isolation & resource limits

**Core Services Table**
| Service | Purpose | Access Pattern | Permission |
|---------|---------|----------------|------------|
| **[Service]** | [What it provides] | [How to call] | [Level] |
| **[Service]** | [What it provides] | [How to call] | [Level] |

## Section B6: VALIDATION & RUNTIME SAFETY

**Pre‑Load Validation**
1. **[Check]** — pass criteria / fail action
2. **[Check]** — pass criteria / fail action
```bash
[validation command]
```

**Runtime Safety**
- Error isolation & recovery
- Resource limits (CPU, memory, time, I/O)
- Circuit breakers (thresholds, auto‑disable, recovery)

## Section B7: CONFIGURATION & CUSTOMIZATION

**Config Sources & Precedence:** [files/env/db/API], hot‑reload [Y/N]  
**Config Schema:**
```[format]
{ "plugin_config": { "[field]": "[type, default]" } }
```
**Customization Points:** overrides, meta‑plugins  
**Scaffolding:**
```bash
[command to scaffold plugin]
```

---

# PART C: PLUGIN ECOSYSTEM & DEVELOPMENT

## Section C1: DEVELOPMENT WORKFLOW
- **Creation steps** (scaffold → implement → register → validate → test)
- **Tools** used for build/test/packaging
```bash
[generator commands]
```

## Section C2: ECOSYSTEM
- **Official/Built‑in Plugins** (name, purpose, hooks, stability)
- **3rd‑Party Distribution** (channels, packaging, install)
- **Community Resources** (docs, examples, forums)

## Section C3: VERSIONING & COMPATIBILITY
- API versioning strategy, breaking change policy, deprecation
- Compatibility matrix and migration guides

---

# PART D: ARCHITECTURAL ANALYSIS

## Section D1: STRENGTHS, LIMITATIONS & TRADEOFFS
- ✅ Strengths (with examples)
- ⚠️ Limitations (with workarounds)
- Tradeoffs: flexibility vs performance, safety vs capability, simplicity vs power

## Section D2: COMPARATIVE METRICS
| Characteristic | Rating (1–5) | Notes |
|----------------|--------------|-------|
| Ease of Plugin Creation | ⭐⭐⭐⭐⭐ | [notes] |
| Extensibility Breadth | ⭐⭐⭐⭐⭐ | [notes] |
| Safety/Isolation | ⭐⭐⭐⭐⭐ | [notes] |
| Performance Overhead | ⭐⭐⭐⭐⭐ | [notes] |
| Documentation Quality | ⭐⭐⭐⭐⭐ | [notes] |
| Developer Experience | ⭐⭐⭐⭐⭐ | [notes] |
| Plugin Ecosystem Size | ⭐⭐⭐⭐⭐ | [notes] |

**Complexity**
- Hello‑world plugin LOC: [#]
- Required artifacts: [#]
- Extension points: [#]
- Learning curve: [Beginner/Intermediate/Advanced]
- Time to first plugin: [hours/days]

## Section D3: MODULAR ARCHITECTURE QUALITY CHECK
- ✅/❌ Separation of concerns; single responsibility
- ✅/❌ Core protected from plugin failures
- ✅/❌ Extensibility without core changes
- ✅/❌ Audit/observability completeness
- ✅/❌ Deterministic & testable behavior
- ✅/❌ Well‑defined boundaries; no circular deps
- ✅/❌ Consistent contracts; scalable design

## Section D4: PATTERNS & DECISIONS
- Core patterns used (e.g., Ports & Adapters, Event Bus, Policy Objects)
- Reusable decisions (✅ keep) and anti‑patterns (❌ avoid)

## Section D5: CROSS‑SYSTEM COMPARISON MATRIX
| Aspect | [System A] | [System B] | [System C] |
|--------|------------|------------|------------|
| Discovery | [Method] | [Method] | [Method] |
| Loading | [Strategy] | [Strategy] | [Strategy] |
| Isolation | [Level] | [Level] | [Level] |
| Extension Points | [Count] | [Count] | [Count] |
| Permission Model | [Type] | [Type] | [Type] |
| Plugin Language | [Lang] | [Lang] | [Lang] |
| Validation | [Approach] | [Approach] | [Approach] |
| Configuration | [Type] | [Type] | [Type] |
| Core Modules | [Count] | [Count] | [Count] |
| Plugin Modules | [Count] | [Count] | [Count] |
| Developer Tools | [Tools] | [Tools] | [Tools] |
| Ecosystem Size | [Size] | [Size] | [Size] |

---

# ANALYSIS GUIDELINES (unchanged logic, README‑first emphasis)

- Start with **README.md** discovery; create a proposed README if missing.
- Classify modules: **CORE** (irremovable), **PLUGIN** (optional/extendable), **SUPPORT** (cross‑cutting).
- Document contracts with concrete signatures and schemas.
- Show integration/data flows, not just inventories.
- Provide evidence: code snippets, commands, schema fragments, and doc links.

---

# OUTPUT CHECKLIST (updated order)

**README.md**
- [ ] Existing README audited OR new README proposed
- [ ] Quickstart, Architecture map, Extensibility overview, Versioning/Docs, Security/Policies included

**Part A — Modular Architecture**
- [ ] Core/Plugin/Support modules enumerated with Purpose/Deliverables/Contracts
- [ ] Summary table complete
- [ ] Dependency tree drawn
- [ ] 3–5 data flows described

**Part B — Plugin Architecture**
- [ ] Lifecycle, hooks, ordering, manifests, contracts
- [ ] Permissions & core services documented
- [ ] Validation & runtime safety described
- [ ] Config/customization & scaffolding covered
- [ ] At least 2 plugin examples

**Part C — Ecosystem & Dev Workflow**
- [ ] Build/test/debug workflow
- [ ] Official/3rd‑party plugin catalog
- [ ] Versioning & migration strategy

**Part D — Architectural Analysis**
- [ ] Strengths/limitations/tradeoffs
- [ ] Comparative metrics
- [ ] Modular quality checklist
- [ ] Patterns & cross‑system matrix

---

# NOW ANALYZE THIS SYSTEM:

**System Name:** [Name]  
**Version/Date:** [If relevant]  
**Documentation Links:** [URLs]  
**Analysis Focus:** [Areas to emphasize]

---

# END OF UNIFIED TEMPLATE

## Usage Tips
- Provide both high‑level docs **and** plugin/extension guides.
- Include scale info so module “core vs plugin” is clear.
- List known plugins to bootstrap Section C.
- Iterate: refine inputs to improve the report.
