# UNIFIED SYSTEM ARCHITECTURE ANALYSIS PROMPT
## Comprehensive Plugin & Modular Architecture Report Template

---

## TASK
Analyze the provided system/framework/application and produce a **comprehensive unified architecture report** that captures both:
1. **Plugin/Extension Architecture** - How the system enables extensibility
2. **Complete Modular Architecture** - Full module hierarchy with Core/Plugin/Support tiers

## INPUT
[Paste system documentation, codebase description, architecture docs, plugin guides, or project description here]

## OUTPUT REQUIREMENTS
Follow this exact template structure to produce ONE unified report containing all sections below.

---

# TEMPLATE: UNIFIED ARCHITECTURE ANALYSIS REPORT

## Title Format
# [SYSTEM_NAME]: Complete Architecture Analysis (Plugin System & Modular Structure)

---

# PART A: PLUGIN SYSTEM ARCHITECTURE

## Section A1: PLUGIN SYSTEM OVERVIEW

### A1.1 Architecture Summary

**System Type:** [Event-driven / Hook-based / Interface-based / Service-oriented]

**Plugin Discovery:** [How plugins are found: directory scanning / manifest registration / API registration]

**Loading Strategy:** [When plugins load: startup / lazy / on-demand]

**Isolation Level:** [Process-level / Namespace / Same-process / Sandboxed]

**Communication Pattern:** [Direct calls / Event bus / Message queue / RPC]

**Core-Plugin Boundary:** [What core controls vs what plugins control]

### A1.2 Plugin Lifecycle

**Lifecycle Stages:**
1. **Discovery** - [How system finds plugins]
2. **Validation** - [What checks happen before loading]
3. **Loading** - [How plugin code is initialized]
4. **Registration** - [How plugin declares capabilities]
5. **Activation** - [When plugin starts handling events/requests]
6. **Deactivation** - [How plugins are disabled/unloaded]
7. **Cleanup** - [Resource cleanup process]

**Lifecycle Events/Hooks:**
- `[event_name]` - [When it fires, what plugins can do]
- `[event_name]` - [Trigger and purpose]
- `[event_name]` - [Trigger and purpose]
- [Continue for all lifecycle events]

---

## Section A2: PLUGIN EXTENSION POINTS

### A2.1 Available Hooks/Events

Create a comprehensive table of all extension points:

| Hook/Event Name | Trigger Condition | Plugin Receives | Plugin Returns | Can Block? | Examples |
|-----------------|-------------------|-----------------|----------------|------------|----------|
| **[EventName]** | [When it fires] | [Input data] | [Output format] | Yes/No | [Use case] |
| **[EventName]** | [When it fires] | [Input data] | [Output format] | Yes/No | [Use case] |
| **[EventName]** | [When it fires] | [Input data] | [Output format] | Yes/No | [Use case] |
| [Continue for all hooks/events] |

### A2.2 Hook Priority & Ordering

**Execution Order Control:**
- [How plugins specify execution order: priority numbers / dependencies / registration order]
- [Default ordering strategy]
- [Conflict resolution when multiple plugins handle same hook]

**Examples:**
```[language]
[Show code example of setting plugin priority/order]
```

---

## Section A3: PLUGIN STRUCTURE & ANATOMY

### A3.1 Required Plugin Artifacts

**Mandatory Files:**
- `[filename]` - [Purpose and format]
- `[filename]` - [Purpose and format]
- `[filename]` - [Purpose and format]

**Optional Files:**
- `[filename]` - [Purpose and format]
- `[filename]` - [Purpose and format]

**Directory Structure:**
```
[plugin-name]/
├── [file1]          # [Purpose]
├── [file2]          # [Purpose]
├── [directory]/
│   └── [file3]      # [Purpose]
└── [file4]          # [Purpose]
```

### A3.2 Plugin Manifest/Descriptor

**Manifest Format:** [JSON / YAML / TOML / Code annotation]

**Required Fields:**
```[format]
{
  "[field]": "[purpose and type]",
  "[field]": "[purpose and type]",
  "[field]": "[purpose and type]"
}
```

**Example Real Manifest:**
```[format]
[Paste actual example from system]
```

### A3.3 Plugin Implementation Pattern

**Implementation Style:** [Class-based / Function-based / Declarative / Mixed]

**Minimal Plugin Example:**
```[language]
[Show smallest viable plugin that demonstrates the pattern]
```

**Full-Featured Plugin Example:**
```[language]
[Show plugin with multiple hooks, configuration, lifecycle methods]
```

---

## Section A4: PLUGIN CONTRACTS & INTERFACES

### A4.1 Core Contracts

For each major contract/interface:

#### Contract: **[InterfaceName]**

**Purpose:** [What this contract enables]

**Required Methods/Functions:**
```[language]
[method_signature](params) -> return_type  # [What it does]
[method_signature](params) -> return_type  # [What it does]
[method_signature](params) -> return_type  # [What it does]
```

**Input Schema:**
```json
{
  "field": "type and constraints",
  "field": "type and constraints"
}
```

**Output Schema:**
```json
{
  "field": "type and constraints",
  "field": "type and constraints"
}
```

**Validation Rules:**
- [Rule 1]
- [Rule 2]
- [Rule 3]

**Example Implementation:**
```[language]
[Show code implementing this contract]
```

[Repeat for each contract]

### A4.2 Communication Protocols

**Plugin → Core:**
- [How plugins call core functionality]
- [Available core APIs/services]
- [Permission model]

**Core → Plugin:**
- [How core invokes plugins]
- [Error handling strategy]
- [Timeout/resource limits]

**Plugin → Plugin:**
- [Can plugins communicate directly? How?]
- [Shared state mechanisms]
- [Event forwarding patterns]

---

## Section A5: PLUGIN CAPABILITIES & PERMISSIONS

### A5.1 Permission Model

**Permission Levels:**
- **[Level]**: [What it can access/modify]
- **[Level]**: [What it can access/modify]
- **[Level]**: [What it can access/modify]

**Capability Declarations:**
```[format]
[How plugins declare what they need]
```

**Restrictions:**
- ❌ [What plugins CANNOT do]
- ❌ [What plugins CANNOT do]
- ❌ [What plugins CANNOT do]

**Sandboxing/Isolation:**
- [Security boundaries]
- [Resource limits]
- [Blast radius control]

### A5.2 Core Services Available to Plugins

| Service | Purpose | Access Pattern | Permission Required |
|---------|---------|----------------|---------------------|
| **[ServiceName]** | [What it provides] | [How to call] | [Level needed] |
| **[ServiceName]** | [What it provides] | [How to call] | [Level needed] |
| **[ServiceName]** | [What it provides] | [How to call] | [Level needed] |

---

## Section A6: PLUGIN VALIDATION & QUALITY GATES

### A6.1 Pre-Load Validation

**Validation Checks:**
1. **[Check Name]** - [What it validates]
   - Pass criteria: [Requirements]
   - Fail action: [What happens]

2. **[Check Name]** - [What it validates]
   - Pass criteria: [Requirements]
   - Fail action: [What happens]

**Validation Tool/Command:**
```bash
[Command to validate a plugin]
```

### A6.2 Runtime Safety Mechanisms

**Error Isolation:**
- [How plugin failures are contained]
- [System recovery strategy]
- [Error reporting to core]

**Resource Limits:**
- Memory: [Limits and enforcement]
- CPU: [Limits and enforcement]
- Time: [Execution timeouts]
- I/O: [Rate limits or restrictions]

**Circuit Breakers:**
- [When plugins are auto-disabled]
- [Failure thresholds]
- [Recovery procedures]

---

## Section A7: PLUGIN CONFIGURATION & CUSTOMIZATION

### A7.1 Configuration System

**Configuration Sources:**
- [Where plugins read config: files / env vars / database / API]
- [Config precedence order]
- [Hot-reload support: Yes/No/Partial]

**Configuration Schema:**
```[format]
{
  "plugin_config": {
    "[field]": "[type and default]",
    "[field]": "[type and default]"
  }
}
```

**Example Plugin Config:**
```[format]
[Paste real example]
```

### A7.2 Plugin-Specific Customization

**Customization Points:**
- [How users customize plugin behavior]
- [Override mechanisms]
- [Extension of extensions (meta-plugins)]

**Templates/Scaffolding:**
```bash
[Command to generate plugin from template]
```

---

# PART B: COMPLETE MODULAR ARCHITECTURE

## Section B1: TIER 1: CORE MODULES (Sacred/Privileged)

For each core module, provide:

### Module N: **[Module Name]**

**Purpose:** [One-sentence description of what this module does]

**Deliverables:**
- `[filepath/component1]` - [Brief description]
- `[filepath/component2]` - [Brief description]
- `[filepath/component3]` - [Brief description]
- [Data files, configs, schemas created/managed]
- [Any generated artifacts]
- [Integration points or interfaces]

**Key Contracts:**
```python
# Show 3-5 key function/method signatures or API endpoints
method_name(param1: Type, param2: Type) -> ReturnType
another_method(param: Type) -> ReturnType

# Optional: Include schema examples if relevant
{
  "example": "data structure",
  "format": "that this module uses"
}
```

**Core Module Identification Criteria:**
- Controls privileged operations (file system, database, security)
- Cannot be disabled without breaking the system
- Other modules depend on it
- Handles critical data or state
- Enforces system-wide rules or policies

[Repeat for each core module - aim for 8-12 core modules]

---

## Section B2: TIER 2: PLUGIN/EXTENSION MODULES (Extensible/Evolvable)

For each plugin/extension module, provide:

### Module N: **[Module Name]**

**Purpose:** [What this plugin/extension accomplishes]

**Deliverables:**
- `[plugin files or components]`
- [Configuration files]
- [Templates or schemas]
- [Integration artifacts]

**[Hook/Event Name]:** [What triggers this module]

**Input Contract:**
```json
{
  "event": "[EventName]",
  "inputs": {
    "expected": "input structure",
    "parameters": "that trigger this module"
  }
}
```

**Output Contract:**
```json
[
  {
    "action": "action_name",
    "payload": {
      "returned": "data structure",
      "actions": "or proposals from this module"
    }
  }
]
```

**Plugin/Extension Identification Criteria:**
- Can be added/removed without breaking core
- Extends functionality rather than providing foundation
- Implements a specific feature or capability
- May have multiple implementations for same purpose
- Often user-configurable or optional

[Repeat for each plugin module - aim for 6-10 plugin modules]

---

## Section B3: TIER 3: SUPPORT MODULES

For each support module, provide:

### Module N: **[Module Name]**

**Purpose:** [What supporting function this provides]

**Deliverables:**
- `[utility files or components]`
- [Configuration data]
- [Supporting artifacts]

**Key Contracts (if applicable):**
```[language]
[method signatures or interface definitions]
```

**Support Module Identification Criteria:**
- Provides utilities or helpers
- Used by multiple other modules
- Not directly part of core functionality
- Often cross-cutting concerns (logging, config, testing)

[Repeat for each support module - aim for 3-6 support modules]

---

## Section B4: COMPLETE DELIVERABLES SUMMARY TABLE

Create a comprehensive table:

| Module | Core Files | Generated Artifacts | Config Files | Tests |
|--------|-----------|---------------------|--------------|-------|
| **[Module 1]** | [file1.ext, file2.ext] | [artifact1, artifact2] | [config.json] | [test_file.ext] |
| **[Module 2]** | [file1.ext] | [generated output] | - | [test_file.ext] |
| [Continue for all modules] |

---

## Section B5: MODULE DEPENDENCIES

Create a dependency tree showing relationships:

```
[Root Module/Orchestrator]
├── [Dependent Module 1] ([what it provides])
├── [Dependent Module 2] ([what it provides])
│   └── [Sub-dependency] ([relationship])
└── [Dependent Module 3] ([what it provides])

[Another Major Module]
├── [Dependencies]
└── [How they interact]

[Plugin Family]
├── [Shared dependencies]
└── [Integration points]
```

---

## Section B6: INTEGRATION POINTS

### External Tool Integration

**Tool Integrations:**
- **[Tool/Service Name]** - [How it's integrated and by which modules]
- **[Tool/Service Name]** - [Purpose and calling modules]
- **[Tool/Service Name]** - [Integration pattern]

### Data Flows

Describe 3-5 key scenarios showing data movement:

1. **[Scenario Name]**
   → [Step 1] → [Step 2] → [Step 3] → [Step 4] → [Final outcome]

2. **[Scenario Name]**
   → [Flow description with steps]

3. **[Scenario Name]**
   → [Flow description with steps]

---

# PART C: PLUGIN ECOSYSTEM & DEVELOPMENT

## Section C1: PLUGIN DEVELOPMENT WORKFLOW

### C1.1 Plugin Creation Process

**Step-by-Step:**
1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Step 4]

**Tools Required:**
- [Tool 1] - [Purpose]
- [Tool 2] - [Purpose]

**Scaffolding/Generators:**
```bash
[Commands to generate plugin boilerplate]
```

### C1.2 Testing & Debugging

**Testing Framework:**
- [How plugins are tested]
- [Test runner integration]
- [Mock/stub systems]

**Debugging Tools:**
- [Debugging capabilities]
- [Logging integration]
- [Error reporting]

**Test Example:**
```[language]
[Show plugin test example]
```

---

## Section C2: PLUGIN ECOSYSTEM

### C2.1 Official/Built-in Plugins

List of official plugins:

| Plugin Name | Purpose | Hooks Used | Stability |
|-------------|---------|------------|-----------|
| **[PluginName]** | [Purpose] | [Hooks] | [Stable/Beta/Experimental] |
| **[PluginName]** | [Purpose] | [Hooks] | [Status] |

### C2.2 Third-Party Plugin Support

**Distribution Channels:**
- [Where plugins are published]
- [Package management]
- [Installation process]

**Community Resources:**
- [Documentation portals]
- [Example repositories]
- [Support forums]

---

## Section C3: VERSIONING & COMPATIBILITY

### C3.1 API Versioning

**Version Strategy:**
- [How plugin API versions are managed]
- [Breaking change policy]
- [Deprecation process]

**Compatibility Matrix:**

| Core Version | Plugin API Version | Compatible With |
|--------------|-------------------|------------------|
| [version] | [version] | [What changed] |

### C3.2 Migration Guides

**Upgrade Paths:**
- [How to migrate plugins between versions]
- [Breaking changes documentation]
- [Automated migration tools]

---

# PART D: ARCHITECTURAL ANALYSIS

## Section D1: PLUGIN ARCHITECTURE STRENGTHS & WEAKNESSES

### D1.1 Architectural Strengths

✅ **[Strength 1]**
   - Why it's good: [Explanation]
   - Example: [How it manifests]

✅ **[Strength 2]**
   - Why it's good: [Explanation]
   - Example: [How it manifests]

✅ **[Strength 3]**
   - Why it's good: [Explanation]
   - Example: [How it manifests]

### D1.2 Architectural Limitations

⚠️ **[Limitation 1]**
   - Why it's limiting: [Explanation]
   - Workaround: [If any]

⚠️ **[Limitation 2]**
   - Why it's limiting: [Explanation]
   - Workaround: [If any]

⚠️ **[Limitation 3]**
   - Why it's limiting: [Explanation]
   - Workaround: [If any]

### D1.3 Design Tradeoffs

**Flexibility vs. Performance:**
- [How this system balances]

**Safety vs. Capability:**
- [Restrictions and rationale]

**Simplicity vs. Power:**
- [Learning curve vs features]

---

## Section D2: COMPARATIVE METRICS

### D2.1 Plugin System Characteristics

| Characteristic | Rating (1-5) | Notes |
|----------------|--------------|-------|
| **Ease of Plugin Creation** | ⭐⭐⭐⭐⭐ | [Brief explanation] |
| **Extensibility Breadth** | ⭐⭐⭐⭐⭐ | [How many extension points] |
| **Safety/Isolation** | ⭐⭐⭐⭐⭐ | [How well plugins are sandboxed] |
| **Performance Overhead** | ⭐⭐⭐⭐⭐ | [Impact on system performance] |
| **Documentation Quality** | ⭐⭐⭐⭐⭐ | [Plugin dev docs completeness] |
| **Developer Experience** | ⭐⭐⭐⭐⭐ | [Tools, debugging, testing] |
| **Plugin Ecosystem Size** | ⭐⭐⭐⭐⭐ | [Number of available plugins] |

### D2.2 Complexity Analysis

**Lines of Code for "Hello World" Plugin:** [Number]

**Number of Required Artifacts:** [Number]

**Number of Extension Points:** [Number]

**Learning Curve:** [Beginner / Intermediate / Advanced]

**Time to First Plugin:** [Estimate in hours/days]

---

## Section D3: MODULAR ARCHITECTURE QUALITY ASSESSMENT

Evaluate the overall modular architecture:

**This modular architecture ensures:**

- ✅/❌ Clear separation of concerns
- ✅/❌ Each module has single responsibility
- ✅/❌ Core protected from plugin failures
- ✅/❌ Extensibility without core changes
- ✅/❌ Complete audit/observability capability
- ✅/❌ Deterministic and testable behavior
- ✅/❌ Well-defined module boundaries
- ✅/❌ Manageable dependencies (no circular deps)
- ✅/❌ Consistent interface contracts
- ✅/❌ Scalable architecture for growth

---

## Section D4: KEY TAKEAWAYS & PATTERNS

### D4.1 Core Architectural Patterns

1. **[Pattern Name]**
   - Description: [How it works]
   - Benefits: [Why it's used]
   - Trade-offs: [Costs]

2. **[Pattern Name]**
   - Description: [How it works]
   - Benefits: [Why it's used]
   - Trade-offs: [Costs]

3. **[Pattern Name]**
   - Description: [How it works]
   - Benefits: [Why it's used]
   - Trade-offs: [Costs]

### D4.2 Reusable Design Decisions

**Decisions Worth Borrowing:**
- ✅ [Decision] - [Why it's good, how to apply elsewhere]
- ✅ [Decision] - [Why it's good, how to apply elsewhere]
- ✅ [Decision] - [Why it's good, how to apply elsewhere]

**Decisions to Avoid:**
- ❌ [Decision] - [Why it's problematic, better alternatives]
- ❌ [Decision] - [Why it's problematic, better alternatives]

---

## Section D5: CROSS-SYSTEM COMPARISON MATRIX

(Use this when analyzing multiple systems for comparison)

| Aspect | [System A] | [System B] | [System C] |
|--------|-----------|-----------|-----------|
| **Discovery Method** | [Method] | [Method] | [Method] |
| **Loading Strategy** | [Strategy] | [Strategy] | [Strategy] |
| **Isolation Level** | [Level] | [Level] | [Level] |
| **Extension Points** | [Count] | [Count] | [Count] |
| **Permission Model** | [Type] | [Type] | [Type] |
| **Plugin Language** | [Lang] | [Lang] | [Lang] |
| **Validation Approach** | [Approach] | [Approach] | [Approach] |
| **Configuration System** | [Type] | [Type] | [Type] |
| **Core Modules** | [Count] | [Count] | [Count] |
| **Plugin Modules** | [Count] | [Count] | [Count] |
| **Developer Tools** | [Tools] | [Tools] | [Tools] |
| **Ecosystem Size** | [Size] | [Size] | [Size] |

---

# ANALYSIS GUIDELINES

## 1. Module Identification Strategy

**Start with data flow:** Follow how data enters, transforms, and exits

**Identify boundaries:** Look for clear interfaces or APIs

**Find privileged operations:** What requires special access?

**Spot extensibility points:** Where can users add functionality?

**Look for separation patterns:** Services, layers, plugins, adapters

## 2. Classification Rules

- **CORE** = Can't remove without system collapse
- **PLUGIN** = Optional, adds features, follows extension pattern
- **SUPPORT** = Utilities, helpers, cross-cutting concerns

## 3. Plugin Architecture Focus

- How plugins are discovered, loaded, and managed
- What extension points exist and their contracts
- How plugins interact with core and each other
- Safety and isolation mechanisms
- Developer experience and tooling

## 4. Deliverables Extraction

- Code files: Actual implementation files with paths
- Generated artifacts: What the module creates/manages
- Configs: What settings it reads/writes
- Tests: Verification components
- Schemas: Data structures or contracts

## 5. Contract Documentation

- Show 3-5 most important interfaces per module
- Use actual code syntax (Python, TypeScript, etc.) or pseudocode
- Include parameter types and return types
- For REST APIs: show endpoint signatures
- For event-driven: show event names and payloads

## 6. Evidence Requirements

For each claim, provide:
- Code examples from actual plugins or documentation
- Command examples showing real usage
- Schema/contract examples with actual formats
- Links to official documentation (if available)

## 7. Maintain Consistency

- Use same naming conventions throughout
- Keep module numbering sequential
- Use consistent formatting for code blocks
- Apply same level of detail to each module
- Use ✅/❌/⚠️/⭐ symbols consistently

## 8. Integration Focus

- Show how modules interact, not just what they do
- Identify data flows between modules
- Highlight external dependencies
- Note any circular dependencies (architectural smell)

## 9. When Information is Missing

If you cannot find specific information:

**[Section Name]:** ⚠️ Not documented / Not found in provided materials

*Inference based on related patterns:* [Your educated guess]
*Recommendation:* [What to look for to complete this section]

---

# OUTPUT CHECKLIST

Before submitting your analysis, verify:

**Part A - Plugin Architecture:**
- [ ] All 7 plugin sections completed (A1-A7)
- [ ] Extension points fully documented with I/O contracts
- [ ] Plugin lifecycle clearly explained
- [ ] Permission model documented
- [ ] Validation/safety mechanisms described
- [ ] At least 2 complete plugin examples provided

**Part B - Modular Architecture:**
- [ ] All modules numbered sequentially across tiers
- [ ] Each module has Purpose + Deliverables + Contracts
- [ ] Core/Plugin/Support tiers clearly separated
- [ ] Summary table includes all modules
- [ ] Dependency tree shows relationships
- [ ] 3-5 data flow scenarios described

**Part C - Plugin Ecosystem:**
- [ ] Development workflow documented
- [ ] Testing/debugging approaches described
- [ ] Plugin catalog provided
- [ ] Versioning strategy explained

**Part D - Architectural Analysis:**
- [ ] Strengths and weaknesses honestly assessed
- [ ] Comparative metrics table filled
- [ ] Quality assessment completed
- [ ] Key patterns identified

**General:**
- [ ] Consistent formatting throughout
- [ ] All code blocks properly formatted with syntax highlighting
- [ ] At least 3 real code examples included
- [ ] Integration points documented
- [ ] No section marked as "TBD" or incomplete

---

# NOW ANALYZE THIS SYSTEM:

[PASTE SYSTEM DOCUMENTATION, ARCHITECTURE DESCRIPTION, PLUGIN GUIDES, OR PROJECT DETAILS HERE]

**System Name:** [Name of system you're analyzing]

**Version/Date:** [If relevant]

**Documentation Links:** [If you have specific URLs to reference]

**Analysis Focus:** [Any specific areas you want emphasized]

---

# END OF UNIFIED TEMPLATE

---

## Usage Instructions

1. **Copy the entire template** from "TASK" to "END OF UNIFIED TEMPLATE"
2. **Paste into your AI conversation**
3. **Replace the [PASTE SYSTEM...] section** with your target system's documentation, architecture guides, plugin documentation, and any relevant materials
4. **Specify system details** (name, version, documentation links)
5. **Run the analysis**
6. **Review the comprehensive unified report**

## Tips for Best Results

- **Provide comprehensive input**: Include both high-level architecture docs AND detailed plugin/extension guides
- **Specify system characteristics**: "event-driven plugin system", "modular microservices", "extensible framework"
- **Include scale info**: Helps AI understand which modules are truly "core" vs "plugin"
- **Mention existing plugins**: List known plugins or extensions if documenting an existing system
- **Request clarification**: If output is unclear, ask AI to explain module boundaries or plugin contracts
- **Iterate**: Run 2-3 times with refined input for best results
- **Compare systems**: Use this template on multiple systems to generate comparison data

## Multi-System Comparison Workflow

To compare multiple architectures:

1. Run this analysis on **System A** → Save as `system_a_unified_analysis.md`
2. Run this analysis on **System B** → Save as `system_b_unified_analysis.md`
3. Run this analysis on **System C** → Save as `system_c_unified_analysis.md`
4. Generate comparison report using Section D5 data from each analysis

---

## What This Unified Template Produces

This template creates a **single comprehensive report** that includes:

✅ **Complete plugin system documentation** (lifecycle, hooks, contracts, validation)
✅ **Full modular architecture breakdown** (Core/Plugin/Support tiers)
✅ **Detailed deliverables per module** (files, artifacts, configs)
✅ **Plugin development workflow** (creation, testing, debugging)
✅ **Ecosystem analysis** (official plugins, third-party support)
✅ **Architectural quality assessment** (strengths, limitations, patterns)
✅ **Comparative metrics** (for cross-system analysis)
✅ **Complete integration mapping** (dependencies, data flows, external tools)

This unified approach ensures you capture **both the extensibility mechanisms (plugins) AND the complete structural organization (modules)** in a single, coherent architectural analysis.
