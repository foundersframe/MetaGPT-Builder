# MetaGPT Builder — Claude Project Setup Guide
## Step-by-Step Setup Using Pre-Built Files

---

# Overview

This guide walks you through setting up the MetaGPT Builder as a Claude Project using the complete file package we've already built.

**Time required:** 10-15 minutes
**Platform:** Claude.ai (Anthropic)
**Result:** Your own MetaGPT Builder Claude Project that you own and can customize

**What you get:** A fully functional system that helps you build effective Custom GPTs and Claude Projects using the complete MetaGPT Builder Framework methodology.

**Important Note:** This creates a **single MetaGPT Builder project**. The "multi-project architecture" you'll read about in the methodology refers to building **systems of multiple AI projects that share knowledge** — not multiple versions of the MetaGPT Builder itself. The Builder helps you design both single projects and multi-project systems.

---

# What's Included

You'll be setting up these files:

| File | Purpose | Size |
|------|---------|------|
| BASE_SYSTEM_PROMPT.md | Core AI behaviors and protocols | 13KB |
| PROJECT_PROMPT_METAGPT_BUILDER.md | MetaGPT Builder-specific instructions | 23KB |
| MASTER_METHODOLOGY_BRIEF.md | Complete framework methodology | 109KB |
| METAGPT_BUILDER_USER_GUIDE.md | How to use the MetaGPT Builder | 26KB |
| METAGPT_FILE_MAP.md | Documentation architecture map | 9KB |
| MAINTENANCE_SOP.md | Update procedures | 12KB |
| CHANGELOG.md | Version history | 3KB |
| TEST_SUITE.md | Validation tests | 22KB |

**Total:** ~217KB of structured knowledge

---

# Prerequisites

- Claude Pro subscription (required for Projects)
- All MetaGPT Builder files downloaded
- 10-15 minutes of setup time

---

# Step 1: Create New Claude Project

1. Go to **claude.ai**
2. Click **Projects** in the left sidebar
3. Click **Create Project** (or the "+" button)
4. Enter project details:
   
   **Name:**
   ```
   MetaGPT Builder
   ```
   
   **Description:**
   ```
   Build effective Custom GPTs and Claude Projects using knowledge architecture. Guides through discovery, creates structured knowledge bases, and generates deployment-ready systems with maintenance procedures.
   ```

5. Click **Create Project**

---

# Step 2: Configure Instructions

Click **Set custom instructions** (or the Instructions section).

**Important:** The MetaGPT Builder uses **two separate prompt files** that both get pasted into Claude's single Instructions field:

**Method 1: Use Pre-Combined File (Easiest)**
Copy the **entire contents** of `METAGPT_BUILDER_COMBINED_PROMPT.md` and paste into the Instructions field.

**Method 2: Manual Combination (Understanding the Architecture)**
1. Copy the **entire contents** of `BASE_SYSTEM_PROMPT.md` and paste it first
2. Copy the **entire contents** of `PROJECT_PROMPT_METAGPT_BUILDER.md` and paste it **directly after**

**Why Two Separate Files?**
- **BASE_SYSTEM_PROMPT.md:** Universal behaviors used across all projects in multi-project systems
- **PROJECT_PROMPT_METAGPT_BUILDER.md:** Specific to the MetaGPT Builder project
- **Maintenance:** Easier to update shared base behaviors vs. project-specific instructions
- **Multi-Project Architecture:** The base prompt gets reused with different project prompts

**Critical:** Base behaviors must come before project-specific instructions. Claude reads them as one continuous instruction set.

---

# Step 3: Upload Knowledge Base Files

Click **Add content** and upload these files **in any order:**

1. **MASTER_METHODOLOGY_BRIEF.md** — The complete framework
2. **METAGPT_BUILDER_USER_GUIDE.md** — How to use the builder
3. **METAGPT_FILE_MAP.md** — Architecture documentation
4. **MAINTENANCE_SOP.md** — Update procedures
5. **CHANGELOG.md** — Version history
6. **TEST_SUITE.md** — Validation tests (optional — for your reference)

**File format:** All files should be .md (Markdown) format

**Upload method:** You can drag and drop multiple files at once or use the file browser.

---

# Step 4: Initial Testing

Before sharing or using extensively, run these quick tests to verify everything is working:

## Test 1: Basic Functionality
**Ask:** "I want to build a customer support GPT for my business. Can you help me start with discovery?"

**Expected:** Should begin the discovery process, asking about single vs. multi-project first.

## Test 2: Knowledge Retrieval
**Ask:** "What's the optimal chunk size for knowledge base documents?"

**Expected:** Should respond with "600-1000 tokens" and explain why.

## Test 3: Template Generation
**Ask:** "Can you create a system prompt for an educational tutoring GPT?"

**Expected:** Should offer to use a template and walk through customization.

## Test 4: Maintenance Mode
**Ask:** "Maintenance mode - I need to update some information"

**Expected:** Should acknowledge maintenance mode and ask about the update type.

---

# Step 5: Project Settings (Optional)

## Project Icon

Add a custom icon if desired:
- Click on the project avatar/icon area
- Upload an image or emoji

---

# Verification Checklist

Before considering setup complete:

- [ ] Project created successfully
- [ ] Both prompts pasted in correct order (Base first, Project second)
- [ ] All 6-8 knowledge files uploaded successfully
- [ ] Test 1 passed: Discovery process starts correctly
- [ ] Test 2 passed: Retrieves framework information
- [ ] Test 3 passed: Can generate templates
- [ ] Test 4 passed: Maintenance mode works

---

# Using Your MetaGPT Builder

## Getting Started

Your first conversation should be:
```
"I want to build an AI project. Can you help me start with discovery?"
```

This initiates the full discovery process.

## Key Capabilities

Your MetaGPT Builder can:

1. **Run Discovery** — 8-step process to understand requirements
2. **Generate System Prompts** — Base and project prompts
3. **Create Knowledge Bases** — Structured, chunked, with metadata
4. **Build Lens Documents** — For multi-project systems
5. **Generate Test Suites** — Validation procedures
6. **Create Maintenance SOPs** — Update procedures
7. **Provide Templates** — All framework components

## Maintenance Mode

When you need to update the MetaGPT Builder itself:
```
"Maintenance mode - I need to update [describe what]"
```

## Advanced Usage

For complex projects, ask about:
- Multi-project architectures
- Lens documents
- Phased expansion strategies
- Gap identification and tracking

---

# Troubleshooting

## Project Won't Accept Instructions

**Issue:** Instructions field has character limit
**Solution:** The combined prompts are ~36KB. If you hit limits, ensure you have Claude Pro, or split into multiple messages during setup.

## File Upload Fails

**Issue:** Files won't upload
**Solution:** 
- Verify files are .md format
- Check file sizes (should all be under Claude's limits)
- Try uploading one at a time

## Responses Seem Generic

**Issue:** Not using the framework knowledge
**Solution:** 
- Verify all knowledge files uploaded successfully
- Check that both prompts were pasted correctly
- Run the test queries to verify retrieval

## Maintenance Mode Won't Trigger

**Issue:** "Maintenance mode" doesn't activate special behavior
**Solution:** 
- Ensure MAINTENANCE_SOP.md was uploaded
- Try exact phrase: "Maintenance mode"
- Verify Base System Prompt includes maintenance triggers

---

# Customization Options

## Modify for Your Domain

To adapt the MetaGPT Builder for a different domain:

1. **Edit the Project Prompt** — Change mission, scope, behavioral guidance
2. **Replace Master Brief** — Substitute your domain methodology
3. **Update User Guide** — Reflect your specific processes
4. **Modify Templates** — Adapt for your field's needs

## Add Your Content

You can add additional knowledge files:
- Industry-specific guidelines
- Your company's standards
- Custom templates
- Example projects

---

# What's Next

## Using Your Personal MetaGPT Builder

Once verified working, your MetaGPT Builder is ready for your personal use. **Note:** Claude Projects are private to your account and cannot be shared with others like Custom GPTs can be.

**If others want their own MetaGPT Builder:**
- Share the file package and this setup guide with them
- They'll need their own Claude Pro subscription
- Each person creates their own private copy

## Keep It Updated

The MetaGPT Builder includes maintenance procedures for keeping itself current. Set a quarterly review schedule to update:
- Framework methodology
- Platform-specific instructions
- Example projects
- Templates

---

# Support

## Documentation

Reference these documents for deeper understanding:
- METAGPT_BUILDER_USER_GUIDE.md (uploaded to your project)
- MASTER_METHODOLOGY_BRIEF.md (uploaded to your project)
- The MetaGPT Builder Framework PDF Guide

## Community

For questions, improvements, or sharing examples:
- **Website:** foundersframe.com
- **Framework Updates:** Watch for new versions of the core files

---

# File Checklist

Verify you have all these files before starting setup:

- [ ] BASE_SYSTEM_PROMPT.md
- [ ] PROJECT_PROMPT_METAGPT_BUILDER.md
- [ ] MASTER_METHODOLOGY_BRIEF.md
- [ ] METAGPT_BUILDER_USER_GUIDE.md
- [ ] METAGPT_FILE_MAP.md
- [ ] MAINTENANCE_SOP.md
- [ ] CHANGELOG.md
- [ ] TEST_SUITE.md

**Total files:** 8
**Missing any?** Download the complete MetaGPT Builder package.

---

**Setup complete!** You now have your own MetaGPT Builder that can help you create sophisticated AI projects using the complete framework methodology.

---

*© 2026 Founders Frame. This setup guide may be shared freely with the MetaGPT Builder files.*
