# PLATFORM GUIDES
## MetaGPT Builder - Platform-Specific Build Guidance

**Document Type:** Knowledge Base (GPT-Optimized)
**Version:** 2.0 (GPT Hybrid Architecture)
**Last Updated:** 2025-02-09
**Purpose:** Guidance for building AI systems optimized for different platforms

**Usage:** Referenced by GPT_CORE_SYSTEM_PROMPT.md when determining architecture approach

---

## TABLE OF CONTENTS

1. [Platform Architecture Selection](#section-1-platform-architecture-selection)
2. [Claude Project Build Strategy](#section-2-claude-project-build-strategy)
3. [Custom GPT Build Strategy](#section-3-custom-gpt-build-strategy)
4. [Hybrid Architecture Generation](#section-4-hybrid-architecture-generation)
5. [Platform-Specific Deliverables](#section-5-platform-specific-deliverables)
6. [Implementation Guidance Generation](#section-6-implementation-guidance-generation)

---

# SECTION 1: PLATFORM COMPARISON

# SECTION 1: PLATFORM ARCHITECTURE SELECTION

## Decision Framework for Build Generation

When user specifies platform during discovery, select architecture approach based on these criteria:

### Claude Project Selection
**When user chooses Claude Projects:**
- **Always use:** Full sophisticated architecture (original framework)
- **Generate:** Complete 50,000+ character combined prompt
- **Include:** All behavioral protocols in system prompt
- **Architecture:** Single comprehensive prompt with full KB integration
- **Advantage:** No character limits, maximum sophistication

### Custom GPT Selection
**When user chooses Custom GPT:**
- **Always use:** Hybrid architecture (core + KB documents)
- **Generate:** GPT_CORE_SYSTEM_PROMPT.md (~7.5K chars) + 4 KB documents
- **Architecture:** Instructions + Knowledge Base retrieval
- **Advantage:** Full sophistication within platform constraints

## Simplified Platform Logic

| Platform | Architecture | Approach |
|----------|-------------|----------|
| **Claude Projects** | Full sophisticated | Original framework (50K+ chars in Instructions) |
| **Custom GPTs** | Hybrid optimized | Core prompt (~7.5K) + KB documents |

**No complexity assessment needed - each platform gets its optimized approach.**

## Platform Capability Mapping

| Requirement | Claude Projects | Custom GPTs (Hybrid) |
|-------------|----------------|--------------------|
| Character limit | No limit | 8,000 chars (core) |
| Sophisticated protocols | ✅ Full in Instructions | ✅ Full via KB retrieval |
| Maintenance mode | ✅ Built-in | ✅ Via BEHAVIORAL_PROTOCOLS.md |
| Complex error handling | ✅ Built-in | ✅ Via BEHAVIORAL_PROTOCOLS.md |
| Template generation | ✅ Built-in | ✅ Via TEMPLATE_LIBRARY.md |
| Multi-project support | ✅ Native | ✅ Via architecture design |

## Recommendation Logic

**Always recommend Claude Projects when:**
- User wants maximum sophistication in Instructions
- Private use acceptable (no public sharing)
- Multi-project coordination needed
- User prefers Anthropic platform

**Always recommend Custom GPT when:**
- Public sharing needed
- User prefers OpenAI platform
- Additional capabilities needed (web browsing, DALL-E, etc.)

**Both approaches deliver full sophistication - just through different architectures.**

---

# SECTION 2: CLAUDE PROJECT IMPLEMENTATION

# SECTION 2: CLAUDE PROJECT BUILD STRATEGY

## Generation Approach for Claude Projects

When building for Claude Projects, use the **original MetaGPT Builder framework** with full sophistication.

### System Prompt Generation

**Architecture:** Combined Base + Project prompt approach
- **Generate:** Complete BASE_SYSTEM_PROMPT.md (all behavioral protocols)
- **Generate:** Complete PROJECT_PROMPT_[NAME].md (project-specific instructions)
- **Total size:** 50,000+ characters (no platform limitation)
- **Include:** All sophisticated behavioral protocols inline

### Key Components to Include

**Base System Prompt sections:**
- Complete Core Identity
- Full Retrieval Configuration (16 query types)
- Complete 3-Layer Maintenance Mode system
- Data Freshness Protocol with all flagging language
- Complete Confidence Weighting system
- Full Spec Confirmation Protocol
- Comprehensive Response Formatting guidelines
- Complete Error Handling procedures
- All Maintenance Mode Instructions (5-step process)
- Complete Quick Reference sections

**Project Prompt sections:**
- Complete Project Mission
- Full KB Integration table
- Complete Self-Help & Onboarding Recognition
- Complete 8-Step Discovery Flow with context assessment
- Full Architecture Design procedures
- Complete Generation Process with content processing
- All Common Scenarios

### Knowledge Base Strategy

**For Claude Projects:**
- **Upload:** Domain-specific knowledge files
- **Upload:** Maintenance SOP, Changelog, Test Suite
- **Architecture:** System can handle complex retrieval natively
- **Organization:** Use full metadata schema where helpful
- **No constraints** on knowledge base complexity or size

### Implementation Guidance Generation

**Always include for Claude Projects:**
```markdown
## IMPLEMENTATION: Claude Project

1. Create new project: [Name]
2. Set description: "[Description]"
3. In Instructions field, paste (in order):
   - BASE_SYSTEM_PROMPT.md content (first)
   - PROJECT_PROMPT.md content (second)
4. Upload to Knowledge:
   - [DOMAIN_KB].md
   - MAINTENANCE_SOP.md
   - CHANGELOG.md
5. Keep locally:
   - FILE_MAP.md
   - TEST_SUITE.md
6. Test with: [specific validation queries]
```

### Claude-Specific Optimizations

**Leverage platform strengths:**
- **No character limits:** Include all sophisticated protocols
- **Consistent retrieval:** Organize KB for optimal access
- **Project memory:** Design for conversation continuity
- **Advanced protocols:** Include full maintenance mode, error handling

---

# SECTION 3: CUSTOM GPT IMPLEMENTATION

# SECTION 3: CUSTOM GPT BUILD STRATEGY

## Generation Approach for Custom GPTs

When building for Custom GPTs, **always use hybrid architecture** to maintain full sophistication within platform constraints.

### Hybrid Architecture Generation (Standard for All Custom GPTs)

**Always generate:** Core system prompt (~7.5K chars) + KB documents

### Core System Prompt Generation (~7.5K chars)

**Generate:** GPT_CORE_SYSTEM_PROMPT.md format containing:
- **Essential Identity** - What the AI is and does
- **Discovery Flow** - Cannot be retrieved mid-conversation
- **KB Retrieval Protocols** - How to access extended behaviors
- **Basic Behavioral Standards** - Core always/never rules

**Critical retrieval instructions:**
```markdown
For complex procedures, retrieve from KB:
- Maintenance issues → BEHAVIORAL_PROTOCOLS.md Section 3
- Generation tasks → GENERATION_PROCEDURES.md Section 2  
- Templates → TEMPLATE_LIBRARY.md
- Implementation → PLATFORM_GUIDES.md
```

### Knowledge Base Document Generation

**Always generate these 4 additional KB documents:**

**1. BEHAVIORAL_PROTOCOLS.md**
- 3-Layer Maintenance Mode system
- Complete Error Handling procedures
- Self-Help Recognition protocols
- Advanced behavioral standards
- Common scenario responses

**2. GENERATION_PROCEDURES.md**
- Content processing workflows
- Architecture design procedures
- Generation order and standards
- Context assessment frameworks

**3. TEMPLATE_LIBRARY.md**
- All system prompt templates
- Knowledge base templates
- Metadata schema examples
- Implementation templates

**4. PLATFORM_GUIDES.md**
- This document for build guidance
- Platform comparison information
- Architecture selection logic

### Hybrid Architecture Benefits

**Maintains full sophistication:**
- All original behavioral protocols preserved
- Complete template library accessible
- Advanced error handling available
- Sophisticated maintenance procedures

**Demonstrates platform expertise:**
- Intelligent solution for platform limitations
- Advanced architecture understanding
- Professional optimization approach

### Implementation Guidance for All Custom GPTs

```markdown
## IMPLEMENTATION: Custom GPT

1. Create new GPT: [Name]
2. Set description: "[Description] (Platform-optimized hybrid architecture)"
3. In Instructions, paste: GPT_CORE_SYSTEM_PROMPT.md content
4. Upload to Knowledge (in order):
   - BEHAVIORAL_PROTOCOLS.md
   - GENERATION_PROCEDURES.md  
   - TEMPLATE_LIBRARY.md
   - PLATFORM_GUIDES.md
   - [DOMAIN]_KNOWLEDGE_BASE.md
5. Test hybrid retrieval: [Specific validation tests]
6. Verify character count: Core prompt under 8,000 chars
```

## User Communication

**When user chooses Custom GPT, explain the approach:**
"I'll create a platform-optimized Custom GPT using hybrid architecture - this maintains full sophistication while working within Custom GPT's 8,000 character limit by using a core prompt + knowledge base documents."

**Benefits to highlight:**
- Full functionality preserved
- Platform limitations solved intelligently
- Professional optimization approach
- All MetaGPT Builder features available

---

# SECTION 4: GPT-OPTIMIZED HYBRID SETUP

# SECTION 4: HYBRID ARCHITECTURE GENERATION

## When to Generate Hybrid Architecture

**Trigger conditions:**
- User chooses Custom GPT AND requirements exceed 8K characters
- User explicitly requests "platform-optimized" or "sophisticated" Custom GPT
- Original framework would generate 25,000+ character system prompt

### Hybrid Generation Workflow

**Step 1: Generate Core System Prompt**
Create condensed version targeting ~7,500 characters:

**Essential components to keep:**
- Core Identity (condensed but complete)
- Discovery Flow (cannot be retrieved mid-conversation)
- Basic Retrieval Protocols (how to access KB documents)
- Critical behavioral standards (essential always/never rules)

**Components to move to KB:**
- 3-Layer Maintenance Mode → BEHAVIORAL_PROTOCOLS.md Section 3
- Complex Error Handling → BEHAVIORAL_PROTOCOLS.md Section 4
- Self-Help Recognition → BEHAVIORAL_PROTOCOLS.md Section 1
- Content Processing Workflows → GENERATION_PROCEDURES.md Section 1
- Template Generation → TEMPLATE_LIBRARY.md

**Step 2: Generate KB Documents**
Create 4 specialized KB documents containing moved content:

1. **BEHAVIORAL_PROTOCOLS.md** (Advanced behaviors)
2. **GENERATION_PROCEDURES.md** (Content workflows)
3. **TEMPLATE_LIBRARY.md** (Templates & examples)
4. **PLATFORM_GUIDES.md** (Implementation guidance)

**Step 3: Validate Character Count**
- Core prompt must be under 8,000 characters
- If over limit, move additional content to KB
- Ensure retrieval instructions are clear and functional

## Retrieval Architecture Design

### Core Prompt Retrieval Instructions

**Include these retrieval protocols in core prompt:**
```markdown
For complex procedures, retrieve from KB:
- Maintenance mode → BEHAVIORAL_PROTOCOLS.md Section 3
- Advanced error handling → BEHAVIORAL_PROTOCOLS.md Section 4
- Template generation → TEMPLATE_LIBRARY.md
- Implementation guidance → PLATFORM_GUIDES.md
```

### KB Document Structure

**Each KB document must:**
- Have clear section markers for retrieval
- Include complete procedures (no placeholders)
- Cross-reference related documents
- Maintain original sophistication level

---

# SECTION 5: PLATFORM-SPECIFIC DELIVERABLES

## Claude Project Deliverable Package

**Always generate for Claude Projects:**
1. **BASE_SYSTEM_PROMPT.md** (complete behavioral protocols)
2. **PROJECT_PROMPT_[NAME].md** (project-specific instructions)
3. **[DOMAIN]_KNOWLEDGE_BASE.md** (domain expertise)
4. **MAINTENANCE_SOP.md** (update procedures)
5. **CHANGELOG.md** (version tracking)
6. **FILE_MAP.md** (architecture reference)
7. **TEST_SUITE.md** (validation protocols)

## Standard Custom GPT Deliverable Package

**Generate for all Custom GPT projects (hybrid architecture):**
1. **GPT_CORE_SYSTEM_PROMPT.md** (~7.5K characters)
2. **BEHAVIORAL_PROTOCOLS.md** (advanced behaviors)
3. **GENERATION_PROCEDURES.md** (content workflows)
4. **TEMPLATE_LIBRARY.md** (templates & examples)
5. **PLATFORM_GUIDES.md** (implementation guidance)
6. **[DOMAIN]_KNOWLEDGE_BASE.md** (domain expertise)
7. **MAINTENANCE_SOP.md** (update procedures)
8. **CHANGELOG.md** (version tracking)

---

# SECTION 6: IMPLEMENTATION GUIDANCE GENERATION

## Platform-Specific Implementation Instructions

### For Claude Project Builds

**Always include this implementation section:**
```markdown
## IMPLEMENTATION: Claude Project

1. Create new project: [Project Name]
2. Set description: "[Project Description]"
3. In Instructions field, paste (in order):
   - BASE_SYSTEM_PROMPT.md content (first)
   - PROJECT_PROMPT.md content (second)
4. Upload to Knowledge:
   - [DOMAIN_KB].md
   - MAINTENANCE_SOP.md
   - CHANGELOG.md
5. Keep locally (do NOT upload):
   - FILE_MAP.md (architecture reference)
   - TEST_SUITE.md (validation protocols)
6. Test with these queries:
   - "[Project-specific test 1]"
   - "[Project-specific test 2]"
```

### For Custom GPT Builds (Hybrid Architecture - Standard)

**Include this implementation section for all Custom GPT projects:**
```markdown
## IMPLEMENTATION: Custom GPT

1. Create new GPT: [Project Name]
2. Set description: "[Project Description] (Platform-optimized hybrid architecture)"
3. In Instructions, paste: GPT_CORE_SYSTEM_PROMPT.md content
4. Upload to Knowledge (in this order):
   - BEHAVIORAL_PROTOCOLS.md (advanced behaviors)
   - GENERATION_PROCEDURES.md (content workflows)
   - TEMPLATE_LIBRARY.md (templates & examples)
   - PLATFORM_GUIDES.md (implementation guidance)
   - [DOMAIN]_KNOWLEDGE_BASE.md (domain expertise)
5. Set Conversation Starters:
   - "[Starter showing main function]"
   - "[Starter demonstrating hybrid capabilities]"
   - "[Starter for complex procedures]"
   - "[Starter for getting help]"
6. Configure Capabilities: [Recommend appropriate settings]
7. Verify hybrid functionality:
   - Test core behavioral responses
   - Test KB document retrieval
   - Test complex procedure handling
8. Architecture Note: Explain hybrid approach maintains full sophistication

**Important:** Explain to user that this version uses Instructions + KB hybrid 
to maintain full sophistication within Custom GPT's 8K character limit.
```

## Testing Protocol Generation

**Always include appropriate test queries based on project type:**
- Basic functionality test
- Knowledge retrieval test  
- Discovery flow test
- Edge case handling test

**For hybrid architecture, add:**
- KB document retrieval test
- Complex procedure test
- Character limit compliance verification

---

**END OF PLATFORM GUIDES**

**Usage Note:** This document guides the MetaGPT Builder AI on how to generate appropriate architectures for different platforms, not how users set up the MetaGPT Builder itself.

**Related Documents:**
- GPT_CORE_SYSTEM_PROMPT.md (references this guide)
- BEHAVIORAL_PROTOCOLS.md (advanced behaviors)
- GENERATION_PROCEDURES.md (content workflows)  
- TEMPLATE_LIBRARY.md (templates and examples)
