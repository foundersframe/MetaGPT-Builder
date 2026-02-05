# METAGPT FILE MAP
## Architecture Reference

**Document Type:** Architecture Reference  
**Version:** 1.0  
**Last Updated:** 2025-01-20  
**Status:** Active

---

## DOCUMENT INVENTORY

### Files in MetaGPT Builder Project

| File | Type | Purpose | Upload To |
|------|------|---------|-----------|
| MASTER_METHODOLOGY_BRIEF.md | KB Document | Core methodology — chunked with metadata | Knowledge |
| BASE_SYSTEM_PROMPT.md | Instructions | Universal behavioral layer | Instructions (1st) |
| PROJECT_PROMPT_METAGPT_BUILDER.md | Instructions | Project-specific behaviors | Instructions (2nd) |
| METAGPT_BUILDER_USER_GUIDE.md | KB Document | New user onboarding, self-help | Knowledge |
| MAINTENANCE_SOP.md | KB Document | Update procedures (retrieval-isolated) | Knowledge |
| METAGPT_FILE_MAP.md | KB Document | This file — architecture reference | Knowledge |
| TEST_SUITE.md | Reference | Validation tests | Knowledge (optional) |
| CHANGELOG.md | KB Document | Version history | Knowledge |

### File Sizes (Approximate)

| File | Size | Chunks |
|------|------|--------|
| MASTER_METHODOLOGY_BRIEF.md | ~18,000 words | ~70 |
| BASE_SYSTEM_PROMPT.md | ~2,500 words | — |
| PROJECT_PROMPT_METAGPT_BUILDER.md | ~3,500 words | — |
| METAGPT_BUILDER_USER_GUIDE.md | ~4,500 words | — |
| MAINTENANCE_SOP.md | ~2,500 words | — |
| METAGPT_FILE_MAP.md | ~1,000 words | — |
| TEST_SUITE.md | ~2,500 words | — |
| CHANGELOG.md | Variable | — |

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

### Instructions Field

Combine both prompts into single field:

```
[Paste entire contents of BASE_SYSTEM_PROMPT.md]

---

[Paste entire contents of PROJECT_PROMPT_METAGPT_BUILDER.md]
```

### Knowledge Uploads

Same as Claude Project:
1. MASTER_METHODOLOGY_BRIEF.md
2. METAGPT_BUILDER_USER_GUIDE.md
3. MAINTENANCE_SOP.md
4. METAGPT_FILE_MAP.md
5. CHANGELOG.md
6. TEST_SUITE.md (optional)

### Conversation Starters

```
- "How do you work?"
- "I want to build a GPT that..."
- "Help me design a multi-project system"
- "Walk me through building my first project"
```

### Capabilities

- ✅ Web Browsing: Optional (for researching platforms)
- ❌ DALL-E: Not needed
- ❌ Code Interpreter: Not needed

---

## FOLDER STRUCTURE

### Local Storage (Your Computer)

```
METAGPT_BUILDER/
│
├── Active/
│   ├── MASTER_METHODOLOGY_BRIEF.md
│   ├── BASE_SYSTEM_PROMPT.md
│   ├── PROJECT_PROMPT_METAGPT_BUILDER.md
│   ├── METAGPT_BUILDER_USER_GUIDE.md
│   ├── MAINTENANCE_SOP.md
│   ├── METAGPT_FILE_MAP.md
│   ├── TEST_SUITE.md
│   └── CHANGELOG.md
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
| Active/ | Current working files | Source of truth, upload from here |
| Reference/ | Blueprint, planning docs | Your reference, not uploaded |
| Archives/ | Dated backups | Safety net, not uploaded |

---

## DOCUMENT RELATIONSHIPS

### Retrieval Flow

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

### Cross-Reference Map

| Document | References | Referenced By |
|----------|------------|---------------|
| MASTER_METHODOLOGY_BRIEF | — | BASE_SYSTEM_PROMPT, PROJECT_PROMPT |
| BASE_SYSTEM_PROMPT | MASTER_METHODOLOGY_BRIEF, MAINTENANCE_SOP | PROJECT_PROMPT |
| PROJECT_PROMPT | MASTER_METHODOLOGY_BRIEF, USER_GUIDE, Appendix A | — |
| USER_GUIDE | — | PROJECT_PROMPT |
| MAINTENANCE_SOP | MASTER_METHODOLOGY_BRIEF | BASE_SYSTEM_PROMPT |
| CHANGELOG | All documents | — |

---

## VERSION TRACKING

### Current Versions

| Document | Version | Last Updated |
|----------|---------|--------------|
| MASTER_METHODOLOGY_BRIEF.md | 1.0 | 2025-01-20 |
| BASE_SYSTEM_PROMPT.md | 1.0 | 2025-01-20 |
| PROJECT_PROMPT_METAGPT_BUILDER.md | 1.0 | 2025-01-20 |
| METAGPT_BUILDER_USER_GUIDE.md | 1.0 | 2025-01-20 |
| MAINTENANCE_SOP.md | 1.0 | 2025-01-20 |
| METAGPT_FILE_MAP.md | 1.0 | 2025-01-20 |
| TEST_SUITE.md | 1.0 | 2025-01-20 |
| CHANGELOG.md | — | 2025-01-20 |

### Version Sync Rule

When MASTER_METHODOLOGY_BRIEF updates:
- Re-upload to Claude Project Knowledge
- Re-upload to Custom GPT Knowledge
- Update CHANGELOG.md
- Update this file's version table

When prompts update:
- Re-paste into Instructions fields
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

### Never Retrieved (Unless Triggered)
- MAINTENANCE_SOP.md (only in maintenance mode)

### Retrieval Priorities by Query Type

| Query About | Priority Sections |
|-------------|-------------------|
| How to use the Builder | USER_GUIDE |
| Getting started | MMB Section 1, 2 |
| Agent types | MMB Section 3 |
| System prompts | MMB Section 4, Appendix A |
| Knowledge base design | MMB Section 5, 6, 7 |
| Multi-project systems | MMB Section 8, 11 |
| Maintenance | MMB Section 9, then MAINTENANCE_SOP |
| Testing | MMB Section 10 |
| Implementation | MMB Section 12, Appendix D |
| Templates | MMB Appendix A |
| Examples | MMB Appendix B |

---

## QUICK SETUP CHECKLIST

### Claude Project

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

### Custom GPT

- [ ] Create new GPT
- [ ] Set name and description
- [ ] Paste combined prompts into Instructions
- [ ] Upload all KB files to Knowledge
- [ ] Add conversation starters
- [ ] Configure capabilities (web browsing optional, others off)
- [ ] Test with: "I want to build a GPT that helps with customer support"
- [ ] Verify discovery flow initiates properly

---

**END OF FILE MAP**
