# MetaGPT Builder — GPT Setup Guide
## Step-by-Step OpenAI Custom GPT Configuration

---

# Overview

This guide walks you through setting up the MetaGPT Builder as a Custom GPT on OpenAI's platform.

**Time required:** 15-20 minutes
**Result:** A shareable GPT link anyone can use

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
Build effective Custom GPTs and Claude Projects using knowledge architecture — not just prompts and hope. Guides you through discovery, creates properly structured knowledge bases, and generates complete deployment-ready systems with maintenance procedures and test suites.
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

**Important:** The MetaGPT Builder uses **two separate prompt files** that both get pasted into the single Instructions field:

**Method 1: Use Pre-Combined File (Easiest)**
Copy the **entire contents** of `GPT_SYSTEM_PROMPT.md` into the Instructions field.

**Method 2: Manual Combination (Understanding the Architecture)**
1. Copy the **entire contents** of `BASE_SYSTEM_PROMPT.md` and paste it first
2. Add a separator line: `---`
3. Copy the **entire contents** of `PROJECT_PROMPT_METAGPT_BUILDER.md` and paste it after

**Why Two Separate Files?**
- **BASE_SYSTEM_PROMPT.md:** Universal behaviors used across all projects in multi-project systems
- **PROJECT_PROMPT_METAGPT_BUILDER.md:** Specific to the MetaGPT Builder project
- **Maintenance:** Easier to update shared base behaviors vs. project-specific instructions
- **Multi-Project Architecture:** The base prompt gets reused with different project prompts

Character count: ~36KB total (within Custom GPT limits)

**Critical:** Base behaviors must come before project-specific instructions.

---

# Step 4: Conversation Starters

Add these four starter prompts:

```
I want to build a GPT
```

```
How do you work?
```

```
Help me structure my knowledge base
```

```
What deliverables will I get?
```

These cover the main entry points: building, learning, specific help, and understanding outputs.

---

# Step 5: Knowledge Files

Upload these files to the Knowledge section:

## Required Files

| File | Size | Purpose |
|------|------|---------|
| MASTER_METHODOLOGY_BRIEF.md | ~100KB | Core methodology, templates, frameworks |
| METAGPT_BUILDER_USER_GUIDE.md | ~19KB | Onboarding, self-help, FAQs |
| MAINTENANCE_SOP.md | ~12KB | Update procedures |
| METAGPT_FILE_MAP.md | ~10KB | Architecture reference |

## Upload Order
1. MASTER_METHODOLOGY_BRIEF.md (largest, most important)
2. METAGPT_BUILDER_USER_GUIDE.md
3. MAINTENANCE_SOP.md
4. METAGPT_FILE_MAP.md

## Files NOT to Upload
- TEST_SUITE.md — Keep locally for your own validation
- CHANGELOG.md — Optional, low priority
- METAGPT_BUILDER_BLUEPRINT.md — Reference only

---

# Step 6: Capabilities

Configure these settings:

| Capability | Setting | Reason |
|------------|---------|--------|
| **Web Browsing** | ❌ OFF | All info should come from Knowledge |
| **DALL·E Image Generation** | ❌ OFF | Not needed |
| **Code Interpreter & Data Analysis** | ✅ **ON** | Required to process user uploads and generate downloadable files |

**Why Code Interpreter ON:**
- Reads user-uploaded documents (PDFs, docs, text)
- Processes content for chunking and structuring
- Generates downloadable .md files as deliverables

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
**Expected:** Offers three choices (explain, walk through, jump in)
**Pass:** ☐

## Test 2: Discovery Flow Start
**Input:** "I want to build a GPT"
**Expected:** Asks about single vs. multi-project FIRST
**Pass:** ☐

## Test 3: Methodology Retrieval
**Input:** "How should I chunk my content?"
**Expected:** References 600-1000 tokens, self-contained chunks, metadata
**Pass:** ☐

## Test 4: User Content Signal (No Maintenance)
**Input:** "Help me revise this document"
**Expected:** Offers to help with user's document, does NOT enter maintenance mode
**Pass:** ☐

## Test 5: Clear Maintenance Trigger
**Input:** "Update the methodology"
**Expected:** Enters maintenance mode, asks what to update
**Pass:** ☐

## Test 6: File Upload Processing
**Input:** Upload a text file and say "Please structure this for a knowledge base"
**Expected:** Reads file, chunks content, applies metadata, offers structured output
**Pass:** ☐

## Test 7: Deliverable Generation
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

- Verify all 4 files uploaded successfully
- Check file sizes match expected (no truncation)
- Try asking directly: "What does your knowledge base say about chunking?"

## "Discovery flow skips steps"

- Check Instructions copied completely
- Verify "Always follow this sequence" section is present
- Test with explicit: "I want to build a GPT — guide me through discovery"

## "Maintenance mode triggers incorrectly"

- Check all 3 layers are in Instructions
- Verify "User Content Signals → NEVER trigger" section present
- Test both trigger and non-trigger phrases

## "Can't read uploaded files"

- Verify Code Interpreter is ON
- Test with simple .txt file first
- Check file isn't corrupted or password-protected

## "Not generating downloadable files"

- Verify Code Interpreter is ON
- Explicitly request: "Generate these as downloadable .md files"
- Check Instructions include "FILE OUTPUTS" section

---

# Quick Reference: Final Configuration

| Setting | Value |
|---------|-------|
| Name | MetaGPT Builder |
| Instructions | Contents of GPT_SYSTEM_PROMPT.md (~6,500 chars) |
| Knowledge | 4 files (~141KB total) |
| Web Browsing | OFF |
| DALL·E | OFF |
| Code Interpreter | ON |
| Conversation Starters | 4 prompts |
| Visibility | Anyone with a link (for sharing) |

---

# Maintenance

## When to Update the GPT

- Methodology improvements → Update MASTER_METHODOLOGY_BRIEF.md, re-upload
- Behavioral changes → Update Instructions
- New features → May require both

## Update Process

1. Make changes to source files locally
2. Go to **My GPTs → MetaGPT Builder → Edit**
3. Re-upload changed Knowledge files (delete old, upload new)
4. Update Instructions if needed
5. Save
6. Run regression tests (Tests 1, 2, 3, 5 minimum)

---

**Setup complete!** Your MetaGPT Builder GPT is ready to share.

---

**END OF SETUP GUIDE**
