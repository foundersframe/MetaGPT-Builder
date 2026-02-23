# MetaGPT Builder — GPT Setup Guide
## Step-by-Step OpenAI Custom GPT Configuration

---

# Overview

This guide walks you through setting up the MetaGPT Builder as a Custom GPT on OpenAI's platform using our platform-optimized hybrid architecture.

**Time required:** 15-20 minutes
**Result:** A shareable GPT link with full sophisticated functionality
**Architecture:** Hybrid (Core prompt + Knowledge Base documents)

---

> ✅ **Platform Optimized**: Uses hybrid architecture to maintain full functionality within Custom GPT's 8K character limit

---

# Step 1: Access GPT Builder

1. Go to **chat.openai.com**
2. Click **Explore GPTs** (left sidebar)
3. Click **Create** (top right) or go to **My GPTs → Create a GPT**
4. Select the **Configure** tab (not Create — you want manual setup)

---

# Step 2: Basic Information

## Name
```
MetaGPT Builder
```

## Description
```
Build effective Custom GPTs and Claude Projects using knowledge architecture — not just prompts and hope. Platform-optimized hybrid architecture maintains full functionality within Custom GPT constraints. Guides you through discovery, creates properly structured knowledge bases, and generates complete deployment-ready systems with maintenance procedures and test suites.
```

## Profile Picture
Upload an icon or let DALL-E generate one. Suggested prompt if generating:
```
A minimalist logo representing AI system architecture: interconnected 
nodes forming a brain-like structure, clean lines, professional blue 
and white color scheme, suitable for a productivity tool icon
```

---

# Step 3: Instructions

**Important:** The MetaGPT Builder uses a **hybrid architecture** to work within Custom GPT's 8,000 character limit while maintaining full sophistication.

## Core Prompt Setup
Copy the **entire contents** of `GPT_CORE_SYSTEM_PROMPT.md` into the Instructions field.

**Character count:** ~7,500 characters (safely under 8K limit)

## What's in the Core Prompt?
- **Essential Identity:** What the AI is and does
- **Discovery Flow:** Cannot be retrieved mid-conversation, must be in Instructions
- **KB Retrieval Protocols:** How to access extended behaviors from Knowledge Base
- **Basic Behavioral Standards:** Core always/never rules

## What's NOT in Instructions (Retrieved from Knowledge Base)
- **Advanced behavioral protocols** → BEHAVIORAL_PROTOCOLS.md
- **Content processing workflows** → GENERATION_PROCEDURES.md  
- **Templates and examples** → TEMPLATE_LIBRARY.md
- **Implementation guidance** → PLATFORM_GUIDES.md

## How Hybrid Architecture Works
The core prompt includes retrieval instructions like:
- "For maintenance mode → retrieve BEHAVIORAL_PROTOCOLS.md Section 3"
- "For template generation → retrieve TEMPLATE_LIBRARY.md"

This allows full sophisticated functionality while staying under the 8K character limit.

**Critical:** Use only GPT_CORE_SYSTEM_PROMPT.md — do NOT use the combined BASE + PROJECT prompts (those exceed 8K characters).

---

# Step 4: Conversation Starters

Add these four starter prompts that showcase the hybrid architecture:

```
I want to build a sophisticated AI project
```

```
How does your hybrid architecture work?
```

```
Give me a complete system template
```

```
Help me with platform optimization
```

These cover the main entry points: sophisticated building (showcases full capabilities), hybrid architecture education, template generation (via KB retrieval), and platform expertise.

---

# Step 5: Knowledge Files

Upload these files to the Knowledge section in the recommended order:

## Required Files (Hybrid Architecture)

| File | Size | Purpose | Priority |
|------|------|---------|----------|
| **Hybrid Architecture Files** ||||
| BEHAVIORAL_PROTOCOLS.md | ~15KB | Advanced behaviors, maintenance mode, error handling | HIGH |
| GENERATION_PROCEDURES.md | ~18KB | Content workflows, architecture design, generation standards | HIGH |
| TEMPLATE_LIBRARY.md | ~22KB | Complete templates, metadata schemas, examples | HIGH |
| PLATFORM_GUIDES.md | ~16KB | Build guidance, platform optimization, implementation | HIGH |
| **Core Methodology Files** ||||
| MASTER_METHODOLOGY_BRIEF.md | ~100KB | Core methodology, frameworks, comprehensive reference | ESSENTIAL |
| METAGPT_BUILDER_USER_GUIDE.md | ~19KB | User onboarding, self-help, FAQs | ESSENTIAL |
| MAINTENANCE_SOP.md | ~12KB | Update procedures, version control | IMPORTANT |
| METAGPT_FILE_MAP.md | ~15KB | Architecture reference, file relationships | IMPORTANT |
| CHANGELOG.md | ~5KB | Version history | OPTIONAL |

## Upload Order (Critical for Hybrid Architecture)

1. **BEHAVIORAL_PROTOCOLS.md** (advanced behaviors)
2. **GENERATION_PROCEDURES.md** (content workflows)  
3. **TEMPLATE_LIBRARY.md** (templates & examples)
4. **PLATFORM_GUIDES.md** (implementation guidance)
5. **MASTER_METHODOLOGY_BRIEF.md** (core methodology)
6. **METAGPT_BUILDER_USER_GUIDE.md** (user guidance)
7. **MAINTENANCE_SOP.md** (update procedures)
8. **METAGPT_FILE_MAP.md** (architecture reference)
9. **CHANGELOG.md** (version history)

## Why Upload Order Matters

The core prompt includes specific retrieval instructions that reference these documents by name. Uploading in this order ensures:
- Highest priority behavioral systems are processed first
- Core retrieval paths work reliably
- Complex procedures are accessible when needed

## Files NOT to Upload
- TEST_SUITE.md — Keep locally for your own validation
- GPT_CORE_SYSTEM_PROMPT.md — This goes in Instructions, not Knowledge
- BASE_SYSTEM_PROMPT.md — Claude Projects only
- PROJECT_PROMPT_METAGPT_BUILDER.md — Claude Projects only

---

# Step 6: Capabilities

Configure these settings:

| Capability | Setting | Reason |
|------------|---------|--------|
| **Web Browsing** | ❌ OFF | All info comes from Knowledge Base (hybrid architecture) |
| **DALL·E Image Generation** | ❌ OFF | Not needed |
| **Code Interpreter & Data Analysis** | ✅ **ON** | Required to process uploads and generate files; supports hybrid architecture |

**Why Code Interpreter ON:**
- Reads user-uploaded documents (PDFs, docs, text)
- Processes content for chunking and structuring
- Generates downloadable .md files as deliverables
- Supports hybrid architecture file processing workflows

---

# Step 7: Additional Settings (Optional)

## Actions
None needed — the Builder doesn't require external API calls.

## Additional Instructions
Leave blank — everything is in the main Instructions field.

---

# Step 8: Save and Test

1. Click **Save** (top right)
2. Choose visibility:
   - **Only me** — For testing
   - **Anyone with a link** — For sharing (recommended after testing)
   - **Public** — For GPT Store listing
3. Click **Confirm**

---

# Step 9: Run Validation Tests

Before sharing, run these tests in the GPT:

## Test 1: Self-Help Recognition
**Input:** "How do you work?"
**Expected:** Explains hybrid architecture approach and capabilities
**Pass:** ☐

## Test 2: Discovery Flow Start
**Input:** "I want to build a sophisticated AI project"
**Expected:** Asks about single vs. multi-project FIRST
**Pass:** ☐

## Test 3: Methodology Retrieval
**Input:** "How should I chunk my content?"
**Expected:** References 600-1000 tokens, self-contained chunks, metadata
**Pass:** ☐

## Test 4: Hybrid Architecture - KB Retrieval
**Input:** "Help me with maintenance mode"
**Expected:** Retrieves from BEHAVIORAL_PROTOCOLS.md, provides maintenance procedures
**Pass:** ☐

## Test 5: Hybrid Architecture - Template Generation
**Input:** "Give me a system prompt template"
**Expected:** Retrieves from TEMPLATE_LIBRARY.md, provides complete template
**Pass:** ☐

## Test 6: User Content Signal (No Maintenance)
**Input:** "Help me revise this document"
**Expected:** Offers to help with user's document, does NOT enter maintenance mode
**Pass:** ☐

## Test 7: Clear Maintenance Trigger
**Input:** "Update the methodology"
**Expected:** Enters maintenance mode, asks what to update
**Pass:** ☐

## Test 8: Platform Optimization Knowledge
**Input:** "What's the difference between Claude Projects and Custom GPTs?"
**Expected:** Explains hybrid architecture solution for Custom GPTs
**Pass:** ☐

## Test 9: File Upload Processing
**Input:** Upload a text file and say "Please structure this for a knowledge base"
**Expected:** Reads file, chunks content, applies metadata, offers structured output
**Pass:** ☐

## Test 10: Deliverable Generation
**Input:** Complete a simple discovery flow and say "Generate the deliverables"
**Expected:** Creates downloadable .md files for each deliverable
**Pass:** ☐

**All tests pass?** → Ready to share!
**Any failures?** → Check Instructions and Knowledge uploads, then re-test.

---

# Step 10: Get Your Shareable Link

1. Open your GPT
2. Click the GPT name (top of chat)
3. Click **Copy link**

Your link format: `https://chat.openai.com/g/g-[unique-id]-metagpt-builder`

This link works for anyone with ChatGPT Plus or Team.

---

# Troubleshooting

## "GPT isn't finding information from Knowledge files"

- Verify all 9 required files uploaded successfully (including hybrid architecture files)
- Check file sizes match expected (no truncation)
- Try asking directly: "What does BEHAVIORAL_PROTOCOLS.md say about maintenance mode?"

## "Hybrid architecture retrieval not working"

- Verify KB files uploaded in correct order (BEHAVIORAL_PROTOCOLS.md first)
- Test specific retrieval: "Give me a template from TEMPLATE_LIBRARY.md"
- Check that GPT_CORE_SYSTEM_PROMPT.md is in Instructions (not Knowledge)

## "Discovery flow skips steps"

- Check Instructions use GPT_CORE_SYSTEM_PROMPT.md (not combined BASE + PROJECT)
- Verify character count is under 8,000 characters
- Test with explicit: "I want to build a sophisticated project — guide me through discovery"

## "Maintenance mode triggers incorrectly"

- Check BEHAVIORAL_PROTOCOLS.md uploaded successfully
- Verify all 3 trigger layers are accessible via KB retrieval
- Test both trigger and non-trigger phrases

## "Can't access advanced features"

- Verify BEHAVIORAL_PROTOCOLS.md, GENERATION_PROCEDURES.md uploaded
- Test complex behavior: "Help me with a multi-project system"
- Check that hybrid architecture files are accessible

## "Not generating templates"

- Verify TEMPLATE_LIBRARY.md uploaded successfully
- Test directly: "Give me a system prompt template"
- Check retrieval instructions in core prompt

## "Can't read uploaded files"

- Verify Code Interpreter is ON
- Test with simple .txt file first
- Check file isn't corrupted or password-protected

## "Not generating downloadable files"

- Verify Code Interpreter is ON
- Explicitly request: "Generate these as downloadable .md files"
- Check Instructions include file generation protocols

---

# Quick Reference: Final Configuration

| Setting | Value |
|---------|-------|
| Name | MetaGPT Builder |
| Instructions | Contents of GPT_CORE_SYSTEM_PROMPT.md (~7,500 chars) |
| Knowledge | 9 files (~200KB total) - hybrid architecture |
| Web Browsing | OFF |
| DALL·E | OFF |
| Code Interpreter | ON |
| Conversation Starters | 4 prompts (hybrid architecture focused) |
| Visibility | Anyone with a link (for sharing) |
| Architecture | Hybrid (Instructions + Knowledge Base retrieval) |

---

# Maintenance

## When to Update the GPT

- **Methodology improvements** → Update MASTER_METHODOLOGY_BRIEF.md, re-upload
- **Behavioral changes** → Update BEHAVIORAL_PROTOCOLS.md or GPT_CORE_SYSTEM_PROMPT.md
- **Template updates** → Update TEMPLATE_LIBRARY.md, re-upload
- **Platform guidance changes** → Update PLATFORM_GUIDES.md, re-upload
- **Core prompt changes** → Update GPT_CORE_SYSTEM_PROMPT.md in Instructions

## Update Process

1. **Make changes to source files locally**
2. **Go to My GPTs → MetaGPT Builder → Edit**
3. **For Knowledge Base updates:**
   - Delete old file from Knowledge section
   - Upload updated file in same order position
4. **For Instructions updates:**
   - Replace with updated GPT_CORE_SYSTEM_PROMPT.md content
   - Verify character count under 8,000
5. **Save**
6. **Run regression tests** (Tests 1, 2, 4, 5, 8 minimum for hybrid architecture)

## Hybrid Architecture Maintenance

**Character Limit Monitoring:**
- Always verify Instructions under 8,000 characters after updates
- If core prompt grows too large, move content to appropriate KB document

**KB Document Dependencies:**
- Maintain upload order for optimal retrieval
- Test retrieval paths after any KB document updates
- Ensure core prompt retrieval instructions match actual KB document names

**Version Sync:**
- Keep local files in sync with uploaded versions
- Update CHANGELOG.md for all changes
- Test hybrid functionality after any updates

---

**Setup complete!** Your MetaGPT Builder GPT is ready to share.

---

**END OF SETUP GUIDE**
