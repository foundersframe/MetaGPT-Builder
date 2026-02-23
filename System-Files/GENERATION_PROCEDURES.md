# GENERATION PROCEDURES
## MetaGPT Builder - Content Processing & Generation Workflows

**Document Type:** Knowledge Base (GPT-Optimized)
**Version:** 2.0 (GPT Hybrid Architecture)
**Last Updated:** 2025-02-09
**Purpose:** Complete generation procedures for Custom GPT hybrid architecture

**Usage:** Referenced by GPT_CORE_SYSTEM_PROMPT.md for complex generation tasks

---

## TABLE OF CONTENTS

1. [Content Processing Workflows](#section-1-content-processing-workflows)
2. [Architecture Design Procedures](#section-2-architecture-design-procedures)
3. [Generation Order & Standards](#section-3-generation-order--standards)
4. [Context Assessment Framework](#section-4-context-assessment-framework)
5. [Knowledge Source Handling](#section-5-knowledge-source-handling)
6. [Output Quality Standards](#section-6-output-quality-standards)

---

# SECTION 1: CONTENT PROCESSING WORKFLOWS

## When User Provides Documents

Before generating the MIB (Master Information Brief), process user-provided content:

### Step 1: Analyze
- Identify logical sections, themes, and structure
- Map content to discovery requirements
- Note gaps or inconsistencies
- Assess content quality and completeness

### Step 2: Chunk
- Break into 600-1000 token segments at natural boundaries
- Respect conceptual transitions
- Maintain narrative flow where possible
- Avoid breaking mid-sentence or mid-concept

### Step 3: Tag (9-Field Metadata Schema)
Apply metadata to each chunk:

```
---
CHUNK_ID: [DOC]-[Section].[Subsection]-[Number]
TOPIC: [primary_category]
SUBTOPIC: [specific_focus]
INSIGHT_TYPE: [concept|framework|procedure|example|template|warning]
RELEVANCE: [single_project|multi_project|both]
APPLICATION: [discovery|architecture|generation|implementation|maintenance]
CONFIDENCE: [established|recommended|experimental]
DATA_FRESHNESS: [YYYY-MM|evergreen]
KEYWORDS: [comma, separated, terms]
---
```

### Step 4: Overlap
- Add boundary overlap at section transitions
- Repeat 1-2 transitional sentences between chunks
- Maintain context for retrieval system
- Ensure smooth information flow

### Step 5: Organize
- Arrange into logical section hierarchy
- Group related concepts together
- Create clear section headings
- Build table of contents

### Step 6: Consolidate
- Group related statistics in appendix for easy updates
- Separate evergreen content from time-sensitive data
- Create reference sections for frequently accessed info
- Optimize for maintenance and updates

## When User Lacks Documents

### Option 1: Deep Research Method
Provide customized research prompt for AI research tools:

**Base Research Prompt Template:**
```
Research [DOMAIN] comprehensively for someone building [PROJECT TYPE].

Focus on:
- Industry best practices and standards
- Common procedures and frameworks  
- Regulatory requirements and compliance
- Key terminology and concepts
- Common challenges and solutions

Format as structured sections with clear headings.
Target output: 3,000-5,000 words of comprehensive domain knowledge.
```

**Customization Process:**
1. Replace [DOMAIN] with user's specific field
2. Replace [PROJECT TYPE] with their specific use case
3. Add domain-specific research focuses
4. Provide research source recommendations

### Option 2: Self-Interview Method
Provide customized interview prompt for knowledge extraction:

**Base Self-Interview Prompt Template:**
```
You are an expert interviewer helping extract knowledge for [DOMAIN] [PROJECT TYPE].

Interview me systematically about:
- My processes and methodologies
- Decision-making frameworks I use
- Common situations I handle
- Lessons learned and best practices
- Tools, resources, and references

Ask probing follow-up questions. Session should run 60-90 minutes.
After each response, ask 1-2 clarifying questions before moving to next topic.
```

**Conversion Prompt:**
```
Convert this interview transcript into structured knowledge sections:

1. Core Methodologies
2. Process Frameworks  
3. Decision Trees
4. Best Practices
5. Common Scenarios
6. Tools and Resources
7. Lessons Learned

Format with clear headings and detailed content.
```

### Option 3: Hybrid Approach (Recommended)
1. **Research Phase** (1-2 hours): Use Deep Research for domain fundamentals
2. **Interview Phase** (1-2 hours): Extract personal expertise and methods
3. **Synthesis Phase** (30-60 minutes): Combine research + interview into comprehensive KB

## Template Generation (No Content Provided)

When user prefers template approach:

1. **Analyze Discovery Results** - Map requirements to content needs
2. **Generate Section Structure** - Create logical KB organization
3. **Add Content Guidance** - Explain what goes in each section
4. **Include Examples** - Show proper formatting and metadata
5. **Provide Population Instructions** - Clear steps for user to complete

---

# SECTION 2: ARCHITECTURE DESIGN PROCEDURES

## Single Project Architecture

### Discovery-to-Architecture Mapping
Based on discovery answers, determine architecture:

| Discovery Result | Architecture Decision |
|-----------------|---------------------|
| Solo + Expert + Production | Lean docs, sophisticated prompts OK |
| Team + Learning + Functional | Clear structure, growth room |
| Clients + Organizing + Production | Full polish, comprehensive docs |
| Multi-role scenarios | Calibrate to dominant needs |

### File Structure for Single Project
```
Files to create:
1. SYSTEM_PROMPT.md — Combined base + project instructions
2. [DOMAIN]_KNOWLEDGE_BASE.md — Main knowledge document
3. MAINTENANCE_SOP.md — Update procedures
4. CHANGELOG.md — Version tracking
5. FILE_MAP.md — Architecture reference
6. TEST_SUITE.md — Validation protocols
```

### Architecture Presentation Format
```
PROPOSED ARCHITECTURE: Single Project

Platform: [Claude Project / Custom GPT]
Agent Type: [Primary] + [Secondary]
Knowledge Sources: [List]
Key Outputs: [List]
Maintenance Plan: [Frequency and procedures]

Files to create: [List with purposes]

Shall I proceed with this structure?
```

## Multi-Project Architecture

### When to Recommend Multi-Project
- Multiple use cases sharing common knowledge
- Different audiences needing different views of same information
- Anticipated adding related tools later
- Organizational structure benefits from shared resources

### Universal/Shared/Project-Specific Model

**Universal Documents (all projects):**
- MASTER_[DOMAIN]_BRIEF.md — Shared knowledge base
- BASE_SYSTEM_PROMPT.md — Universal behaviors
- MAINTENANCE_SOP.md — Update procedures across system

**Shared Documents (some projects):**
- Determined based on project relationships
- Could be audience-specific, function-specific, or domain-specific

**Per-Project Documents:**
- LENS_[XX]_[Name].md — Project-specific knowledge view
- PROJECT_PROMPT_[XX].md — Project-specific instructions

### Multi-Project Architecture Presentation
```
PROPOSED ARCHITECTURE: Multi-Project System

Universal Documents (all projects):
- MASTER_[DOMAIN]_BRIEF.md — Shared knowledge
- BASE_SYSTEM_PROMPT.md — Universal behaviors
- MAINTENANCE_SOP.md — Update procedures

Projects identified:
1. [Project 1] — [Purpose] — [Audience]
2. [Project 2] — [Purpose] — [Audience]
[etc.]

Sync Strategy: [How updates propagate]
Maintenance Plan: [Coordination procedures]

Shall I proceed with this structure?
```

---

# SECTION 3: GENERATION ORDER & STANDARDS

## Generation Sequence

### For Single Project (Always in this order)
1. **System prompt** (combined base + project)
2. **Primary KB document** (MIB) — populated or template
3. **Maintenance SOP** — Update procedures
4. **File Map** — Architecture documentation
5. **Changelog** — Initial version entry
6. **Test Suite** — Validation protocols
7. **Implementation guide** — Platform-specific setup

### For Multi-Project (Always in this order)
1. **Architecture overview document**
2. **Master knowledge document** (MIB)
3. **Base system prompt** — Universal behaviors
4. **Shared documents** — If any identified
5. **Lens documents** — One per project
6. **Project prompts** — One per project  
7. **Maintenance SOP** — Multi-project procedures
8. **File Map** — Complete architecture
9. **Changelog** — Initial version entry
10. **Test Suite** — System-wide validation
11. **Implementation guide** — All projects

## Document Generation Standards

### Every Document Must Be
- **Complete** — No placeholders, no "[add content here]"
- **Copy-paste ready** — User can use immediately without editing
- **Properly formatted** — Clear markdown structure, consistent headings
- **Platform-appropriate** — Adapted for target platform requirements

### System Prompts Must Include
- All sections from methodology templates
- Specific, actionable instructions (no vague guidance like "be helpful")
- Platform-specific behavioral adjustments
- Error handling and edge case protocols
- Clear retrieval and processing instructions

### KB Documents Must Include
- Proper chunking (600-1000 tokens per section)
- Complete 9-field metadata headers where appropriate
- Boundary overlap at conceptual transitions
- Clear section structure with table of contents
- Change tracking and version information

### Lens Documents Must Include
- All sections from lens template (Appendix A)
- Specific retrieval weights and priorities
- Chunk ID references where possible
- Gap assessment and expansion planning
- Cross-project coordination notes

## Quality Assurance Checklist

Before finalizing any deliverable:
- [ ] Follows methodology principles and framework
- [ ] Includes proper metadata where applicable
- [ ] Provides clear implementation steps
- [ ] References relevant methodology sections appropriately
- [ ] Includes maintenance considerations and update procedures
- [ ] Formatted consistently with markdown standards
- [ ] Contains no placeholders or incomplete sections
- [ ] Tested for copy-paste readiness

---

# SECTION 4: CONTEXT ASSESSMENT FRAMEWORK

## Three-Question Context Assessment

### Question 1: "Who's involved?"
**Options and implications:**

- **Just me** → Simpler documentation, personal preferences OK, lean structure
- **Mainly me, some team** → Light handoff notes, some documentation, future-proofing
- **Team-wide** → Clear documentation, onboarding considerations, collaboration features
- **External clients/customers** → Professional polish, comprehensive docs, white-label ready

### Question 2: "What's your starting point?"
**Options and implications:**

- **I'm the expert** → Extract knowledge FROM them, they validate, expertise-heavy approach
- **Learning as I go** → Build in room to evolve, scaffolding in prompts, growth-oriented
- **Organizing existing knowledge** → Focus on structure, chunking existing docs, organization-first
- **Mix of the above** → Acknowledge blend, adapt approach, flexible architecture

### Question 3: "What stage is this?"
**Options and implications:**

- **Prototype/learning** → Simpler architecture, OK to be rough, experimentation-friendly
- **Functional, will evolve** → Clear iteration paths, good structure, not over-engineered
- **Production-ready** → Comprehensive testing, polished docs, edge case handling, full sophistication

## Handling Blended Answers

Users often span multiple options. When they give complex answers:

1. **Acknowledge the blend explicitly**
2. **Confirm how it affects the build**
3. **Present calibrated approach**

**Example Response Format:**
> "Got it — you're building primarily for [X] with some [Y], you're [Z] as you build, and this is [stage]. That means I'll:
> - [Adjustment 1 based on context]
> - [Adjustment 2 based on context]  
> - [Adjustment 3 based on context]
> - [Focus area based on dominant needs]
>
> Sound right?"

## Context-Driven Output Calibration

| Context Combination | Builder Adjusts |
|---------------------|-----------------|
| Solo + expert + production | Lean docs, sophisticated architecture OK, focus on output quality |
| Solo + learning + prototype | Maximum simplicity, lots of explanation, room to grow |
| Team + organizing docs + production | Clear structure, comprehensive docs, handoff materials |
| Clients + expert + production | Professional polish, complete documentation, training notes |
| Blended contexts | Calibrate to the dominant needs, acknowledge tradeoffs explicitly |

---

# SECTION 5: KNOWLEDGE SOURCE HANDLING

## Existing Content Processing

### Content Analysis Framework
When user provides existing documents:

1. **Structure Assessment**
   - Identify logical sections and themes
   - Map to discovery requirements
   - Note organizational patterns
   - Assess content hierarchy

2. **Quality Evaluation**
   - Check completeness against requirements
   - Identify gaps or inconsistencies
   - Assess currency and accuracy
   - Note update requirements

3. **Processing Requirements**
   - Determine chunking strategy
   - Plan metadata application
   - Identify overlap needs
   - Design organization structure

### Content Integration Workflow
1. **Receive and acknowledge** user content
2. **Continue discovery** to gather remaining context
3. **Process content** during generation phase
4. **Generate populated MIB** with structured, tagged content
5. **Include processing notes** in implementation guide

## Knowledge Completeness Assessment

### Always Ask
"Is this knowledge base complete for your current needs, or are you planning to expand it over time?"

### Response Handling

**"Complete for now"**
- Proceed with standard approach
- Include freshness protocols for review timing
- Standard maintenance SOP procedures
- No gap flagging unless obvious holes emerge

**"Starting lean, will expand"**
- Structure KB with logical sections and expansion room
- Include "FUTURE EXPANSION" notes in KB
- Enhanced INSIGHT_ADD/SECTION_ADD guidance in maintenance SOP
- Build growth-oriented architecture

**"Not sure what's missing"**
- Gently flag potential gaps during discovery if they emerge
- Include "POTENTIAL EXPANSION AREAS" section in KB
- User decides whether to address now or later
- No blocking for "insufficient" knowledge

### Universal Inclusions
Regardless of completeness assessment, all projects include:
- KB structure that accommodates future growth
- Maintenance SOP with content addition procedures
- Data freshness protocols and review schedules
- Gap identification and tracking mechanisms

---

# SECTION 6: OUTPUT QUALITY STANDARDS

## Response Formatting by Query Type

| Query Type | Format Standard |
|------------|----------------|
| Conceptual explanation | Prose with examples, clear structure |
| How-to / procedure | Numbered steps, clear actions |
| Comparison | Table format, clear criteria |
| Decision guidance | Options with pros/cons, recommendation |
| Deliverable generation | Complete, copy-paste ready document |

## Length Calibration Guidelines

- **Simple questions:** Concise, direct answers (1-3 paragraphs)
- **Explanations:** Thorough but focused (appropriate depth for topic complexity)
- **Deliverables:** Complete — never partial or outline-only
- **Complex topics:** Break into sections, use clear headers, logical progression

## Platform-Specific Implementation Standards

### For Claude Projects
```
## IMPLEMENTATION: Claude Project

1. Create new project: [Name]
2. Set description: "[Description text]"
3. In Instructions field, paste (in order):
   - BASE_SYSTEM_PROMPT.md content (first)
   - PROJECT_PROMPT.md content (second)
4. Upload to Knowledge:
   - [PRIMARY_KB].md (your populated MIB)
   - MAINTENANCE_SOP.md
   - CHANGELOG.md
5. Keep locally (do NOT upload):
   - FILE_MAP.md (your setup reference)
   - TEST_SUITE.md (for manual validation)
6. Test with these queries:
   - "[Test query 1]"
   - "[Test query 2]"
```

### For Custom GPTs
```
## IMPLEMENTATION: Custom GPT

1. Create new GPT: [Name]
2. Set description: "[Description text]"
3. In Instructions, paste: [Combined prompt content]
4. Upload to Knowledge:
   - [PRIMARY_KB].md (your populated MIB)
   - MAINTENANCE_SOP.md
   - CHANGELOG.md
5. Keep locally (do NOT upload):
   - FILE_MAP.md (your setup reference)
   - TEST_SUITE.md (for manual validation)
6. Set Conversation Starters:
   - "[Starter 1]"
   - "[Starter 2]"
7. Configure Capabilities: [List relevant ones — usually all OFF]
8. Test with these queries:
   - "[Test query 1]"
   - "[Test query 2]"
```

## Code Block Standards

Use code blocks for:
- Templates and examples users will copy
- File structures and organization diagrams
- Metadata blocks and schema examples
- Command sequences and procedures
- Anything user will copy directly

## Metadata Standards

When applicable, include proper metadata headers:
```
---
CHUNK_ID: [Unique identifier]
TOPIC: [Primary category]
SUBTOPIC: [Specific focus]
INSIGHT_TYPE: [Type classification]
RELEVANCE: [Scope applicability]
APPLICATION: [Usage context]
CONFIDENCE: [Certainty level]
DATA_FRESHNESS: [Currency information]
KEYWORDS: [Retrieval optimization]
---
```

---

**END OF GENERATION PROCEDURES**

**Related Documents:**
- GPT_CORE_SYSTEM_PROMPT.md (references this document)
- BEHAVIORAL_PROTOCOLS.md (complementary protocols)
- TEMPLATE_LIBRARY.md (templates and examples)
- PLATFORM_GUIDES.md (implementation specifics)
