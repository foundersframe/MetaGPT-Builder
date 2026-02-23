# METAGPT FILE MAP
## Architecture Reference

**Document Type:** Architecture Reference  
**Version:** 2.0 (GPT Optimization Update)  
**Last Updated:** 2025-02-09  
**Status:** Active

---

## DOCUMENT INVENTORY

### Files in MetaGPT Builder Project

| File | Type | Purpose | Upload To |
|------|------|---------|-----------|
| **Core Methodology Files (Universal)** ||||
| MASTER_METHODOLOGY_BRIEF.md | KB Document | Core methodology — chunked with metadata | Knowledge |
| METAGPT_BUILDER_USER_GUIDE.md | KB Document | New user onboarding, self-help | Knowledge |
| MAINTENANCE_SOP.md | KB Document | Update procedures (retrieval-isolated) | Knowledge |
| METAGPT_FILE_MAP.md | KB Document | This file — architecture reference | Knowledge |
| TEST_SUITE.md | Reference | Validation tests | Knowledge (optional) |
| CHANGELOG.md | KB Document | Version history | Knowledge |
| **Claude Project Files** ||||
| BASE_SYSTEM_PROMPT.md | Instructions | Universal behavioral layer | Instructions (1st) |
| PROJECT_PROMPT_METAGPT_BUILDER.md | Instructions | Project-specific behaviors | Instructions (2nd) |
| **Custom GPT Hybrid Architecture Files** ||||
| GPT_CORE_SYSTEM_PROMPT.md | Instructions | Core prompt (~7.5K chars) — essential behaviors | Instructions |
| BEHAVIORAL_PROTOCOLS.md | KB Document | Advanced behaviors — maintenance, error handling, self-help | Knowledge |
| GENERATION_PROCEDURES.md | KB Document | Content workflows — chunking, architecture, generation standards | Knowledge |
| TEMPLATE_LIBRARY.md | KB Document | Complete templates — system prompts, KB templates, metadata schemas | Knowledge |
| PLATFORM_GUIDES.md | KB Document | Build guidance for AI — platform selection, architecture generation | Knowledge |

### File Sizes (Approximate)

| File | Size | Chunks | Notes |
|------|------|--------|-------|
| MASTER_METHODOLOGY_BRIEF.md | ~18,000 words | ~70 | Core methodology |
| BASE_SYSTEM_PROMPT.md | ~2,500 words | — | Claude Projects only |
| PROJECT_PROMPT_METAGPT_BUILDER.md | ~3,500 words | — | Claude Projects only |
| GPT_CORE_SYSTEM_PROMPT.md | ~2,000 words | — | Custom GPTs only |
| BEHAVIORAL_PROTOCOLS.md | ~4,000 words | — | Custom GPTs hybrid |
| GENERATION_PROCEDURES.md | ~5,000 words | — | Custom GPTs hybrid |
| TEMPLATE_LIBRARY.md | ~6,000 words | — | Custom GPTs hybrid |
| PLATFORM_GUIDES.md | ~4,500 words | — | Custom GPTs hybrid |
| METAGPT_BUILDER_USER_GUIDE.md | ~4,500 words | — | Both platforms |
| MAINTENANCE_SOP.md | ~2,500 words | — | Both platforms |
| METAGPT_FILE_MAP.md | ~2,000 words | — | Both platforms |
| TEST_SUITE.md | ~3,000 words | — | Both platforms |
| CHANGELOG.md | Variable | — | Both platforms |

---

## CLAUDE PROJECT SETUP

### Instructions Field

Paste in this order:

```
1. [Paste entire contents of BASE_SYSTEM_PROMPT.md]

2. [Paste entire contents of PROJECT_PROMPT_METAGPT_BUILDER.md]
```

**Order matters.** Base prompt establishes universal behaviors; project prompt adds specifics.

### Knowledge Uploads

Upload these files:
1. MASTER_METHODOLOGY_BRIEF.md
2. METAGPT_BUILDER_USER_GUIDE.md
3. MAINTENANCE_SOP.md
4. METAGPT_FILE_MAP.md
5. CHANGELOG.md
6. TEST_SUITE.md (optional)

### Project Description

```
Build effective Custom GPTs and Claude Projects using a sophisticated knowledge architecture framework. Guides you through discovery, architecture design, document generation, and platform implementation.
```

---

## CUSTOM GPT SETUP

**Note:** Custom GPTs have an 8,000 character limit on Instructions. Uses hybrid architecture to maintain full sophistication.

### Instructions Field (Hybrid Architecture)

**Use GPT_CORE_SYSTEM_PROMPT.md only:**

```
[Paste entire contents of GPT_CORE_SYSTEM_PROMPT.md]
```

**Character count:** ~7,500 characters (safely under 8K limit)

**Contains:** Essential identity, discovery flow, KB retrieval protocols

### Knowledge Uploads (Critical for Functionality)

Upload in this recommended order:

1. **BEHAVIORAL_PROTOCOLS.md** (advanced behavioral systems)
2. **GENERATION_PROCEDURES.md** (content processing workflows)  
3. **TEMPLATE_LIBRARY.md** (templates and examples)
4. **PLATFORM_GUIDES.md** (implementation guidance)
5. **MASTER_METHODOLOGY_BRIEF.md** (core methodology)
6. **METAGPT_BUILDER_USER_GUIDE.md** (user guidance)
7. **MAINTENANCE_SOP.md** (update procedures)
8. **METAGPT_FILE_MAP.md** (architecture reference)
9. **CHANGELOG.md** (version history)
10. **TEST_SUITE.md** (optional)

### How Hybrid Architecture Works

- **Instructions Field:** Core behaviors that can't be retrieved mid-conversation
- **Knowledge Base:** Extended protocols retrieved as needed via instructions like:
  - "For maintenance mode → retrieve BEHAVIORAL_PROTOCOLS.md Section 3"
  - "For template generation → retrieve TEMPLATE_LIBRARY.md"

### Conversation Starters

```
- "I want to build a sophisticated AI project"
- "How does your hybrid architecture work?"  
- "Give me a complete system template"
- "Help me with platform optimization"
```

### Capabilities

- ✅ Web Browsing: Optional (for researching platforms)
- ❌ DALL-E: Not needed
- ✅ Code Interpreter: Recommended (for file processing)

### GPT Description

```
Build effective AI projects using sophisticated knowledge architecture. Platform-optimized hybrid architecture maintains full functionality within Custom GPT constraints. Guides discovery, architecture design, and implementation for both Claude Projects and Custom GPTs.
```

---

## FOLDER STRUCTURE

### Local Storage (Your Computer)

```
METAGPT_BUILDER/
│
├── Active/
│   ├── Core_Files/
│   │   ├── MASTER_METHODOLOGY_BRIEF.md
│   │   ├── METAGPT_BUILDER_USER_GUIDE.md
│   │   ├── MAINTENANCE_SOP.md
│   │   ├── METAGPT_FILE_MAP.md
│   │   ├── TEST_SUITE.md
│   │   └── CHANGELOG.md
│   │
│   ├── Claude_Project_Files/
│   │   ├── BASE_SYSTEM_PROMPT.md
│   │   └── PROJECT_PROMPT_METAGPT_BUILDER.md
│   │
│   └── Custom_GPT_Hybrid_Files/
│       ├── GPT_CORE_SYSTEM_PROMPT.md
│       ├── BEHAVIORAL_PROTOCOLS.md
│       ├── GENERATION_PROCEDURES.md
│       ├── TEMPLATE_LIBRARY.md
│       └── PLATFORM_GUIDES.md
│
├── Reference/
│   └── METAGPT_BUILDER_BLUEPRINT.md
│
└── Archives/
    └── [Quarterly snapshots]
```

### What Goes Where

| Location | Contents | Purpose |
|----------|----------|---------|
| Active/Core_Files/ | Universal files for both platforms | Used by both Claude Projects and Custom GPTs |
| Active/Claude_Project_Files/ | Full sophistication prompts | Only for Claude Projects (no character limits) |
| Active/Custom_GPT_Hybrid_Files/ | Hybrid architecture files | Only for Custom GPTs (works within 8K limit) |
| Reference/ | Blueprint, planning docs | Your reference, not uploaded |
| Archives/ | Dated backups | Safety net, not uploaded |

---

## DOCUMENT RELATIONSHIPS

### Retrieval Flow - Claude Projects

```
User Query
    │
    ▼
BASE_SYSTEM_PROMPT (behavioral rules)
    │
    ▼
PROJECT_PROMPT (task routing)
    │
    ▼
┌─────────────────────────────────────┐
│     MASTER_METHODOLOGY_BRIEF        │
│  ┌─────────────────────────────┐    │
│  │ Section 1-12 + Appendices   │◄───┼── Normal retrieval
│  └─────────────────────────────┘    │
└─────────────────────────────────────┘
    │
    ▼ (only if maintenance triggered)
┌─────────────────────────────────────┐
│        MAINTENANCE_SOP              │
└─────────────────────────────────────┘
```

### Retrieval Flow - Custom GPT Hybrid

```
User Query
    │
    ▼
GPT_CORE_SYSTEM_PROMPT (essential behaviors + KB retrieval protocols)
    │
    ▼
┌─────────────────────────────────────┐
│      KB DOCUMENT RETRIEVAL          │
│  ┌─────────────────────────────┐    │
│  │ BEHAVIORAL_PROTOCOLS.md     │◄───┼── For complex behaviors
│  │ GENERATION_PROCEDURES.md    │◄───┼── For content workflows
│  │ TEMPLATE_LIBRARY.md         │◄───┼── For templates
│  │ PLATFORM_GUIDES.md          │◄───┼── For implementation guidance
│  │ MASTER_METHODOLOGY_BRIEF    │◄───┼── For methodology content
│  └─────────────────────────────┘    │
└─────────────────────────────────────┘
```

### Cross-Reference Map

| Document | References | Referenced By | Platform |
|----------|------------|---------------|----------|
| **Core Files** ||||
| MASTER_METHODOLOGY_BRIEF | — | All system prompts | Both |
| METAGPT_BUILDER_USER_GUIDE | — | PROJECT_PROMPT, GPT_CORE | Both |
| MAINTENANCE_SOP | MASTER_METHODOLOGY_BRIEF | BASE_SYSTEM_PROMPT, BEHAVIORAL_PROTOCOLS | Both |
| **Claude Project Files** ||||
| BASE_SYSTEM_PROMPT | MASTER_METHODOLOGY_BRIEF, MAINTENANCE_SOP | PROJECT_PROMPT | Claude Only |
| PROJECT_PROMPT | MASTER_METHODOLOGY_BRIEF, USER_GUIDE | — | Claude Only |
| **Custom GPT Hybrid Files** ||||
| GPT_CORE_SYSTEM_PROMPT | All KB documents | — | GPT Only |
| BEHAVIORAL_PROTOCOLS | MASTER_METHODOLOGY_BRIEF, MAINTENANCE_SOP | GPT_CORE | GPT Only |
| GENERATION_PROCEDURES | MASTER_METHODOLOGY_BRIEF, TEMPLATE_LIBRARY | GPT_CORE | GPT Only |
| TEMPLATE_LIBRARY | MASTER_METHODOLOGY_BRIEF | GPT_CORE, GENERATION_PROCEDURES | GPT Only |
| PLATFORM_GUIDES | MASTER_METHODOLOGY_BRIEF | GPT_CORE | GPT Only |
| **Universal Files** ||||
| CHANGELOG | All documents | — | Both |
| TEST_SUITE | All documents | — | Both |

---

## VERSION TRACKING

### Current Versions

| Document | Version | Last Updated | Platform |
|----------|---------|--------------|----------|
| **Core Files (Universal)** ||||
| MASTER_METHODOLOGY_BRIEF.md | 2.0 | 2025-02-09 | Both |
| METAGPT_BUILDER_USER_GUIDE.md | 2.0 | 2025-02-09 | Both |
| MAINTENANCE_SOP.md | 2.0 | 2025-02-09 | Both |
| METAGPT_FILE_MAP.md | 2.0 | 2025-02-09 | Both |
| TEST_SUITE.md | 2.0 | 2025-02-09 | Both |
| CHANGELOG.md | 2.0 | 2025-02-09 | Both |
| **Claude Project Files** ||||
| BASE_SYSTEM_PROMPT.md | 1.0 | 2025-01-20 | Claude Only |
| PROJECT_PROMPT_METAGPT_BUILDER.md | 1.0 | 2025-01-20 | Claude Only |
| **Custom GPT Hybrid Files** ||||
| GPT_CORE_SYSTEM_PROMPT.md | 1.0 | 2025-02-09 | GPT Only |
| BEHAVIORAL_PROTOCOLS.md | 1.0 | 2025-02-09 | GPT Only |
| GENERATION_PROCEDURES.md | 1.0 | 2025-02-09 | GPT Only |
| TEMPLATE_LIBRARY.md | 1.0 | 2025-02-09 | GPT Only |
| PLATFORM_GUIDES.md | 1.0 | 2025-02-09 | GPT Only |

### Version Sync Rule

**When MASTER_METHODOLOGY_BRIEF.md updates:**
- Re-upload to both Claude Project and Custom GPT Knowledge
- Update CHANGELOG.md
- Update this file's version table

**When Claude Project prompts update:**
- Re-paste BASE_SYSTEM_PROMPT.md into Instructions (first)
- Re-paste PROJECT_PROMPT.md into Instructions (second)
- Update CHANGELOG.md
- Update this file's version table

**When Custom GPT hybrid files update:**
- Re-paste GPT_CORE_SYSTEM_PROMPT.md into Instructions
- Re-upload updated KB documents to Knowledge
- Verify character count still under 8,000
- Update CHANGELOG.md
- Update this file's version table

**When Universal files update:**
- Re-upload to both platform Knowledge sections
- Update CHANGELOG.md
- Update this file's version table

---

## MAINTENANCE TRIGGERS

### Layer 1 — Clear Triggers (Immediate Maintenance Mode)

- "update the methodology"
- "update the MetaGPT"
- "add to the methodology"
- "maintenance mode"
- "fix the builder"
- "the methodology is wrong"

### Layer 2 — User Content Signals (NEVER Trigger)

- "revise this [document]"
- "fix this [content]"
- "update this [draft]"
- Anything with "this" or "my" referring to user's work

### Layer 3 — Ambiguous (Ask Clarification First)

- "revise the project"
- "update the system"
- "fix an error"
- "something is wrong"

### Maintenance Mode Behavior

1. MAINTENANCE_SOP.md becomes retrievable
2. System shifts from build mode to update mode
3. Update classification procedures apply
4. Changes require confirmation before implementation

---

## RETRIEVAL ISOLATION

### Always Retrieved (Standard Mode)
- MASTER_METHODOLOGY_BRIEF.md (based on query relevance)
- METAGPT_FILE_MAP.md (if architecture questions)
- CHANGELOG.md (if version questions)

### Hybrid Architecture Retrieval (Custom GPT Only)
- **BEHAVIORAL_PROTOCOLS.md** (when complex behaviors needed)
- **GENERATION_PROCEDURES.md** (when content processing guidance needed)
- **TEMPLATE_LIBRARY.md** (when templates requested)
- **PLATFORM_GUIDES.md** (when implementation guidance needed)

### Never Retrieved (Unless Triggered)
- MAINTENANCE_SOP.md (only in maintenance mode)

### Retrieval Priorities by Query Type

| Query About | Priority Sections | Platform Notes |
|-------------|-------------------|----------------|
| How to use the Builder | USER_GUIDE | Both platforms |
| Getting started | MMB Section 1, 2 | Both platforms |
| Agent types | MMB Section 3 | Both platforms |
| System prompts | MMB Section 4, Appendix A + TEMPLATE_LIBRARY.md | GPT uses hybrid |
| Knowledge base design | MMB Section 5, 6, 7 | Both platforms |
| Multi-project systems | MMB Section 8, 11 | Both platforms |
| Maintenance | MMB Section 9, then MAINTENANCE_SOP + BEHAVIORAL_PROTOCOLS.md | GPT uses hybrid |
| Testing | MMB Section 10 + TEST_SUITE.md | Both platforms |
| Implementation | MMB Section 12, Appendix D + PLATFORM_GUIDES.md | GPT uses hybrid |
| Templates | MMB Appendix A + TEMPLATE_LIBRARY.md | GPT uses hybrid |
| Examples | MMB Appendix B | Both platforms |
| Platform differences | MMB Updated sections + PLATFORM_GUIDES.md | GPT uses hybrid |
| Character limits | PLATFORM_GUIDES.md + hybrid architecture docs | GPT specific |
| Hybrid architecture | BEHAVIORAL_PROTOCOLS.md + PLATFORM_GUIDES.md | GPT specific |

---

## QUICK SETUP CHECKLIST

### Claude Project (Full Sophistication)

- [ ] Create new project
- [ ] Set project name and description
- [ ] Paste BASE_SYSTEM_PROMPT.md into Instructions (first)
- [ ] Paste PROJECT_PROMPT_METAGPT_BUILDER.md into Instructions (second)
- [ ] Upload MASTER_METHODOLOGY_BRIEF.md to Knowledge
- [ ] Upload METAGPT_BUILDER_USER_GUIDE.md to Knowledge
- [ ] Upload MAINTENANCE_SOP.md to Knowledge
- [ ] Upload METAGPT_FILE_MAP.md to Knowledge
- [ ] Upload CHANGELOG.md to Knowledge
- [ ] Upload TEST_SUITE.md to Knowledge (optional)
- [ ] Test with: "How do you work?"
- [ ] Test with: "I want to build a GPT that helps with customer support"
- [ ] Verify self-help and discovery flows work properly

### Custom GPT (Hybrid Architecture)

- [ ] Create new GPT
- [ ] Set name and description (mention "Platform-optimized hybrid architecture")
- [ ] Paste GPT_CORE_SYSTEM_PROMPT.md into Instructions (verify under 8K chars)
- [ ] Upload BEHAVIORAL_PROTOCOLS.md to Knowledge (first)
- [ ] Upload GENERATION_PROCEDURES.md to Knowledge
- [ ] Upload TEMPLATE_LIBRARY.md to Knowledge
- [ ] Upload PLATFORM_GUIDES.md to Knowledge
- [ ] Upload MASTER_METHODOLOGY_BRIEF.md to Knowledge
- [ ] Upload METAGPT_BUILDER_USER_GUIDE.md to Knowledge
- [ ] Upload MAINTENANCE_SOP.md to Knowledge
- [ ] Upload METAGPT_FILE_MAP.md to Knowledge
- [ ] Upload CHANGELOG.md to Knowledge
- [ ] Upload TEST_SUITE.md to Knowledge (optional)
- [ ] Add conversation starters showcasing hybrid capabilities
- [ ] Configure capabilities (web browsing optional, code interpreter recommended, DALL-E off)
- [ ] Test hybrid functionality:
  - [ ] "I want to build a sophisticated AI project" (basic response)
  - [ ] "Help me with maintenance mode" (should retrieve BEHAVIORAL_PROTOCOLS.md)
  - [ ] "Give me a system prompt template" (should retrieve TEMPLATE_LIBRARY.md)
- [ ] Verify character count compliance and KB retrieval works

---

**END OF FILE MAP**
