# MASTER METHODOLOGY BRIEF
## The Complete Framework for Building Effective GPTs and Claude Projects

**Document Type:** Master Methodology  
**Version:** 2.0 (GPT Optimization Update)  
**Last Updated:** 2025-02-09  
**Status:** Active

---

## CHANGELOG

| Version | Date | Type | Description |
|---------|------|------|-------------|
| 2.0 | 2025-02-09 | MAJOR_UPDATE | Added GPT optimization framework - hybrid architecture for Custom GPT 8K character limit |
| 1.0 | 2025-01-20 | INITIAL | Initial release |

---

## TABLE OF CONTENTS

1. Foundations
2. Discovery — Clarifying Questions Framework
3. Agent Taxonomy & Design Patterns
4. System Prompt Architecture
5. Knowledge Base Design
6. Chunking & Retrieval Optimization
7. Metadata Schema
8. Lens Documents (Multi-Project)
9. Maintenance & Versioning
10. Testing & Validation
11. File Organization
12. Implementation Guidance

Appendix A: Templates  
Appendix B: Example Build — AI Consultancy  
Appendix C: Glossary  
Appendix D: Platform-Specific Notes

---

# SECTION 1: FOUNDATIONS

---
CHUNK_ID: MMB-1.1-001
TOPIC: foundations
SUBTOPIC: knowledge_systems_vs_chatbots
INSIGHT_TYPE: concept
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: knowledge system, chatbot, RAG, retrieval, architecture
---

## 1.1 Knowledge Systems vs. Chatbots

Most people building Custom GPTs or Claude Projects create chatbots — they write instructions and maybe upload some files. The result works for simple tasks but fails when complexity increases. The chatbot retrieves wrong information, forgets context, gives inconsistent answers, and degrades over time as knowledge becomes stale.

A knowledge system is fundamentally different. It treats the AI not as a chatbot with instructions, but as an intelligent interface to a structured knowledge base. The architecture ensures the right information surfaces for the right queries. Behavioral protocols handle uncertainty, staleness, and edge cases gracefully. Maintenance procedures keep the system accurate over time.

The difference is not capability — it's architecture. The same underlying AI model performs dramatically better when connected to well-structured knowledge through retrieval-optimized design.

---
CHUNK_ID: MMB-1.1-002
TOPIC: foundations
SUBTOPIC: rag_without_infrastructure
INSIGHT_TYPE: concept
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: RAG, retrieval, embedding, vector database, native retrieval
---

## 1.2 RAG-Like Behavior Without RAG Infrastructure

Retrieval-Augmented Generation (RAG) typically requires vector databases, embedding models, and custom infrastructure. Most users building GPTs or Projects cannot implement this. However, both platforms have native retrieval capabilities — they automatically chunk uploaded documents and retrieve relevant sections based on queries.

The methodology in this document optimizes for native retrieval. By structuring documents with proper chunking, adding metadata that aids retrieval, and using boundary overlap to preserve context, you achieve RAG-like precision without building infrastructure. The key insight is that retrieval quality depends more on how you structure information than on the retrieval mechanism itself.

Native retrieval has limitations — it lacks the fine-grained control of custom RAG. But for most use cases, well-structured content with native retrieval outperforms poorly-structured content with sophisticated retrieval.

---
CHUNK_ID: MMB-1.2-001
TOPIC: foundations
SUBTOPIC: build_workflow
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: workflow, process, discovery, architecture, generation, implementation, maintenance
---

## 1.3 The Build Workflow

Effective GPT/Project creation follows a five-phase workflow:

**Phase 1: Discovery**
Understand what needs to be built through structured questioning. Determine purpose, audience, knowledge sources, behavioral requirements, and scale (single vs. multi-project). Never skip discovery — assumptions lead to rework.

**Phase 2: Architecture**
Design the system structure based on discovery findings. Determine document types, chunking strategy, metadata approach, and file organization. For multi-project systems, design the Universal/Shared/Project-Specific structure.

**Phase 3: Generation**
Create all required documents — system prompts, knowledge base files, lens documents (if applicable), maintenance SOPs. Apply chunking and metadata. Ensure copy-paste readiness.

**Phase 4: Implementation**
Deploy to the target platform. Paste prompts, upload knowledge files, configure settings. Test retrieval and behavior.

**Phase 5: Maintenance**
Ongoing updates as knowledge changes. Follow update procedures, maintain changelogs, perform periodic reviews.

Each phase builds on the previous. Skipping phases or rushing through them creates systems that fail under real-world use.

---
CHUNK_ID: MMB-1.3-001
TOPIC: foundations
SUBTOPIC: single_vs_multi_project
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: single project, multi-project, architecture, lens documents, shared knowledge
---

## 1.4 Single-Project vs. Multi-Project Architecture

The first architectural decision is scale: Are you building one GPT/Project, or a system of multiple related projects?

**Single-Project Architecture**

Appropriate when:
- One clear purpose
- One primary audience
- Self-contained knowledge (not shared with other projects)
- Straightforward maintenance (one person, one system)

Structure:
- One combined system prompt
- Knowledge base documents specific to this project
- Maintenance SOP
- Changelog

**Multi-Project Architecture**

Appropriate when:
- Multiple use cases sharing common knowledge
- Different audiences needing different views of the same information
- Need for consistent behavior across related tools
- Team maintenance across multiple projects

Structure:
- Universal documents (shared by ALL projects): Master knowledge brief, base system prompt, maintenance SOP
- Shared documents (used by SOME projects): Style guides, templates, reference materials
- Project-specific documents: Lens documents, project prompts, project-specific knowledge

The multi-project architecture requires more upfront investment but pays dividends in consistency and maintainability. When knowledge updates, you update the source once and sync to all projects — rather than updating each project individually and risking drift.

---
CHUNK_ID: MMB-1.4-001
TOPIC: foundations
SUBTOPIC: maintenance_first_class
INSIGHT_TYPE: concept
RELEVANCE: both
APPLICATION: maintenance
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: maintenance, updates, decay, freshness, evergreen
---

## 1.5 Maintenance as a First-Class Feature

Knowledge decays. Market data becomes stale. Best practices evolve. Platform features change. A GPT/Project built today will degrade over time unless maintenance is planned from the start.

Most builders treat maintenance as an afterthought — something to figure out later. This leads to systems that become increasingly unreliable, with no clear process for updates and no way to track what changed when.

This methodology treats maintenance as a first-class feature:
- Every document includes freshness metadata
- System prompts include staleness flagging protocols
- Maintenance SOPs define update procedures by type
- Changelogs track all modifications
- Archive procedures preserve historical versions

Building maintenance into the architecture from day one is far easier than retrofitting it later. The incremental effort during creation prevents significant pain during operation.

---

# SECTION 2: DISCOVERY — CLARIFYING QUESTIONS FRAMEWORK

---
CHUNK_ID: MMB-2.1-001
TOPIC: discovery
SUBTOPIC: why_discovery_matters
INSIGHT_TYPE: concept
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: discovery, requirements, clarifying questions, garbage in garbage out
---

## 2.1 Why Discovery Matters

The quality of a GPT/Project is determined before any document is written. Discovery — the process of understanding what needs to be built — is where most projects succeed or fail.

Common failure modes from inadequate discovery:
- Building for the wrong audience (too technical, too simple)
- Missing critical knowledge sources
- Unclear behavioral boundaries (what should it refuse?)
- Wrong output formats (user wanted tables, got prose)
- Single-project approach when multi-project was needed

Discovery is not about asking every possible question. It's about asking the right questions in the right sequence to surface requirements that the user may not have articulated — or even recognized.

A thorough discovery conversation takes 10-15 minutes. Skipping it costs hours of rework when the built system doesn't match actual needs.

---
CHUNK_ID: MMB-2.2-001
TOPIC: discovery
SUBTOPIC: question_sequence
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: question sequence, discovery flow, requirements gathering
---

## 2.2 The Discovery Question Sequence

Discovery follows a logical sequence, with each category building on previous answers:

**1. Scale & Structure (Ask First)**
"Is this a single GPT/Project, or a system of multiple related projects?"

This question comes first because the answer shapes everything else. Multi-project systems require different architecture, different documentation, different maintenance approaches.

**2. Purpose & Goals**
- What is the primary job this GPT/Project needs to do?
- What does success look like? How will you know it's working?
- What should it explicitly NOT do?

**3. Target Audience**
- Who will use this?
- What is their technical sophistication?
- What do they already know vs. need to learn?

**4. Knowledge Sources**
- What documents, data, or expertise should it have access to?
- How current does the information need to be?
- Are there authoritative sources it should prioritize?

**5. Behavioral Requirements**
- What tone and communication style?
- What formats for outputs (prose, lists, tables, code)?
- What topics or actions are off-limits?

**6. Output Requirements**
- What specific deliverables should it produce?
- What length and detail level?
- Are there templates or examples to follow?

**7. Constraints & Boundaries**
- What should it never assume?
- What should trigger clarification vs. proceeding?
- Are there compliance, legal, or policy constraints?

---
CHUNK_ID: MMB-2.3-001
TOPIC: discovery
SUBTOPIC: decision_trees
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: decision tree, follow-up questions, conditional logic
---

## 2.3 Decision Trees — Conditional Follow-Up Questions

Some answers unlock additional questions. Recognizing these branch points prevents missing critical requirements.

**Scale Decision Tree:**
```
Q: "Is this a single project or multiple related projects?"
│
├── Single Project
│   └── Continue to Purpose & Goals
│
└── Multiple Projects
    ├── Q: "Do they share a common knowledge base?"
    │   ├── Yes → Plan Universal/Shared/Project-Specific structure
    │   └── No → Treat as separate single projects
    │
    └── Q: "How many projects? Who maintains them?"
        └── Affects sync complexity and documentation needs
```

**Knowledge Source Decision Tree:**
```
Q: "What knowledge sources should it have?"
│
├── Existing Documents
│   └── Q: "Are these final or will they update?"
│       ├── Final → Standard KB approach
│       └── Updates expected → Plan maintenance procedures
│
├── Expertise (No Documents)
│   └── Q: "Can we document this expertise now?"
│       ├── Yes → Create knowledge documents together
│       └── No → Limited to prompt-based guidance
│
└── External/Dynamic Data
    └── Q: "How current must it be?"
        ├── Real-time → May need API integration (outside scope)
        └── Periodic → Plan update schedule
```

**Behavioral Decision Tree:**
```
Q: "What tone and style?"
│
├── Professional/Formal
│   └── Q: "Industry-specific terminology?"
│       └── Affects vocabulary and examples
│
├── Casual/Conversational
│   └── Q: "Any boundaries on informality?"
│       └── Affects humor, emoji, slang usage
│
└── Adaptive (varies by context)
    └── Q: "What signals should trigger which tone?"
        └── Build conditional behavior into prompt
```

---
CHUNK_ID: MMB-2.4-001
TOPIC: discovery
SUBTOPIC: red_flags
INSIGHT_TYPE: warning
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: red flags, warning signs, unclear requirements, scope creep
---

## 2.4 Red Flags — When to Pause Before Building

Certain answers indicate the user needs more clarity before building can proceed effectively:

**"It should do everything"**
No clear priority means no clear architecture. Push for: "If it could only do one thing well, what would that be?"

**"I'm not sure who will use it"**
Unknown audience means unknown tone, depth, and format. Cannot optimize for everyone.

**"The documents aren't ready yet"**
Building without knowledge sources creates a shell. Better to wait or help create the documents first.

**"Just make it smart"**
Vague behavioral requirements lead to unpredictable behavior. Need specific guidance on tone, boundaries, outputs.

**"We'll figure out maintenance later"**
Maintenance deferred is maintenance ignored. At minimum, establish who owns updates and how often.

**Conflicting requirements**
"Be thorough but keep it short." "Be formal but friendly." Surface conflicts and force resolution before building.

When red flags appear, pause building and resolve the underlying ambiguity. Building on unclear foundations wastes everyone's time.

---

# SECTION 3: AGENT TAXONOMY & DESIGN PATTERNS

---
CHUNK_ID: MMB-3.1-001
TOPIC: agent_taxonomy
SUBTOPIC: ten_agent_types
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: agent types, taxonomy, classification, design patterns
---

## 3.1 The Ten Agent Types

Every GPT/Project has a primary function that maps to one of ten agent types. Identifying the type guides architectural and behavioral decisions.

| # | Type | Core Function | Typical Outputs |
|---|------|---------------|-----------------|
| 1 | Information Retrieval | Extract, summarize, analyze, compare data | Reports, summaries, comparisons |
| 2 | Creative Generation | Generate stories, scripts, creative works | Fiction, scripts, creative content |
| 3 | Technical | Solve technical problems, produce code | Code, technical documentation, debugging |
| 4 | Educational/Tutoring | Teach or explain topics | Lessons, explanations, curricula |
| 5 | Business/Operations | Create SOPs, workflows, documentation | Process documents, workflows, templates |
| 6 | Strategy/Advisory | Provide structured thinking and strategic insight | Recommendations, frameworks, analysis |
| 7 | Support/Communication | Handle conversations, FAQs, inquiries | Responses, FAQs, customer communication |
| 8 | Personal Productivity | Task management, organization | Lists, schedules, organization systems |
| 9 | Content Creation | Create posts, emails, ads, marketing copy | Marketing content, copy, social posts |
| 10 | Specialized Domain | Highly specific domain expertise | Domain-specific outputs |

Most projects have a **primary type** that dominates and a **secondary type** that influences. For example, a project that creates marketing content (Content Creation) informed by market research (Information Retrieval) has Content Creation as primary and Information Retrieval as secondary.

---
CHUNK_ID: MMB-3.2-001
TOPIC: agent_taxonomy
SUBTOPIC: behavioral_implications
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: behavior, tone, format, depth, agent type implications
---

## 3.2 Behavioral Implications by Agent Type

Agent type determines default behaviors that should be encoded in system prompts:

**Strategy/Advisory**
- Tone: Consultative, analytical, balanced
- Format: Structured recommendations with rationale
- Depth: Comprehensive, covering tradeoffs
- Style: Present options, not just answers

**Content Creation**
- Tone: Calibrated to target audience
- Format: Publication-ready, minimal editing needed
- Depth: As specified by content requirements
- Style: Persuasive where appropriate, voice-consistent

**Educational/Tutoring**
- Tone: Clear, encouraging, patient
- Format: Scaffolded complexity, builds progressively
- Depth: Appropriate to learner level
- Style: Examples before abstractions, check understanding

**Support/Communication**
- Tone: Helpful, efficient, empathetic
- Format: Conversational, appropriately brief
- Depth: Answer the question, offer relevant follow-up
- Style: De-escalation aware, solution-focused

**Information Retrieval**
- Tone: Neutral, precise, objective
- Format: Organized findings, clear sourcing
- Depth: Thorough within scope
- Style: Distinguish fact from interpretation

**Technical**
- Tone: Precise, unambiguous
- Format: Code with comments, step-by-step procedures
- Depth: Implementation-ready
- Style: Explain reasoning, anticipate edge cases

These defaults can be overridden by specific project requirements, but provide sensible starting points.

---
CHUNK_ID: MMB-3.3-001
TOPIC: agent_taxonomy
SUBTOPIC: type_combinations
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: primary type, secondary type, combination, hybrid
---

## 3.3 Common Type Combinations

Effective projects often combine types. Common pairings and their implications:

**Content Creation + Strategy/Advisory**
Creates content informed by strategic thinking. Outputs are publication-ready but grounded in market awareness and positioning. Common for marketing and thought leadership projects.

**Educational/Tutoring + Content Creation**
Teaches through content. Creates learning materials that are both instructive and engaging. Common for training and course development projects.

**Strategy/Advisory + Business/Operations**
Provides strategic recommendations AND operational documentation. Can both advise on what to do and document how to do it. Common for consulting-support projects.

**Support/Communication + Information Retrieval**
Answers questions by retrieving from knowledge base. The support layer handles conversation; the retrieval layer provides accurate information. Common for customer service and FAQ projects.

**Technical + Educational/Tutoring**
Solves technical problems while teaching. Explains reasoning, not just solutions. Common for developer tools and learning platforms.

When combining types, the primary type dominates tone and format. The secondary type influences depth and approach.

---

# SECTION 4: SYSTEM PROMPT ARCHITECTURE

---
CHUNK_ID: MMB-4.1-001
TOPIC: system_prompts
SUBTOPIC: two_layer_system
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: base prompt, project prompt, two-layer, system prompt architecture
---

## 4.1 The Two-Layer System

Effective system prompts use a two-layer architecture:

**Layer 1: Base System Prompt**
Universal behaviors that apply regardless of specific query:
- Core identity and role
- Retrieval configuration
- Data freshness handling
- Confidence weighting
- Error handling
- Maintenance mode triggers

**Layer 2: Project System Prompt**
Project-specific behaviors and context:
- Project mission and scope
- KB integration (which documents, what priorities)
- Specific behavioral guidance
- Output standards and templates
- Cross-project coordination (if multi-project)

**Why Two Layers?**

Separation of concerns. The base prompt handles "how to behave as an AI assistant connected to a knowledge base." The project prompt handles "what this specific project does and how."

For single-project builds, both layers can be combined into one prompt. For multi-project builds, the base prompt stays constant while project prompts vary — ensuring consistent foundational behavior with project-specific adaptation.

In Claude Projects, paste base prompt first, then project prompt. In Custom GPTs, use hybrid architecture: core prompt (~7.5K chars) in Instructions field + extended protocols in Knowledge Base if sophisticated functionality needed.

---
CHUNK_ID: MMB-4.2-001
TOPIC: system_prompts
SUBTOPIC: base_prompt_sections
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: base prompt, sections, structure, core identity, retrieval
---

## 4.2 Base System Prompt Structure

The base system prompt should include these sections:

**CORE IDENTITY**
Who the assistant is, its expertise, its relationship to the user. Sets the foundational frame for all interactions.

```
You are [Role], an expert in [Domain]. Your purpose is [Mission].
Your approach: [Key principles that guide behavior].
```

**RETRIEVAL CONFIGURATION**
How to use the knowledge base:
- Standard mode: What to retrieve, what to prioritize
- Maintenance mode: When triggered, what changes
- Exclusions: What to never retrieve in normal operation (e.g., maintenance SOPs)

**DATA FRESHNESS PROTOCOL**
How to handle temporal information:
- Thresholds by content type (when to flag as potentially stale)
- Flagging language (how to communicate uncertainty)
- Verification suggestions (when to recommend checking current sources)

**CONFIDENCE WEIGHTING**
How to present information based on certainty:
- Established facts: State directly
- Recommendations: Frame as "recommended approach"
- Experimental: Frame as "promising but unproven"
- Contrarian views: Present as alternative perspective

**SPEC CONFIRMATION PROTOCOL**
When and how to confirm understanding before generating:
- Triggers (complex requests, ambiguous requirements)
- Confirmation format
- When to proceed without confirmation

**ERROR HANDLING**
What to do when things go wrong:
- Missing information: Ask specific clarifying questions
- Conflicting information: Surface conflict, ask user to resolve
- Outside scope: Acknowledge limitation, suggest alternatives

**MAINTENANCE MODE**
How to handle update requests:
- Trigger phrases that activate maintenance mode
- Procedures to follow
- Classification framework for updates

---
CHUNK_ID: MMB-4.3-001
TOPIC: system_prompts
SUBTOPIC: project_prompt_sections
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: project prompt, sections, structure, mission, KB integration
---

## 4.3 Project System Prompt Structure

The project system prompt should include these sections:

**PROJECT MISSION**
What this specific project accomplishes. Be precise about scope — what it does AND what it doesn't do.

```
This project [primary function]. Use it for [specific use cases].
Do NOT use this project for [out of scope items] — use [alternative] instead.
```

**KB INTEGRATION**
How to use this project's knowledge base:
- Which documents exist and their purposes
- Retrieval priorities (which docs for which queries)
- Weights (primary sources vs. supporting sources)

```
| Document | Priority | Use For |
|----------|----------|---------|
| [Doc 1] | PRIMARY | [Query types] |
| [Doc 2] | SUPPORTING | [Query types] |
```

**BEHAVIORAL GUIDANCE**
Project-specific behavior rules:
- Tone and style requirements
- What to always include
- What to avoid
- Special handling instructions

**OUTPUT STANDARDS**
What outputs should look like:
- Formats (prose, lists, tables, code)
- Length guidelines
- Template references
- Quality checklist

**CROSS-PROJECT COORDINATION** (Multi-project only)
How this project relates to others:
- Handoff procedures
- Shared context
- When to direct users to other projects

---
CHUNK_ID: MMB-4.4-001
TOPIC: system_prompts
SUBTOPIC: spec_confirmation
INSIGHT_TYPE: procedure
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: spec confirmation, verify understanding, complex requests
---

## 4.4 Spec Confirmation Protocol

Before generating complex deliverables, confirm understanding to prevent wasted effort.

**When to Confirm:**
- Multi-step or multi-document requests
- Requests with implicit requirements
- Ambiguous or underspecified requests
- High-effort outputs (long documents, complex systems)

**When to Proceed Without Confirmation:**
- Simple, clear questions
- Single-concept explanations
- User has provided detailed specifications
- Follow-up to already-confirmed work

**Confirmation Format:**
```
Before I build this, let me confirm my understanding:

**[Key Dimension 1]:** [Your interpretation]
**[Key Dimension 2]:** [Your interpretation]
**[Key Dimension 3]:** [Your interpretation]

Is this correct, or should I adjust anything?
```

**Example:**
```
Before I create this system prompt, let me confirm:

**Project Type:** Single Claude Project for customer support
**Agent Type:** Support/Communication primary, Information Retrieval secondary
**Tone:** Professional but warm, de-escalation aware
**Knowledge Sources:** FAQ document, product specs, return policy
**Key Outputs:** Customer responses, escalation summaries

Is this correct?
```

After confirmation, proceed with generation. Reference the confirmed spec if questions arise during generation.

---

# SECTION 5: KNOWLEDGE BASE DESIGN

---
CHUNK_ID: MMB-5.1-001
TOPIC: kb_design
SUBTOPIC: document_types
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: document types, KB files, master brief, methodology, reference, templates
---

## 5.1 Document Types and Their Purposes

Knowledge bases contain different document types, each serving a specific function:

**Master Intelligence/Methodology Brief**
Comprehensive domain knowledge organized for retrieval. The "brain" of the system. Contains everything the project needs to know about its domain, properly chunked with metadata.

Use when: Deep domain expertise is required, multiple topics must be covered, retrieval precision matters.

**Reference Documents**
Lookup information — facts, data, specifications that need to be retrieved accurately but don't require extensive context.

Use when: Quick-access data is needed, information is relatively static, precision matters more than explanation.

**Methodology/Process Documents**
How-to procedures, workflows, step-by-step guides. Teach the system how to DO things, not just know things.

Use when: The project guides users through processes, consistency of approach matters, procedures may update.

**Template Libraries**
Reusable patterns for common outputs. Ensure consistency when generating similar deliverables.

Use when: Project produces recurring output types, format consistency matters, templates reduce generation time.

**SOP Documents**
Operational procedures for maintaining the system itself. Maintenance SOPs, update procedures, troubleshooting guides.

Use when: System requires ongoing maintenance, multiple maintainers need consistent procedures, updates are expected.

---
CHUNK_ID: MMB-5.2-001
TOPIC: kb_design
SUBTOPIC: consolidation_vs_separation
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: consolidation, separation, document organization, retrieval
---

## 5.2 When to Consolidate vs. Separate Documents

**Consolidate When:**
- Content is closely related and often needed together
- Separation would orphan fragments (statistics without context)
- Maintaining sync across multiple files would be burdensome
- Total content fits comfortably in one well-organized document

**Separate When:**
- Content serves distinctly different purposes
- Different update frequencies (some content changes often, some rarely)
- Different audiences or projects need different subsets
- Document would exceed practical size (~50 pages / ~20,000 words)

**The Consolidation Test:**
Ask: "If I update this content, what else must I update at the same time?"

Content that updates together should live together. Content that updates independently can live separately.

**Common Mistake:**
Over-separation — creating many small files that fragment related information. This hurts retrieval (related content doesn't surface together) and hurts maintenance (updates require touching many files).

When in doubt, consolidate. A well-organized single document retrieves better than scattered fragments.

---
CHUNK_ID: MMB-5.3-001
TOPIC: kb_design
SUBTOPIC: file_naming
INSIGHT_TYPE: procedure
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: file naming, naming convention, organization
---

## 5.3 File Naming Conventions

Consistent naming aids organization and retrieval. Use this pattern:

```
[TYPE]_[DOMAIN]_[SPECIFICITY].md

Examples:
MASTER_Customer_Support_Brief.md
LENS_01_Technical_Support.md
SOP_Maintenance.md
TEMPLATE_Email_Responses.md
REF_Product_Specifications.md
```

**Type Prefixes:**
- MASTER_ — Comprehensive knowledge documents
- LENS_ — Project-specific views (multi-project)
- SOP_ — Standard operating procedures
- TEMPLATE_ — Reusable patterns
- REF_ — Reference/lookup documents
- GUIDE_ — How-to guides

**Numbering:**
For multi-project systems, number lens documents and project prompts to maintain order:
- LENS_01_[Project].md
- LENS_02_[Project].md
- PROJECT_PROMPT_01_[Project].md

**Avoid:**
- Spaces in filenames (use underscores)
- Special characters
- Overly long names
- Generic names like "notes.md" or "data.md"

---
CHUNK_ID: MMB-5.4-001
TOPIC: kb_design
SUBTOPIC: building_from_zero
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: no documents, starting from scratch, research, expertise extraction, tacit knowledge
---

## 5.4 Building Knowledge From Zero

Many users want to build an AI project but don't have existing documents. The knowledge exists in their head, in scattered notes, or needs to be researched. This is a valid starting point.

**The "No Documents" Scenario:**
- "I want a GPT that knows my business, but I haven't documented anything"
- "The knowledge is in my head — I just need to get it out"
- "I know what questions it should answer, but I don't have written answers"

**Three Methods for Building Initial Knowledge:**

### Method 1: Deep Research

Use AI research tools (Claude with web search, ChatGPT with browsing, Perplexity) to gather foundational domain knowledge.

**When Deep Research Works Best:**

| Use Case | Value |
|----------|-------|
| Industry best practices | High — consolidates established knowledge |
| Regulatory/compliance info | High — gathers current requirements |
| Technical procedures | Medium — good foundation, needs customization |
| Company-specific processes | Low — requires internal knowledge |
| Proprietary information | None — must come from user |

**Deep Research Workflow:**
1. Research domain fundamentals broadly
2. Identify gaps specific to user's context
3. Research specific sub-topics in depth
4. Customize with user's policies, processes, preferences
5. Structure into proper KB format

### Method 2: Self-Interview

Extract tacit knowledge through structured questioning. The most valuable expertise is often undocumented.

**Self-Interview Topic Areas:**
1. **Frequent Questions** — What do people ask most? What do beginners always ask? What do experienced people still get wrong?
2. **Processes & Procedures** — Walk-throughs of key tasks, step-by-step for common scenarios
3. **Decision Making** — How to choose between options, what factors matter, red flags
4. **Troubleshooting** — What goes wrong, how to diagnose, how to fix
5. **Best Practices** — What separates good from great, advice for beginners, hard-won lessons
6. **Specific Information** — Pricing, policies, contacts, resources

**Self-Interview Process:**
1. Set aside 60-90 minutes
2. Use an AI as interviewer (ask questions one at a time)
3. Focus on how you ACTUALLY do things, not theory
4. Capture exceptions, edge cases, "it depends" situations
5. Convert transcript to structured KB content

### Method 3: Hybrid Approach (Recommended)

Combine research for domain fundamentals with self-interview for specific expertise:

| Knowledge Type | Source |
|----------------|--------|
| Industry fundamentals | Deep Research |
| Best practices | Deep Research + User perspective |
| User's specific processes | Self-Interview |
| User's policies/pricing | Self-Interview |
| User's preferences/style | Self-Interview |
| Edge cases encountered | Self-Interview |

**Hybrid Workflow:**
1. **Research Foundation (1-2 hours)** — Gather domain fundamentals via Deep Research
2. **Extract User Knowledge (1-2 hours)** — Self-interview for specific expertise
3. **Synthesize & Structure (1-2 hours)** — Merge, resolve conflicts (user's way wins), structure for retrieval
4. **Review & Refine (30 minutes)** — Fill gaps, test with sample queries

---
CHUNK_ID: MMB-5.4-002
TOPIC: kb_design
SUBTOPIC: deep_research_prompt
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: deep research, research prompt, domain knowledge, gathering content
---

## 5.4.1 Deep Research Prompt Template

When user needs to gather domain knowledge, provide this prompt for use with research-capable AI:

```
I'm building a knowledge base for a [TYPE] AI assistant that helps [AUDIENCE] with [PURPOSE].

Please research and compile comprehensive information on:

**Core Topics:**
1. [Topic area 1]
2. [Topic area 2]
3. [Topic area 3]
4. [Topic area 4]

**For each topic, gather:**
- Key concepts and definitions
- Standard procedures or processes
- Industry best practices
- Frequently asked questions (and answers)
- Common mistakes and how to avoid them
- Relevant regulations or requirements (if applicable)

**Research Parameters:**
- Industry/Domain: [specify]
- Audience expertise: [beginner / intermediate / advanced]
- Content priority: [practical how-to / conceptual / regulatory]

**Output Format:**
Structure findings as section summaries, detailed content by subtopic, FAQ compilation, and quick reference. Format for easy conversion to knowledge base chunks (600-1000 tokens per logical section).
```

---
CHUNK_ID: MMB-5.4-003
TOPIC: kb_design
SUBTOPIC: self_interview_prompt
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: self-interview, knowledge extraction, tacit knowledge, expertise capture
---

## 5.4.2 Self-Interview Prompt Template

When user needs to extract their own expertise, provide this prompt:

```
You're going to interview me to extract knowledge for a [TYPE] AI assistant that helps [AUDIENCE] with [PURPOSE].

**Interview Instructions:**
1. Ask me ONE question at a time
2. After each answer, either ask a follow-up to go deeper OR move to the next topic
3. Push me for specifics — don't let me stay vague
4. Ask for examples when I make general claims
5. Capture exceptions, edge cases, and "it depends" situations

**Focus Areas:**
- How I actually do things (not just theory)
- Decision-making frameworks
- Common problems and solutions
- Lessons learned the hard way
- Specific details (numbers, timelines, policies)

**Topics to Cover:**
1. Most common questions/tasks
2. Key processes (walk-throughs)
3. Decision making (how to choose)
4. Troubleshooting (what goes wrong)
5. Best practices and tips
6. Specific information (pricing, policies, contacts)

Start with: "What's the most common question or problem you help people with?"
```

**After interview, convert with:**

```
Here is my interview transcript about [DOMAIN]:

[PASTE TRANSCRIPT]

Transform this into structured knowledge base content:
1. Organize by topic (4-7 main sections)
2. Chunk into 600-1000 token segments
3. Add metadata headers (TOPIC, SUBTOPIC, TYPE, KEYWORDS)
4. Preserve my voice and specific insights
5. Include a Quick Reference section
```

---

# SECTION 6: CHUNKING & RETRIEVAL OPTIMIZATION

---
CHUNK_ID: MMB-6.1-001
TOPIC: chunking
SUBTOPIC: why_chunking_matters
INSIGHT_TYPE: concept
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: chunking, retrieval, context window, precision
---

## 6.1 Why Chunking Matters

When you upload a document to a GPT or Claude Project, the platform doesn't load the entire document into context for every query. That would exhaust context windows quickly. Instead, it chunks the document and retrieves relevant chunks based on the query.

This means retrieval quality depends heavily on how content is chunked:
- **Poor chunking:** Wrong chunks surface, right information buried, context lost
- **Good chunking:** Relevant information surfaces, context preserved, precise retrieval

You don't control the platform's chunking algorithm directly. But you control how you structure content — and well-structured content chunks predictably, while poorly-structured content chunks unpredictably.

The goal: Structure content so that however the platform chunks it, meaningful units stay together and can be retrieved independently while maintaining connections to related content.

---
CHUNK_ID: MMB-6.2-001
TOPIC: chunking
SUBTOPIC: optimal_chunk_size
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: chunk size, tokens, 600-1000 tokens
---

## 6.2 Optimal Chunk Size

Target chunk size: **600-1000 tokens** (roughly 450-750 words)

**Why this range?**

Too small (under 400 tokens):
- Fragments lose context
- Statistics separated from interpretation
- Increased retrieval noise (more chunks, harder to rank)

Too large (over 1200 tokens):
- Retrieval pulls irrelevant content alongside relevant
- Harder to achieve precision
- May hit retrieval limits on some platforms

The 600-1000 range balances:
- Enough context to be self-contained
- Small enough for precise retrieval
- Alignment with typical platform chunk sizes

**Practical Application:**
When writing content, think in "chunk-sized" sections. Each major subsection should be roughly 600-1000 tokens. Use headers and clear section breaks to signal chunk boundaries.

---
CHUNK_ID: MMB-6.3-001
TOPIC: chunking
SUBTOPIC: boundary_overlap
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: boundary overlap, transitions, context preservation
---

## 6.3 Boundary Overlap Technique

When content spans chunks, logical connections can be lost. Boundary overlap addresses this by repeating transitional content at chunk boundaries.

**The Technique:**

Repeat 1-2 transitional sentences at the end of one chunk and the beginning of the next. This ensures logical connections survive regardless of which chunk retrieves.

**Example:**

```
[Chunk A ends:]
...these three factors determine pricing strategy. The relationship 
between market positioning and price point is particularly critical
for new market entrants.

[Chunk B begins:]
The relationship between market positioning and price point is 
particularly critical for new market entrants. When setting initial 
prices, consider...
```

**When to Use Boundary Overlap:**
- Conceptual continuity (idea spans sections)
- Causal relationships (cause in one section, effect in next)
- Sequential processes (steps that must be understood in order)
- Statistics and interpretation (number in one place, meaning in another)

**When It's Not Needed:**
- Clearly independent sections
- Topic changes (new header, new subject)
- Reference/lookup content (standalone facts)

The redundancy is intentional. It's a small cost in storage for significant gain in retrieval quality.

---
CHUNK_ID: MMB-6.4-001
TOPIC: chunking
SUBTOPIC: good_chunk_boundaries
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: chunk boundaries, headers, sections, natural breaks
---

## 6.4 What Makes a Good Chunk Boundary

Good chunk boundaries occur at natural conceptual breaks:

**Strong Boundaries (place breaks here):**
- Header changes (new section, new topic)
- Completed concept (full idea expressed)
- Perspective shifts (from description to recommendation)
- Temporal breaks (past to present, present to future)

**Weak Boundaries (avoid breaks here):**
- Mid-paragraph
- Between statistic and interpretation
- Between cause and effect
- Between question and answer
- Between claim and evidence

**Structural Signals:**
Use document structure to signal boundaries:
- Clear headers and subheaders
- Horizontal rules between major sections
- Consistent section lengths (targeting 600-1000 tokens)
- Metadata blocks between chunks (where applicable)

**The Self-Containment Test:**
For each potential chunk, ask: "If this chunk retrieves alone, does it make sense? Does it provide enough context to be useful?"

If yes, it's a good chunk. If it depends critically on adjacent content to make sense, the boundary is in the wrong place or needs overlap.

---
CHUNK_ID: MMB-6.5-001
TOPIC: chunking
SUBTOPIC: common_mistakes
INSIGHT_TYPE: warning
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: chunking mistakes, anti-patterns, common errors
---

## 6.5 Common Chunking Mistakes

**Mistake 1: Orphaned Statistics**
Numbers without context. "The failure rate is 87%." Retrieved alone, this is useless — failure rate of what? In what context? What does it mean?

Fix: Keep statistics with their interpretation. "87% of AI projects fail to deliver expected value, primarily due to adoption challenges rather than technical limitations."

**Mistake 2: Scattered Related Content**
The same concept discussed in multiple places without cross-referencing. Retrieval surfaces one fragment, missing the complete picture.

Fix: Consolidate related content or add explicit cross-references in each location.

**Mistake 3: Overly Long Sections**
2000+ token sections that cover multiple sub-topics. Retrieval has to pull the entire section even when only one sub-topic is relevant.

Fix: Break into focused subsections of 600-1000 tokens each.

**Mistake 4: Overly Short Sections**
100-200 token fragments that lack context. May retrieve accurately but provide insufficient information.

Fix: Combine with related content to reach minimum viable chunk size.

**Mistake 5: No Structural Signals**
Wall-of-text documents with no headers, breaks, or organization. Platform must guess where to chunk.

Fix: Add clear structure with headers, consistent section sizes, and explicit breaks.

---

# SECTION 7: METADATA SCHEMA

---
CHUNK_ID: MMB-7.1-001
TOPIC: metadata
SUBTOPIC: nine_field_schema
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: metadata schema, nine fields, chunk metadata
---

## 7.1 The Nine-Field Metadata Schema

Metadata enhances retrieval by providing structured information about each chunk. This schema uses nine fields:

```
---
CHUNK_ID: [Unique identifier]
TOPIC: [Primary category]
SUBTOPIC: [Specific focus]
INSIGHT_TYPE: [Content classification]
RELEVANCE: [Which projects/contexts need this]
APPLICATION: [What use cases it supports]
CONFIDENCE: [How certain/proven]
DATA_FRESHNESS: [When last validated]
KEYWORDS: [Retrieval helpers]
---
```

**Field Purposes:**

| Field | Purpose | Retrieval Benefit |
|-------|---------|-------------------|
| CHUNK_ID | Unique reference | Cross-referencing, tracking |
| TOPIC | Primary category | Broad filtering |
| SUBTOPIC | Specific focus | Narrow filtering |
| INSIGHT_TYPE | Content classification | Match query intent |
| RELEVANCE | Who needs this | Multi-project filtering |
| APPLICATION | Use cases | Workflow-stage filtering |
| CONFIDENCE | Certainty level | Appropriate framing |
| DATA_FRESHNESS | Currency | Staleness flagging |
| KEYWORDS | Retrieval helpers | Semantic matching |

Metadata appears at the start of each chunk, helping both the retrieval system and the AI understand what the chunk contains and how to use it.

---
CHUNK_ID: MMB-7.2-001
TOPIC: metadata
SUBTOPIC: field_definitions
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: field definitions, CHUNK_ID, TOPIC, SUBTOPIC, INSIGHT_TYPE
---

## 7.2 Field Definitions — Identification and Classification

**CHUNK_ID**
Format: [DOC]-[Section].[Subsection]-[Number]
Example: MMB-4.2-003

Purpose: Unique identifier for cross-referencing. When one chunk refers to another, use CHUNK_ID. When tracking updates in changelog, reference CHUNK_ID.

**TOPIC**
The primary category this chunk belongs to. Should match major section themes. Use consistent values across the document.

Example values: foundations, discovery, agent_taxonomy, system_prompts, kb_design, chunking, metadata, maintenance

**SUBTOPIC**
Specific focus within the topic. More granular than TOPIC but still categorical, not a description.

Example values: 
- Under "chunking": optimal_size, boundary_overlap, common_mistakes
- Under "discovery": question_sequence, red_flags, decision_trees

**INSIGHT_TYPE**
What kind of content this chunk contains:

| Value | Definition | Example |
|-------|------------|---------|
| concept | Foundational idea, definition | "What is chunking" |
| framework | Structured approach, model | "The nine-field metadata schema" |
| procedure | Step-by-step instructions | "How to add a new chunk" |
| example | Illustrative instance | "Example: AI Consultancy build" |
| template | Reusable pattern | "System prompt template" |
| warning | Caution, anti-pattern | "Common chunking mistakes" |

---
CHUNK_ID: MMB-7.3-001
TOPIC: metadata
SUBTOPIC: field_definitions_context
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: RELEVANCE, APPLICATION, CONFIDENCE, DATA_FRESHNESS, KEYWORDS
---

## 7.3 Field Definitions — Context and Currency

**RELEVANCE**
Which projects or contexts need this chunk. Critical for multi-project systems where different projects need different subsets of the master knowledge.

Single-project values: all, primary, supporting
Multi-project values: project names or categories (e.g., "content_projects, marketing_projects")
Universal value: "both" (for content relevant regardless of single/multi structure)

**APPLICATION**
What workflow stages or use cases this chunk supports:

| Value | When Retrieved |
|-------|----------------|
| discovery | During initial requirements gathering |
| architecture | When designing system structure |
| generation | When creating deliverables |
| implementation | When deploying to platform |
| maintenance | When updating the system |

**CONFIDENCE**
How certain or proven this content is:

| Value | Definition | Presentation |
|-------|------------|--------------|
| established | Proven, widely accepted | State directly |
| recommended | Best practice, strong evidence | "Recommended approach..." |
| experimental | Promising but unproven | "Experimental technique..." |

**DATA_FRESHNESS**
When this content was last validated. Format: YYYY-MM or "evergreen"

- Date format for time-sensitive content: 2025-01
- "Evergreen" for content that doesn't age (definitions, core concepts)

**KEYWORDS**
Comma-separated terms that aid retrieval. Include:
- Synonyms for main concepts
- Related terms users might search
- Specific proper nouns if applicable

---
CHUNK_ID: MMB-7.4-001
TOPIC: metadata
SUBTOPIC: metadata_example
INSIGHT_TYPE: example
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: metadata example, well-tagged chunk, complete example
---

## 7.4 Example: A Well-Tagged Chunk

```
---
CHUNK_ID: MMB-6.3-001
TOPIC: chunking
SUBTOPIC: boundary_overlap
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: boundary overlap, transitions, context preservation, chunk boundaries
---

## 6.3 Boundary Overlap Technique

When content spans chunks, logical connections can be lost. Boundary 
overlap addresses this by repeating transitional content at chunk 
boundaries.

[Content continues...]
```

**Why This Tagging Works:**

- CHUNK_ID enables precise reference (MMB-6.3-001)
- TOPIC + SUBTOPIC enable filtering (chunking → boundary_overlap)
- INSIGHT_TYPE indicates this is a framework (structured approach)
- RELEVANCE "both" means it applies to single and multi-project builds
- APPLICATION "generation" indicates when to use it (when creating documents)
- CONFIDENCE "recommended" signals best practice but not universal requirement
- DATA_FRESHNESS "evergreen" means this won't age
- KEYWORDS include synonyms and related terms for retrieval

---
CHUNK_ID: MMB-7.5-001
TOPIC: metadata
SUBTOPIC: when_to_use_metadata
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: when to use metadata, metadata necessity, lightweight metadata
---

## 7.5 When to Use Full vs. Lightweight Metadata

Full nine-field metadata is valuable but adds overhead. Use it strategically:

**Use Full Metadata When:**
- Master knowledge documents (MIBs, methodology briefs)
- Multi-project systems where filtering matters
- Content with varying freshness or confidence
- Documents exceeding 20 chunks
- Retrieval precision is critical

**Use Lightweight Metadata When:**
- Simple reference documents
- Single-project builds with limited KB
- Template libraries
- SOPs (which are already isolated by function)

**Lightweight Schema (4 fields):**
```
---
CHUNK_ID: [Identifier]
TOPIC: [Category]
TYPE: [concept/procedure/template/reference]
UPDATED: [Date or evergreen]
---
```

**No Metadata When:**
- Very short documents (under 5 chunks)
- Self-contained templates
- Platform may not use metadata in retrieval anyway

The goal is retrieval quality, not metadata completeness. If metadata doesn't improve retrieval for your use case, don't add complexity for its own sake.

---

# SECTION 8: LENS DOCUMENTS (MULTI-PROJECT ONLY)

---
CHUNK_ID: MMB-8.1-001
TOPIC: lens_documents
SUBTOPIC: purpose
INSIGHT_TYPE: concept
RELEVANCE: multi_project
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: lens documents, multi-project, project views, shared knowledge
---

## 8.1 What Lens Documents Are

In multi-project architectures, multiple projects share a common knowledge base — typically a Master Intelligence Brief or similar comprehensive document. But each project needs different parts of that knowledge, weighted differently, applied differently.

Lens documents solve this problem. They're project-specific views that tell each project:
- Which sections of the master knowledge are most relevant
- How to weight and prioritize that information
- How to apply the knowledge for this project's specific purpose
- What behavioral adjustments to make
- What gaps exist that need future research

Think of it like this: The master document is a comprehensive library. The lens document is a reading list and study guide customized for a specific course.

**Lens documents do NOT duplicate content.** They reference the master document by section and chunk ID. The master document is the single source of truth; lens documents are navigation layers.

---
CHUNK_ID: MMB-8.2-001
TOPIC: lens_documents
SUBTOPIC: when_needed
INSIGHT_TYPE: framework
RELEVANCE: multi_project
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: when to use lens documents, lens necessity, multi-project decision
---

## 8.2 When Lens Documents Are Needed

**Required When:**
- Multiple projects share a master knowledge document
- Projects serve different audiences with different needs
- Behavioral requirements vary by project
- You need to track which parts of master knowledge apply where

**Not Needed When:**
- Single-project build
- Projects have completely separate knowledge bases (no sharing)
- Project is simple enough that system prompt handles all guidance
- Master document is small enough to use entirely in each project

**The Test:**
"Does this project need a different subset or weighting of the shared knowledge than other projects?"

If yes, create a lens document. If no, the project can use the master document directly with guidance in its project prompt.

---
CHUNK_ID: MMB-8.3-001
TOPIC: lens_documents
SUBTOPIC: structure
INSIGHT_TYPE: template
RELEVANCE: multi_project
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: lens document structure, lens template, sections
---

## 8.3 Lens Document Structure

```markdown
# LENS: [Project Name]

## PURPOSE
What this project accomplishes. Clear scope statement.

## AGENT TYPE CLASSIFICATION
**Primary Type:** [From taxonomy]
**Secondary Type:** [From taxonomy]

**Behavioral Implications:**
- [How the agent types affect this project's behavior]
- [Tone, format, depth implications]

## PRIMARY INTELLIGENCE SECTIONS

Which sections of the master document matter most:

| Section | Weight | Use For |
|---------|--------|---------|
| Section 3 | HIGH | [What queries] |
| Section 7 | HIGH | [What queries] |
| Section 5 | MEDIUM | [What queries] |
| Section 1 | LOW | [What queries] |

## KEY EXTRACTS

Critical chunks this project needs most often:

- **CHUNK_ID:** [ID] — [Why this chunk is critical]
- **CHUNK_ID:** [ID] — [Why this chunk is critical]

## PROJECT-SPECIFIC CONTEXT

How to apply the intelligence for THIS project. Not what the 
information says, but how to USE it here.

## BEHAVIORAL GUIDANCE

Project-specific behavior rules:
- Tone: [Requirements]
- Format: [Preferences]
- Include: [What to always incorporate]
- Avoid: [What to never do]

## CROSS-REFERENCES

Other lens documents/projects that interact with this one:
- [Project X] — [How they relate, when to hand off]

## GAP ASSESSMENT

| Area | Coverage | Research Needed |
|------|----------|-----------------|
| [Topic] | STRONG | — |
| [Topic] | PARTIAL | [What's missing] |
| [Topic] | WEAK | [Phase 2 priority] |
```

---

# SECTION 9: MAINTENANCE & VERSIONING

---
CHUNK_ID: MMB-9.1-001
TOPIC: maintenance
SUBTOPIC: why_maintenance_matters
INSIGHT_TYPE: concept
RELEVANCE: both
APPLICATION: maintenance
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: maintenance, updates, knowledge decay, staleness
---

## 9.1 Why Maintenance Matters

Knowledge degrades. What's accurate today may be wrong in six months:
- Market data shifts
- Platform features change
- Best practices evolve
- New tools emerge
- Old approaches become obsolete

A GPT/Project without maintenance becomes increasingly unreliable. Users lose trust. Wrong information causes problems. The initial investment loses value.

Maintenance isn't optional — it's the difference between a system that stays useful and one that becomes a liability.

Planning maintenance during the build phase is far easier than retrofitting it later. Every document created should already consider: "How will this be updated? Who will update it? How will we know when it needs updating?"

---
CHUNK_ID: MMB-9.2-001
TOPIC: maintenance
SUBTOPIC: update_classification
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: maintenance
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: update types, classification, STAT_UPDATE, INSIGHT_ADD, CORRECTION
---

## 9.2 Update Classification Framework

Not all updates are equal. Classifying updates by type ensures appropriate procedures:

| Type | Definition | Risk | Procedure |
|------|------------|------|-----------|
| STAT_UPDATE | New data for existing metric | Low | Update in place, change DATA_FRESHNESS |
| INSIGHT_ADD | New insight within existing topic | Low-Medium | Add chunk, update changelog |
| SECTION_ADD | New topic area | Medium | Add section, update TOC, update relevant lenses |
| CORRECTION | Factual error fix | Low | Correct immediately, note in changelog |
| SUPERSEDE | Old insight no longer valid | Medium-High | Mark old as superseded, add new, update changelog |
| MAJOR_REVISION | Significant restructure | High | Archive current, rebuild, full regression test |

**STAT_UPDATE Example:**
Market size figure changed from $4.5B to $5.2B. Update the number, update DATA_FRESHNESS to current date, add changelog entry.

**SUPERSEDE Example:**
Previously recommended approach is now considered harmful. Add new chunk with current recommendation, add SUPERSEDES field to old chunk pointing to new, update changelog with explanation.

**MAJOR_REVISION Triggers:**
- Fundamental methodology change
- Platform changes that affect architecture
- Multiple cascading corrections
- Structural reorganization needed

---
CHUNK_ID: MMB-9.3-001
TOPIC: maintenance
SUBTOPIC: freshness_thresholds
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: maintenance
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: freshness thresholds, staleness, time-sensitive content
---

## 9.3 Data Freshness Thresholds

Different content types age at different rates:

| Content Type | Flag At | Action |
|--------------|---------|--------|
| Market data, pricing, adoption statistics | 6 months | Note uncertainty, suggest verification |
| Industry trends, competitive landscape | 12 months | Acknowledge may have shifted |
| Platform features, tool capabilities | 6 months | Verify current state before relying |
| Frameworks, methodologies | 18-24 months | Review for continued relevance |
| Definitions, core concepts | Never | Evergreen — present with confidence |

**Flagging Language:**

When content exceeds freshness threshold:
- "This reflects data as of [date]. Current figures may differ."
- "Platform features change frequently — verify current capabilities."
- "This trend was identified in [date]; the landscape may have evolved."

**In System Prompts:**

Include instructions for handling stale content:
```
When referencing content with DATA_FRESHNESS older than 6 months for 
market data or platform features, note the date and suggest verification
if the query is time-sensitive.
```

---
CHUNK_ID: MMB-9.4-001
TOPIC: maintenance
SUBTOPIC: changelog_management
INSIGHT_TYPE: procedure
RELEVANCE: both
APPLICATION: maintenance
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: changelog, version tracking, update history
---

## 9.4 Changelog Management

Every document that may be updated needs a changelog — either embedded or linked.

**Changelog Entry Format:**

```
| Date | Chunk ID | Type | Description | Linked Changes |
|------|----------|------|-------------|----------------|
| 2025-01-20 | MMB-3.2-007 | STAT_UPDATE | Updated market size | — |
| 2025-01-18 | MMB-5.1-002 | SUPERSEDE | Replaced old approach | See MMB-5.1-003 |
| 2025-01-15 | — | SECTION_ADD | Added Section 12 | Updated TOC |
```

**Fields:**
- **Date:** When the update was made
- **Chunk ID:** Which chunk was affected (or "—" for structural changes)
- **Type:** Classification from update framework
- **Description:** What changed (brief but specific)
- **Linked Changes:** Other chunks/documents affected

**Changelog Location:**
- For single documents: Top of document, after title/metadata
- For multi-document systems: Central CHANGELOG.md plus document-specific notes
- For Claude Projects: CHANGELOG.md as separate KB file

**Review Cadence:**
- Monthly: Scan for needed updates
- Quarterly: Full review against freshness thresholds
- Annually: Consider structural improvements

---

# SECTION 10: TESTING & VALIDATION

---
CHUNK_ID: MMB-10.1-001
TOPIC: testing
SUBTOPIC: why_testing_matters
INSIGHT_TYPE: concept
RELEVANCE: both
APPLICATION: implementation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: testing, validation, quality assurance, retrieval testing
---

## 10.1 Why Testing Matters

Building a GPT/Project without testing is like shipping software without QA. It might work. It might fail in ways you don't discover until users complain.

Testing validates:
- **Retrieval accuracy:** Does the right information surface for the right queries?
- **Behavioral compliance:** Does the system follow its protocols?
- **Edge case handling:** What happens with ambiguous or difficult inputs?
- **Regression prevention:** Did updates break existing functionality?

Testing catches problems before users do. A small investment in testing prevents significant trust damage from system failures.

---
CHUNK_ID: MMB-10.2-001
TOPIC: testing
SUBTOPIC: test_categories
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: implementation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: test categories, retrieval tests, behavioral tests, edge cases
---

## 10.2 Test Categories

**Retrieval Tests**
Verify that queries surface the correct chunks:

```
TEST: Retrieval-001
QUERY: "How should I structure my system prompt?"
EXPECTED: Chunks from Section 4 (System Prompt Architecture)
PASS: Section 4 content appears in response
FAIL: Response lacks system prompt guidance or pulls wrong sections
```

**Behavioral Tests**
Verify that protocols are followed:

```
TEST: Behavioral-001
QUERY: [Complex multi-part request]
EXPECTED: Spec confirmation before generating
PASS: System confirms understanding, awaits approval
FAIL: System generates without confirmation
```

```
TEST: Behavioral-002
QUERY: "What's the current market size?"
EXPECTED: If data >6 months old, note uncertainty
PASS: Response includes freshness caveat
FAIL: Presents stale data without qualification
```

**Edge Case Tests**
Verify graceful handling of difficult inputs:

```
TEST: Edge-001
QUERY: [Request for something outside scope]
EXPECTED: Acknowledge limitation, suggest alternative
PASS: Polite decline with helpful redirect
FAIL: Attempt to answer anyway or unhelpful refusal
```

```
TEST: Edge-002
QUERY: [Ambiguous request with multiple interpretations]
EXPECTED: Clarifying question before proceeding
PASS: Asks specific question to resolve ambiguity
FAIL: Assumes one interpretation without checking
```

**Regression Tests**
After any update, re-run critical tests to ensure nothing broke.

---
CHUNK_ID: MMB-10.3-001
TOPIC: testing
SUBTOPIC: test_documentation
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: implementation
CONFIDENCE: recommended
DATA_FRESHNESS: evergreen
KEYWORDS: test documentation, test format, test suite
---

## 10.3 Test Documentation Format

Maintain a test suite document with all tests:

```markdown
# TEST SUITE: [Project Name]

## Retrieval Tests

| ID | Query | Expected Result | Pass Criteria |
|----|-------|-----------------|---------------|
| R-001 | [Query] | [Expected] | [Criteria] |
| R-002 | [Query] | [Expected] | [Criteria] |

## Behavioral Tests

| ID | Scenario | Expected Behavior | Pass Criteria |
|----|----------|-------------------|---------------|
| B-001 | [Scenario] | [Expected] | [Criteria] |
| B-002 | [Scenario] | [Expected] | [Criteria] |

## Edge Case Tests

| ID | Input | Expected Handling | Pass Criteria |
|----|-------|-------------------|---------------|
| E-001 | [Input] | [Expected] | [Criteria] |
| E-002 | [Input] | [Expected] | [Criteria] |

## Test Run History

| Date | Version | Tests Run | Passed | Failed | Notes |
|------|---------|-----------|--------|--------|-------|
| 2025-01-20 | 1.0 | 24 | 24 | 0 | Initial release |
```

**Minimum Test Coverage:**
- 5-10 retrieval tests covering major topic areas
- 3-5 behavioral tests for key protocols
- 3-5 edge case tests for likely difficult inputs
- Regression run after every significant update

---

# SECTION 11: FILE ORGANIZATION

---
CHUNK_ID: MMB-11.1-001
TOPIC: file_organization
SUBTOPIC: single_project_structure
INSIGHT_TYPE: framework
RELEVANCE: single_project
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: single project, file structure, organization, folder structure
---

## 11.1 Single-Project File Structure

For single GPT/Project builds, keep organization simple:

```
PROJECT_NAME/
├── SYSTEM_PROMPT.md (or paste directly into Instructions)
├── [PRIMARY_KB].md (main knowledge document)
├── [SECONDARY_KB].md (if needed)
├── MAINTENANCE_SOP.md
├── CHANGELOG.md
└── TEST_SUITE.md (optional, for your reference)
```

**What Gets Uploaded:**
- Knowledge documents → Knowledge/Files section
- System prompt → Instructions field (pasted, not uploaded)
- Maintenance SOP → Knowledge (retrieval-isolated via triggers)
- Changelog → Knowledge (for reference)
- Test Suite → Usually kept locally, not uploaded

**Naming:**
Use descriptive names that indicate content:
- `Customer_Support_Knowledge.md`
- `Product_FAQ_Reference.md`
- `Response_Templates.md`

---
CHUNK_ID: MMB-11.2-001
TOPIC: file_organization
SUBTOPIC: multi_project_structure
INSIGHT_TYPE: framework
RELEVANCE: multi_project
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: multi-project, Universal, Shared, Project-Specific, folder structure
---

## 11.2 Multi-Project File Structure

For systems with multiple related projects sharing knowledge:

```
DOMAIN_FOUNDATION/
│
├── Universal/
│   ├── MASTER_[DOMAIN]_BRIEF.md
│   ├── BASE_SYSTEM_PROMPT.md
│   ├── MAINTENANCE_SOP.md
│   └── [SHARED_METHODOLOGY].md (if applicable)
│
├── Shared_Content/
│   ├── [STYLE_GUIDE].md (if applicable)
│   ├── [TEMPLATES].md (if applicable)
│   └── [OTHER_SHARED].md
│
├── Lens_Documents/
│   ├── LENS_01_[Project].md
│   ├── LENS_02_[Project].md
│   └── ...
│
├── Project_Prompts/
│   ├── PROJECT_PROMPT_01_[Project].md
│   ├── PROJECT_PROMPT_02_[Project].md
│   └── ...
│
├── Reference_Only/ (NOT uploaded to projects)
│   ├── FILE_MAP.md
│   ├── TEST_SUITE.md
│   └── TEMPLATES/
│
└── Archives/
    └── [Quarterly snapshots]
```

**Category Definitions:**

| Category | Contents | Upload To |
|----------|----------|-----------|
| Universal | Documents ALL projects need | Every project |
| Shared_Content | Documents SOME projects need | Applicable projects only |
| Lens_Documents | Project-specific views | One per project |
| Project_Prompts | Project-specific instructions | One per project (Instructions field) |
| Reference_Only | Your management tools | None — local reference |
| Archives | Historical versions | None — backup only |

---
CHUNK_ID: MMB-11.3-001
TOPIC: file_organization
SUBTOPIC: sync_management
INSIGHT_TYPE: procedure
RELEVANCE: multi_project
APPLICATION: maintenance
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: sync, update propagation, multi-project sync, version consistency
---

## 11.3 Sync Management (Multi-Project)

When universal or shared documents update, changes must propagate to all affected projects.

**Sync Matrix:**

Create a matrix showing which documents go to which projects:

| Document | Proj 1 | Proj 2 | Proj 3 | Proj 4 |
|----------|--------|--------|--------|--------|
| Master Brief | ✓ | ✓ | ✓ | ✓ |
| Base Prompt | ✓ | ✓ | ✓ | ✓ |
| Style Guide | ✓ | ✓ | — | ✓ |
| Templates | — | ✓ | ✓ | — |

✓ = Include | — = Exclude

**Sync Procedure:**

1. Update source document in Universal/ or Shared_Content/
2. Update changelog with change description
3. Re-upload to all affected projects (per sync matrix)
4. Update each project's changelog with sync note
5. Run regression tests on affected projects

**Sync Timing:**

| Update Type | Sync Timing |
|-------------|-------------|
| CORRECTION | Immediate |
| STAT_UPDATE | Within 48 hours |
| INSIGHT_ADD | Within 48 hours |
| SECTION_ADD | Within 24 hours |
| SUPERSEDE | Within 24 hours |
| MAJOR_REVISION | Immediate + full regression |

---

# SECTION 12: IMPLEMENTATION GUIDANCE

---
CHUNK_ID: MMB-12.1-001
TOPIC: implementation
SUBTOPIC: claude_projects
INSIGHT_TYPE: procedure
RELEVANCE: both
APPLICATION: implementation
CONFIDENCE: established
DATA_FRESHNESS: 2025-01
KEYWORDS: Claude Projects, implementation, setup, Anthropic
---

## 12.1 Claude Projects Implementation

Step-by-step setup for Claude Projects (Anthropic):

**Step 1: Create Project**
- Go to claude.ai → Projects → New Project
- Name it descriptively (users will see this name)
- Add description (brief summary of purpose)

**Step 2: Configure Instructions**
- Click "Set instructions" or find the Instructions field
- Paste BASE_SYSTEM_PROMPT.md content FIRST
- Then paste PROJECT_PROMPT.md content SECOND
- Order matters — base behaviors before project specifics

**Step 3: Upload Knowledge**
- Click "Add content" or Knowledge section
- Upload all KB files for this project:
  - Master/methodology documents
  - Lens document (if multi-project)
  - Maintenance SOP
  - Changelog
  - Any project-specific knowledge files
- Supported formats: .md, .txt, .pdf, .docx

**Step 4: Configure Settings**
- Review any additional project settings
- Enable/disable features as appropriate

**Step 5: Test**
- Run retrieval tests: Ask questions that should surface specific content
- Run behavioral tests: Trigger protocols (maintenance mode, spec confirmation)
- Run edge cases: Test graceful handling of difficult inputs

**Troubleshooting:**
- If retrieval seems off, check document structure and chunking
- If behaviors aren't followed, check prompt order and clarity
- If responses are inconsistent, simplify and clarify instructions

---
CHUNK_ID: MMB-12.2-001
TOPIC: implementation
SUBTOPIC: custom_gpts
INSIGHT_TYPE: procedure
RELEVANCE: both
APPLICATION: implementation
CONFIDENCE: established
DATA_FRESHNESS: 2025-01
KEYWORDS: Custom GPT, OpenAI, implementation, setup, GPT Builder
---

## 12.2 Custom GPT Implementation

Custom GPTs have an 8,000 character limit on Instructions. For sophisticated systems, use hybrid architecture:

**Hybrid Architecture (Recommended for All Custom GPTs):**

**Step 1: Create GPT**
- Go to chat.openai.com → Explore GPTs → Create
- Or: ChatGPT → My GPTs → Create a GPT

**Step 2: Configure Basic Info**
- Name: Clear, descriptive name
- Description: What it does (users see this)
- Note: Hybrid architecture maintains full sophistication

**Step 3: Core Instructions (~7.5K characters)**
Paste condensed core prompt containing:
- Essential identity and mission
- Discovery flow (cannot be retrieved mid-conversation)
- KB retrieval protocols: "For complex procedures, retrieve from [KB documents]"
- Basic behavioral standards

**Step 4: Upload Knowledge Base (Critical)**
Upload these files in order:
- BEHAVIORAL_PROTOCOLS.md (advanced behaviors)
- GENERATION_PROCEDURES.md (content workflows)
- TEMPLATE_LIBRARY.md (templates & examples)
- PLATFORM_GUIDES.md (implementation guidance)
- [DOMAIN]_KNOWLEDGE_BASE.md (domain expertise)

**Step 5: Configure Capabilities**
- Web Browsing: Enable if real-time info needed
- DALL-E: Usually OFF unless image generation needed
- Code Interpreter: Enable if file processing needed

**Step 6: Set Conversation Starters**
- Add 4 example prompts showcasing hybrid capabilities
- Include one showing KB retrieval functionality

**Step 7: Test Hybrid Architecture**
- Test core behavioral responses
- Test KB document retrieval ("Help me with maintenance mode")
- Test complex procedure handling
- Verify character count under 8,000

**Benefits of Hybrid Approach:**
- Maintains full sophisticated functionality
- Works within platform constraints
- Demonstrates advanced platform optimization
- Provides educational value about architecture design

---
CHUNK_ID: MMB-12.3-001
TOPIC: implementation
SUBTOPIC: platform_differences
INSIGHT_TYPE: framework
RELEVANCE: both
APPLICATION: implementation
CONFIDENCE: established
DATA_FRESHNESS: 2025-01
KEYWORDS: platform differences, Claude vs GPT, comparison
---

## 12.3 Platform Differences

Key differences to consider when choosing or building for each platform:

| Aspect | Claude Projects | Custom GPTs (Hybrid) |
|--------|-----------------|---------------------|
| Instructions | Two-part (base + project separate) | Core prompt (~7.5K) + KB documents |
| Character Limit | No practical limit | 8,000 chars (solved with hybrid architecture) |
| Sophistication | Full complexity in Instructions | Full complexity via Instructions + KB |
| Retrieval | Generally more consistent | Hybrid retrieval (Instructions + KB) |
| Memory | Project memory across conversations | Conversation memory only |
| File Support | .md, .txt, .pdf, .docx | Broader format support |
| Capabilities | Text-focused | Web, DALL-E, Code Interpreter |
| Sharing | Link sharing | GPT Store + link sharing |
| Updates | Re-upload files | Re-upload files |
| Architecture | Single comprehensive prompt | Hybrid (core + retrieval protocols) |

**Claude Projects Strengths:**
- Full sophistication in single prompt
- More consistent retrieval
- Project memory aids continuity
- No character limit constraints

**Custom GPT Strengths:**
- Additional capabilities (web, images, code)
- Broader distribution (GPT Store)
- More file format support
- Hybrid architecture demonstrates platform optimization

**Both Platforms Now Support:**
- Full sophisticated functionality
- Advanced behavioral protocols
- Complex maintenance procedures
- Professional-grade knowledge systems

**Building for Both:**
If you need to support both platforms:
- Use Claude Projects for maximum prompt sophistication
- Use Custom GPT hybrid for public sharing + full functionality
- Both deliver equivalent user experience
- Choose based on sharing needs and platform preference

---

# APPENDIX A: TEMPLATES

---
CHUNK_ID: MMB-A.1-001
TOPIC: templates
SUBTOPIC: base_system_prompt_template
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: base system prompt template, template
---

## A.1 Base System Prompt Template

```markdown
# BASE SYSTEM PROMPT

## CORE IDENTITY

You are [Role Name], an expert [domain] assistant. Your purpose is to [primary mission].

Your approach:
- [Key principle 1]
- [Key principle 2]
- [Key principle 3]

## RETRIEVAL CONFIGURATION

**Standard Mode (default):**
- Retrieve from knowledge base based on query relevance
- Prioritize [primary document] for [query types]
- Prioritize [secondary document] for [query types]

**Maintenance Mode:**

*LAYER 1 — Clear Triggers (enter maintenance immediately):*
- "update the knowledge base"
- "update the [project name]"
- "add to the knowledge base"
- "maintenance mode"
- "the KB needs updating"

*LAYER 2 — User Content Signals (NEVER trigger maintenance):*
- "revise this [document/draft/section]"
- "fix this [content/writing]"
- "update this [document/draft]"
- Any revision request containing "this" or "my" — treat as user content work

*LAYER 3 — Ambiguous (ask for clarification FIRST):*
- "revise the project"
- "update the system"
- "fix an error"
- "something is wrong"
- Any revision language without clear referent

*When ambiguous, ask:*
"Quick clarification — are you wanting to update this project's knowledge base, or are you working on your own document/content?"

*When maintenance confirmed:*
- Include MAINTENANCE_SOP in retrieval
- Follow update classification procedures

**Exclusions:**
Do not retrieve MAINTENANCE_SOP unless maintenance mode triggered.

## DATA FRESHNESS PROTOCOL

When referencing content:
- If DATA_FRESHNESS > 6 months for market/platform data: Note uncertainty
- If DATA_FRESHNESS > 12 months for trends: Acknowledge may have evolved
- If "evergreen": Present with confidence

Flagging language: "This reflects [topic] as of [date]. Current state may differ."

## CONFIDENCE WEIGHTING

| Level | Presentation |
|-------|--------------|
| Established | State directly |
| Recommended | "The recommended approach..." |
| Experimental | "An experimental technique..." |

## SPEC CONFIRMATION PROTOCOL

**Confirm before generating when:**
- Request is complex or multi-part
- Requirements are ambiguous
- Output requires significant effort

**Confirmation format:**
"Before I proceed, let me confirm: [key dimensions]. Is this correct?"

**Proceed without confirmation when:**
- Simple, clear questions
- User has provided detailed specifications
- Follow-up to confirmed work

## ERROR HANDLING

- **Missing information:** Ask specific clarifying question
- **Conflicting information:** Surface conflict, ask user to resolve
- **Outside scope:** Acknowledge limitation, suggest alternatives
- **Uncertain:** Express uncertainty appropriately, offer to clarify

## MAINTENANCE MODE

When maintenance triggered:
1. Acknowledge maintenance request
2. Classify update type (STAT_UPDATE, INSIGHT_ADD, CORRECTION, etc.)
3. Follow procedures from MAINTENANCE_SOP
4. Confirm changes before implementing
```

---
CHUNK_ID: MMB-A.2-001
TOPIC: templates
SUBTOPIC: project_prompt_template
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: project prompt template, template
---

## A.2 Project System Prompt Template

```markdown
# PROJECT PROMPT: [Project Name]

## PROJECT MISSION

This project [primary function]. 

**Use this project for:**
- [Use case 1]
- [Use case 2]
- [Use case 3]

**Do NOT use this project for:**
- [Out of scope 1] → Use [alternative] instead
- [Out of scope 2] → Use [alternative] instead

## KB INTEGRATION

| Document | Priority | Use For |
|----------|----------|---------|
| [Document 1] | PRIMARY | [Query types] |
| [Document 2] | SUPPORTING | [Query types] |
| [Document 3] | REFERENCE | [Query types] |

## BEHAVIORAL GUIDANCE

**Tone:** [Tone requirements]

**Always:**
- [Required behavior 1]
- [Required behavior 2]

**Never:**
- [Prohibited behavior 1]
- [Prohibited behavior 2]

## OUTPUT STANDARDS

**Default format:** [Format description]

**Length:** [Length guidance]

**Structure:** [Structure requirements]

**Quality checklist:**
- [ ] [Quality criterion 1]
- [ ] [Quality criterion 2]
- [ ] [Quality criterion 3]

## [MULTI-PROJECT ONLY] CROSS-PROJECT COORDINATION

**Related projects:**
- [Project X]: [Relationship, when to hand off]
- [Project Y]: [Relationship, when to hand off]

**Handoff format:**
When directing to another project: "[Explanation of why other project is better fit]"
```

---
CHUNK_ID: MMB-A.3-001
TOPIC: templates
SUBTOPIC: lens_document_template
INSIGHT_TYPE: template
RELEVANCE: multi_project
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: lens document template, template
---

## A.3 Lens Document Template

```markdown
# LENS: [Project Name]

**Document Type:** Lens Document  
**Version:** 1.0  
**Last Updated:** [Date]  
**Master Document:** [Name of master document this lenses into]

---

## PURPOSE

[Clear statement of what this project accomplishes]

---

## AGENT TYPE CLASSIFICATION

**Primary Type:** [Type from taxonomy]
**Secondary Type:** [Type from taxonomy]

**Behavioral Implications:**
- [Implication 1 based on agent types]
- [Implication 2]
- [Implication 3]

---

## PRIMARY INTELLIGENCE SECTIONS

| Section | Weight | Use For |
|---------|--------|---------|
| Section [X] | HIGH | [Query types this section answers] |
| Section [Y] | HIGH | [Query types] |
| Section [Z] | MEDIUM | [Query types] |
| Section [W] | LOW | [Query types] |

---

## KEY EXTRACTS

Critical chunks this project retrieves most often:

- **[CHUNK_ID]:** [Brief description of why critical]
- **[CHUNK_ID]:** [Brief description]
- **[CHUNK_ID]:** [Brief description]

---

## PROJECT-SPECIFIC CONTEXT

[How to APPLY the master document intelligence for this project's specific purpose. Not what the information says, but how to use it here.]

---

## BEHAVIORAL GUIDANCE

**Tone:** [Requirements]

**Format Preferences:** [Preferences]

**Always Include:** [Required elements]

**Always Avoid:** [Prohibited elements]

---

## CROSS-REFERENCES

| Related Project | Relationship | Handoff Trigger |
|-----------------|--------------|-----------------|
| [Project name] | [How related] | [When to direct there] |

---

## GAP ASSESSMENT

| Topic Area | Coverage | Research Needed |
|------------|----------|-----------------|
| [Area 1] | STRONG | — |
| [Area 2] | PARTIAL | [What's missing] |
| [Area 3] | WEAK | [Priority for Phase 2] |
```

---
CHUNK_ID: MMB-A.4-001
TOPIC: templates
SUBTOPIC: maintenance_sop_template
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: maintenance SOP template, template
---

## A.4 Maintenance SOP Template

```markdown
# MAINTENANCE SOP

**Document Type:** Standard Operating Procedure  
**Version:** 1.0  
**Last Updated:** [Date]

---

## RETRIEVAL ISOLATION

This document is EXCLUDED from normal retrieval. Only surface when maintenance mode is triggered.

**LAYER 1 — Clear Triggers (enter maintenance immediately):**
- "update the knowledge base"
- "update the [project name]"
- "add to the knowledge base"
- "maintenance mode"
- "the KB needs updating"

**LAYER 2 — User Content Signals (NEVER trigger maintenance):**
- "revise this [document/draft/section]"
- "fix this [content/writing]"
- "update this [document/draft]"
- Any revision request containing "this" or "my" — treat as user content work

**LAYER 3 — Ambiguous (ask for clarification FIRST):**
- "revise the project"
- "update the system"
- "fix an error"
- "something is wrong"
- Any revision language without clear referent

**When ambiguous, ask:**
"Quick clarification — are you wanting to update this project's knowledge base, or are you working on your own document/content?"

---

## UPDATE CLASSIFICATION

| Type | Definition | Risk | Procedure |
|------|------------|------|-----------|
| STAT_UPDATE | New data for existing metric | Low | Update in place |
| INSIGHT_ADD | New insight in existing topic | Low-Med | Add chunk |
| SECTION_ADD | New topic area | Medium | Add section |
| CORRECTION | Error fix | Low | Correct immediately |
| SUPERSEDE | Old insight invalid | Med-High | Mark + replace |
| MAJOR_REVISION | Significant restructure | High | Archive + rebuild |

---

## PROCEDURES BY TYPE

### STAT_UPDATE
1. Locate the chunk containing the statistic
2. Update the value
3. Update DATA_FRESHNESS to current date
4. Add changelog entry
5. [Multi-project] Sync to affected projects

### INSIGHT_ADD
1. Determine appropriate section
2. Create new chunk with full metadata
3. Add boundary overlap if needed
4. Update changelog
5. [Multi-project] Update relevant lens documents

### SECTION_ADD
1. Determine where new section fits
2. Create section with proper chunking
3. Add metadata to all new chunks
4. Update Table of Contents
5. Add changelog entry
6. [Multi-project] Update lens documents if section is relevant

### CORRECTION
1. Identify incorrect content
2. Make correction
3. Add changelog entry noting what was wrong
4. [Multi-project] Sync immediately

### SUPERSEDE
1. Locate outdated chunk
2. Add SUPERSEDED_BY field pointing to new chunk
3. Create new chunk with current information
4. Update changelog with explanation
5. [Multi-project] Sync with priority

### MAJOR_REVISION
1. Archive current version
2. Plan revision scope
3. Implement changes
4. Run full test suite
5. Update all changelogs
6. [Multi-project] Full sync + regression

---

## PHASED KB EXPANSION

Many projects start with core knowledge and expand over time. This is not just valid — it's often the best approach. Trying to build everything upfront leads to analysis paralysis, content that's never used, and wasted effort.

### The Minimum Viable Knowledge Base (MVKB)

Launch with just enough to be useful:

**MVKB Checklist:**
- [ ] Core purpose content (what it MUST know)
- [ ] Top 10 most common questions/tasks
- [ ] Key constraints and guardrails
- [ ] Basic error handling guidance

**Explicitly Defer:**
- Edge cases (document when they arise)
- Rarely-used information (add when needed)
- Nice-to-have sections (track for later)

### The Four-Phase Expansion Framework

**Phase 1: Launch (Week 1)**
Goal: Get something working

- Core functionality only
- 3-5 main sections
- Test with real queries
- Note gaps as you find them

Size: 10-20 chunks (5,000-15,000 tokens)

**Phase 2: Fill Gaps (Weeks 2-4)**
Goal: Address what's missing

- Review queries that failed or struggled
- Add content for frequent questions
- Expand thin sections
- Add first round of edge cases

Trigger: "I keep having to answer this manually"

Size: 20-35 chunks

**Phase 3: Deepen (Month 2-3)**
Goal: Improve quality

- Add nuance to existing sections
- Include more examples
- Document exceptions and special cases
- Add cross-references between sections

Trigger: "It answers, but not as well as I would"

Size: 35-50 chunks

**Phase 4: Expand (Month 3+)**
Goal: Broaden coverage

- Add new topic areas
- Include advanced content
- Document rare scenarios
- Consider splitting into multiple projects if scope grows

Trigger: "Users are asking about things outside current scope"

Size: 50+ chunks

### Identifying Gaps from Usage

Track these signals from actual use:

| Signal | Meaning | Action |
|--------|---------|--------|
| "I don't have information about..." | Content gap | Add content |
| Retrieves wrong section | Chunking/metadata issue | Restructure |
| Partially correct answers | Thin content | Deepen section |
| Users rephrase repeatedly | Retrieval not matching queries | Add keywords to metadata |
| Users give up | Major gap or usability issue | Investigate and fix |

### Gap Tracking

Keep a simple log:

```
| Date | Query/Situation | Gap Type | Priority | Status |
|------|-----------------|----------|----------|--------|
| [Date] | [What happened] | [Type] | [P1/P2/P3] | [Status] |
```

### Monthly Gap Review Process

1. Review gap log
2. Identify patterns (same gap multiple times = high priority)
3. Batch similar additions together
4. Update KB following maintenance procedures
5. Test and document changes

### Expansion vs. Depth Decision

| Add New Section When | Deepen Existing When |
|----------------------|----------------------|
| Completely new topic | Related to current content |
| Different audience segment | Same audience, more detail |
| New use case | Same use case, more nuance |
| Would clutter existing sections | Fits naturally in current structure |

### When NOT to Expand

- **One-time question** — Answer manually, don't clutter KB
- **Out of scope** — Redirect users, don't scope creep
- **Changes constantly** — Keep in separate, easily-updated section
- **Highly personalized** — Some things need human judgment

**When expanding the KB:**

1. **Review existing structure** — Identify where new content fits
2. **Maintain consistency** — Match formatting, chunking, metadata patterns
3. **Use INSIGHT_ADD** — For new content within existing topics
4. **Use SECTION_ADD** — For entirely new topic areas
5. **Update cross-references** — Ensure new content connects to existing
6. **Document in changelog** — Track what was added and why

**FUTURE EXPANSION areas (if identified during build):**
[List any areas flagged for future research or content development]

---

## CHANGELOG FORMAT

| Date | Chunk ID | Type | Description | Linked |
|------|----------|------|-------------|--------|
| [Date] | [ID] | [Type] | [Description] | [Links] |

---

## FRESHNESS THRESHOLDS

| Content Type | Review At |
|--------------|-----------|
| Market data | 6 months |
| Platform features | 6 months |
| Industry trends | 12 months |
| Methodologies | 18 months |
| Core concepts | Evergreen |

---

## REVIEW SCHEDULE

- **Monthly:** Scan for needed updates
- **Quarterly:** Full freshness review
- **Annually:** Structural review
```

---
CHUNK_ID: MMB-A.5-001
TOPIC: templates
SUBTOPIC: metadata_template
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: metadata template, chunk metadata template
---

## A.5 Metadata Block Template

```
---
CHUNK_ID: [DOC]-[Section].[Subsection]-[Number]
TOPIC: [primary_category]
SUBTOPIC: [specific_focus]
INSIGHT_TYPE: [concept | framework | procedure | example | template | warning]
RELEVANCE: [single_project | multi_project | both | specific_project_names]
APPLICATION: [discovery | architecture | generation | implementation | maintenance]
CONFIDENCE: [established | recommended | experimental]
DATA_FRESHNESS: [YYYY-MM | evergreen]
KEYWORDS: [comma, separated, retrieval, terms]
---
```

---
CHUNK_ID: MMB-A.6-001
TOPIC: templates
SUBTOPIC: mib_template
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: MIB template, master intelligence brief, knowledge base template
---

## A.6 Master Intelligence Brief (MIB) Template

The MIB is the comprehensive knowledge document for a project or system. Adapt this structure to the user's domain.

```markdown
# MASTER [DOMAIN] BRIEF
## [Subtitle describing scope]

**Document Type:** Master Intelligence Brief  
**Version:** 1.0  
**Last Updated:** [Date]  
**Status:** Active

---

## CHANGELOG

| Version | Date | Type | Description |
|---------|------|------|-------------|
| 1.0 | [Date] | INITIAL | Initial release |

---

## TABLE OF CONTENTS

1. [Foundation/Overview Section]
2. [Core Domain Knowledge Section]
3. [Frameworks & Methodologies Section]
4. [Market/Industry Context Section] (if applicable)
5. [Practical Applications Section]
6. [Common Challenges & Solutions]
7. [Best Practices]
8. [Tools & Resources] (if applicable)
9. [Action Frameworks]
10. [Future Considerations]

Appendix A: Key Data & Statistics
Appendix B: Templates & Examples
Appendix C: Glossary

---

# SECTION 1: [FOUNDATION/OVERVIEW]

---
CHUNK_ID: [DOC]-1.1-001
TOPIC: [section_topic]
SUBTOPIC: [specific_focus]
INSIGHT_TYPE: concept
RELEVANCE: [who needs this]
APPLICATION: [what phase]
CONFIDENCE: established
DATA_FRESHNESS: [date or evergreen]
KEYWORDS: [terms]
---

## 1.1 [Subsection Title]

[Content: 600-1000 tokens]

[Key concept explanation]

[Why it matters]

[How it connects to rest of document]

---
CHUNK_ID: [DOC]-1.2-001
TOPIC: [section_topic]
SUBTOPIC: [specific_focus]
INSIGHT_TYPE: [type]
RELEVANCE: [who needs this]
APPLICATION: [what phase]
CONFIDENCE: [level]
DATA_FRESHNESS: [date or evergreen]
KEYWORDS: [terms]
---

## 1.2 [Subsection Title]

[Content: 600-1000 tokens]

[Continue pattern for each subsection]

---

# SECTION 2: [CORE DOMAIN KNOWLEDGE]

[Continue section pattern...]

---

# APPENDIX A: KEY DATA & STATISTICS

[Consolidate quantitative claims here for easy reference and updating]

| Metric | Value | Source | Date |
|--------|-------|--------|------|
| [Metric 1] | [Value] | [Source] | [Date] |

---

# APPENDIX B: TEMPLATES & EXAMPLES

[Domain-specific templates and examples]

---

# APPENDIX C: GLOSSARY

| Term | Definition |
|------|------------|
| [Term] | [Definition] |

---

**END OF MASTER [DOMAIN] BRIEF**
```

### MIB Construction Guidelines

**Section Planning:**
- 8-12 main sections typical
- Each section: 3-6 subsections
- Each subsection: 1 chunk (600-1000 tokens)
- Total: 40-70 chunks typical

**Chunking Rules:**
- One concept per chunk
- Statistics stay with interpretation
- Use boundary overlap at conceptual transitions
- Self-contained but connected

**Metadata Application:**
- Every chunk gets full 9-field metadata
- TOPIC matches section theme
- SUBTOPIC is specific focus
- KEYWORDS aid retrieval

**Appendix Strategy:**
- Appendix A: All statistics consolidated (easy updates)
- Appendix B: Reusable templates
- Appendix C: Definitions (aids consistency)

---
CHUNK_ID: MMB-A.7-001
TOPIC: templates
SUBTOPIC: file_map_template
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: file map template, architecture reference, document inventory
---

## A.7 File Map Template

**Deployment:** Keep locally — do NOT upload to project Knowledge.
This file is your reference for setup, versions, and maintenance. The GPT/Project does not need access to it.

```markdown
# [PROJECT NAME] FILE MAP
## Architecture Reference

**Document Type:** Architecture Reference  
**Version:** 1.0  
**Last Updated:** [Date]  
**Status:** Active  
**Location:** Keep locally — do not upload to Knowledge

---

## DOCUMENT INVENTORY

### Files in This Project

| File | Type | Purpose | Deploy To |
|------|------|---------|-----------|
| [SYSTEM_PROMPT].md | Instructions | Behavioral layer | Instructions field |
| [PRIMARY_KB].md | KB Document | Core knowledge | Knowledge |
| MAINTENANCE_SOP.md | KB Document | Update procedures | Knowledge |
| CHANGELOG.md | KB Document | Version history | Knowledge |
| FILE_MAP.md | Reference | This file | Keep locally |
| TEST_SUITE.md | Reference | Validation tests | Keep locally |

---

## PLATFORM SETUP

### Claude Project

**Instructions Field:**
Paste in this order:
1. [First prompt content]
2. [Second prompt content if applicable]

**Knowledge Uploads:**
1. [File 1]
2. [File 2]
3. [etc.]

**Project Description:**
"[Brief description for project identification]"

### Custom GPT (if applicable)

**Instructions Field:**
[Combined prompt guidance]

**Knowledge Uploads:**
[Same as Claude Project]

**Conversation Starters:**
- "[Starter 1]"
- "[Starter 2]"

---

## FOLDER STRUCTURE

### Local Storage

```
[PROJECT_NAME]/
├── Active/
│   ├── [File 1]
│   ├── [File 2]
│   └── [etc.]
├── Reference/
│   └── [Reference docs not uploaded]
└── Archives/
    └── [Dated backups]
```

---

## DOCUMENT RELATIONSHIPS

### Retrieval Flow

```
User Query
    │
    ▼
SYSTEM_PROMPT (behavioral rules)
    │
    ▼
[PRIMARY_KB] (main knowledge)
    │
    ▼ (only if triggered)
MAINTENANCE_SOP (update procedures)
```

---

## VERSION TRACKING

| Document | Version | Last Updated |
|----------|---------|--------------|
| [File 1] | 1.0 | [Date] |
| [File 2] | 1.0 | [Date] |

---

## MAINTENANCE TRIGGERS

**Phrases that activate maintenance mode:**
- "update the knowledge base"
- "maintenance mode"
- [Project-specific triggers]

**Phrases that do NOT trigger maintenance:**
- "revise this [document]"
- "fix this [content]"
- Anything with "this" or "my" referring to user's own work

---

## QUICK SETUP CHECKLIST

- [ ] Create project/GPT
- [ ] Set name and description
- [ ] Paste instructions
- [ ] Upload knowledge files
- [ ] Test with sample queries
- [ ] Verify retrieval accuracy

---

**END OF FILE MAP**
```

---
CHUNK_ID: MMB-A.8-001
TOPIC: templates
SUBTOPIC: changelog_template
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: changelog template, version history, update tracking
---

## A.8 Changelog Template

```markdown
# CHANGELOG
## [Project Name] — Version History

**Document Type:** Changelog  
**Last Updated:** [Date]

---

## Version Summary

| Version | Date | Type | Summary |
|---------|------|------|---------|
| 1.0 | [Date] | INITIAL | Initial release |

---

## Detailed Changes

### v1.0 — [Date]

**Type:** INITIAL RELEASE

**Summary:** [Brief description of what was created]

**Documents Created:**

| Document | Description |
|----------|-------------|
| [Doc 1] | [Purpose] |
| [Doc 2] | [Purpose] |

---

## Change Entry Format

When logging updates, use this format:

### vX.X — [Date]

**Type:** [STAT_UPDATE | INSIGHT_ADD | SECTION_ADD | CORRECTION | SUPERSEDE | MAJOR_REVISION]

**Summary:** [Brief description]

**Changes:**

| Chunk ID | Change | Reason |
|----------|--------|--------|
| [ID] | [What changed] | [Why] |

**Affected Documents:**
- [List documents updated]

**Migration Notes:** (if applicable)
- [Steps users need to take]

---

## Update Type Definitions

| Type | Definition | When to Use |
|------|------------|-------------|
| STAT_UPDATE | Number or statistic changed | Data refreshes |
| INSIGHT_ADD | New content in existing topic | Expanding knowledge |
| SECTION_ADD | Entirely new topic | New capability area |
| CORRECTION | Fixing an error | Something was wrong |
| SUPERSEDE | Old info no longer valid | Replacing outdated content |
| MAJOR_REVISION | Significant restructure | Architecture changes |

---

**END OF CHANGELOG**
```

---
CHUNK_ID: MMB-A.9-001
TOPIC: templates
SUBTOPIC: test_suite_template
INSIGHT_TYPE: template
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: test suite template, validation tests, quality assurance
---

## A.9 Test Suite Template

```markdown
# TEST SUITE
## [Project Name] — Validation Tests

**Document Type:** Test Suite  
**Version:** 1.0  
**Last Updated:** [Date]  
**Status:** Active

---

## PURPOSE

This test suite validates that [Project Name]:
1. Retrieves correct content for queries
2. Follows behavioral protocols
3. Handles edge cases gracefully

**Usage:** Run tests after deployment and after any updates.

---

## RETRIEVAL TESTS

Verify correct content surfaces for relevant queries.

### R-001: [Topic] Retrieval
**Query:** "[Question about main topic]"  
**Expected:** Content from [relevant section]  
**Pass Criteria:** Response includes [specific elements]

### R-002: [Topic] Retrieval
**Query:** "[Question about second topic]"  
**Expected:** Content from [relevant section]  
**Pass Criteria:** Response includes [specific elements]

### R-003: [Topic] Retrieval
**Query:** "[Question about third topic]"  
**Expected:** Content from [relevant section]  
**Pass Criteria:** Response includes [specific elements]

[Add 3-5 more retrieval tests covering main knowledge areas]

---

## BEHAVIORAL TESTS

Verify the project follows its protocols.

### B-001: [Key Behavior]
**Query:** "[Query that should trigger behavior]"  
**Expected:** [Expected behavior]  
**Pass Criteria:** [How to verify]

### B-002: Tone/Style Consistency
**Query:** "[Sample request]"  
**Expected:** Response matches specified tone  
**Pass Criteria:** [Tone indicators present]

### B-003: Boundary Respect
**Query:** "[Out of scope request]"  
**Expected:** Polite decline or redirect  
**Pass Criteria:** Doesn't attempt out-of-scope task

[Add 2-3 more behavioral tests specific to project]

---

## MAINTENANCE TRIGGER TESTS

### MT-001: Clear Trigger Works
**Query:** "Update the knowledge base"  
**Expected:** Enters maintenance mode  
**Pass Criteria:** Acknowledges maintenance mode

### MT-002: User Content Not Triggered
**Query:** "Help me revise this document"  
**Expected:** Treats as content help, NOT maintenance  
**Pass Criteria:** Offers content help without maintenance mode

### MT-003: Ambiguous Asks Clarification
**Query:** "I need to make a revision"  
**Expected:** Asks for clarification  
**Pass Criteria:** Asks whether KB update or content help

---

## EDGE CASE TESTS

### E-001: Missing Information
**Query:** "[Question KB can't fully answer]"  
**Expected:** Acknowledges limitation appropriately  
**Pass Criteria:** Honest about gaps without being unhelpful

### E-002: Ambiguous Request
**Query:** "[Vague or unclear request]"  
**Expected:** Asks clarifying question  
**Pass Criteria:** Seeks clarity before proceeding

---

## REGRESSION TESTS

Run after any update:

### REG-001: Core Retrieval
**Test:** R-001, R-002, R-003  
**Pass:** All pass

### REG-002: Key Behaviors
**Test:** B-001, B-002  
**Pass:** Both pass

### REG-003: Maintenance Triggers
**Test:** MT-001, MT-002  
**Pass:** Both pass

---

## TEST RUN HISTORY

| Date | Version | Tests Run | Passed | Failed | Notes |
|------|---------|-----------|--------|--------|-------|
| [Date] | 1.0 | — | — | — | Initial deployment |

---

**END OF TEST SUITE**
```

### Test Suite Generation Guidelines

**Minimum tests per project:**
- 5 Retrieval tests (cover main knowledge areas)
- 3 Behavioral tests (tone, boundaries, key behaviors)
- 3 Maintenance trigger tests (always include)
- 2 Edge case tests (missing info, ambiguity)
- 3 Regression tests (quick validation after updates)

**Customize based on:**
- Project's agent type (different behaviors to test)
- Knowledge base content (what should retrieve)
- Specific behavioral rules (what to verify)
- User context (what edge cases are likely)

---

# APPENDIX B: EXAMPLE BUILD — AI CONSULTANCY

---
CHUNK_ID: MMB-B.1-001
TOPIC: example
SUBTOPIC: ai_consultancy_overview
INSIGHT_TYPE: example
RELEVANCE: multi_project
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: example build, AI consultancy, multi-project example
---

## B.1 Example: AI Consultancy Multi-Project System

This example demonstrates a complete multi-project architecture for an AI consultancy serving service businesses.

**Business Context:**
An AI consultant helping founder-led service businesses implement operational automation and AI solutions. Target verticals include home services, professional services, and similar B2B service businesses.

**Why Multi-Project:**
The consultancy needs multiple specialized tools:
- Business strategy and planning
- Content creation and marketing
- Prospecting and outreach
- Training and workshops
- Internal education and research

All these share common knowledge (market intelligence, positioning, methodology) but apply it differently.

---
CHUNK_ID: MMB-B.2-001
TOPIC: example
SUBTOPIC: ai_consultancy_structure
INSIGHT_TYPE: example
RELEVANCE: multi_project
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: example structure, folder organization, AI consultancy
---

## B.2 File Structure

```
AI_CONSULTANCY_FOUNDATION/
│
├── Universal/
│   ├── MASTER_INTELLIGENCE_BRIEF.md (market data, positioning, methodology)
│   ├── BASE_SYSTEM_PROMPT.md
│   ├── MAINTENANCE_SOP.md
│   └── DELIVERY_METHODOLOGY.md (service tiers, pricing, process)
│
├── Shared_Content/
│   ├── BRAND_GUIDELINES.md (voice, tone, messaging)
│   ├── WRITING_VOICE.md (authentic writing patterns)
│   └── SEO_KEYWORDS.md (search strategy)
│
├── Lens_Documents/
│   ├── LENS_01_Business_Development.md
│   ├── LENS_02_Marketing_Materials.md
│   ├── LENS_03_Lead_Magnets.md
│   ├── LENS_04_Content_Creation.md
│   ├── LENS_05_Social_Media.md
│   ├── LENS_06_Prospecting.md
│   ├── LENS_07_Portfolio_Projects.md
│   ├── LENS_08_Case_Studies.md
│   ├── LENS_09_Training_Workshops.md
│   └── LENS_10_Consultant_Education.md
│
├── Project_Prompts/
│   └── [10 project-specific prompts]
│
└── Reference_Only/
    ├── FILE_MAP.md
    └── TEST_SUITE.md
```

---
CHUNK_ID: MMB-B.3-001
TOPIC: example
SUBTOPIC: ai_consultancy_sync
INSIGHT_TYPE: example
RELEVANCE: multi_project
APPLICATION: maintenance
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: sync matrix, example sync, AI consultancy
---

## B.3 Sync Matrix

| Document | 01 | 02 | 03 | 04 | 05 | 06 | 07 | 08 | 09 | 10 |
|----------|----|----|----|----|----|----|----|----|----|----|
| Master Intelligence Brief | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Base System Prompt | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Maintenance SOP | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Delivery Methodology | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Brand Guidelines | — | ✓ | ✓ | ✓ | ✓ | — | — | ✓ | ✓ | — |
| Writing Voice | — | ✓ | — | ✓ | ✓ | — | — | ✓ | — | — |
| SEO Keywords | — | ✓ | ✓ | ✓ | ✓ | — | — | — | — | — |

Projects: 01=Business Development, 02=Marketing, 03=Lead Magnets, 04=Content, 05=Social Media, 06=Prospecting, 07=Portfolio, 08=Case Studies, 09=Training, 10=Education

---
CHUNK_ID: MMB-B.4-001
TOPIC: example
SUBTOPIC: ai_consultancy_agent_types
INSIGHT_TYPE: example
RELEVANCE: multi_project
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: agent types example, AI consultancy agent classification
---

## B.4 Agent Type Classifications

| Project | Primary | Secondary | Key Implication |
|---------|---------|-----------|-----------------|
| Business Development | Strategy/Advisory | Business/Operations | Structured recommendations |
| Marketing Materials | Content Creation | Strategy/Advisory | Publication-ready outputs |
| Lead Magnets | Content Creation | Educational/Tutoring | Value-first, conversion-aware |
| Content Creation | Content Creation | Strategy/Advisory | Voice-consistent, SEO-aware |
| Social Media | Content Creation | Support/Communication | Platform-appropriate, engaging |
| Prospecting | Support/Communication | Content Creation | Personal, response-oriented |
| Portfolio Projects | Strategy/Advisory | Creative Generation | Ideation, evaluation |
| Case Studies | Content Creation | Business/Operations | Narrative, results-focused |
| Training | Educational/Tutoring | Content Creation | Progressive, engaging |
| Consultant Education | Information Retrieval | Educational/Tutoring | Synthesis, prioritization |

---

# APPENDIX C: GLOSSARY

---
CHUNK_ID: MMB-C.1-001
TOPIC: glossary
SUBTOPIC: terms
INSIGHT_TYPE: reference
RELEVANCE: both
APPLICATION: discovery
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: glossary, definitions, terms
---

## Glossary of Terms

**Agent Type:** Classification of a GPT/Project's primary function from a taxonomy of 10 types (Information Retrieval, Creative Generation, Technical, Educational/Tutoring, Business/Operations, Strategy/Advisory, Support/Communication, Personal Productivity, Content Creation, Specialized Domain).

**Base System Prompt:** The foundational layer of instructions defining universal behaviors that apply regardless of specific query. Handles core identity, retrieval configuration, error handling, and maintenance triggers.

**Boundary Overlap:** Technique of repeating 1-2 transitional sentences at chunk boundaries to preserve logical connections regardless of which chunk retrieves.

**Chunk:** A segment of content sized for optimal retrieval (typically 600-1000 tokens). Should be self-contained while maintaining connections to related content.

**Confidence Weighting:** System for presenting information based on certainty level (established, recommended, experimental).

**Data Freshness:** Metadata field tracking when content was last validated. Used for staleness flagging.

**Knowledge Base (KB):** The collection of documents uploaded to a GPT/Project that it can retrieve from when answering queries.

**Lens Document:** A project-specific document that defines how one project should use a shared master knowledge document. Specifies retrieval weights, behavioral adjustments, and application context.

**Maintenance Mode:** A triggered state where the system shifts from normal operation to KB update procedures. Activated by phrases like "update," "maintenance," etc.

**Master Intelligence Brief (MIB):** A comprehensive knowledge document containing deep domain expertise, properly chunked with metadata for retrieval optimization.

**Metadata:** Structured information about a chunk that aids retrieval and appropriate use. The 9-field schema includes: CHUNK_ID, TOPIC, SUBTOPIC, INSIGHT_TYPE, RELEVANCE, APPLICATION, CONFIDENCE, DATA_FRESHNESS, KEYWORDS.

**Multi-Project Architecture:** A system of multiple related GPTs/Projects sharing common knowledge through Universal and Shared documents, with project-specific customization through Lens documents and Project prompts.

**Project System Prompt:** The project-specific layer of instructions defining mission, KB integration, behavioral guidance, and output standards for a particular GPT/Project.

**RAG (Retrieval-Augmented Generation):** An architecture where AI retrieves relevant content from a knowledge base before generating responses. This methodology achieves RAG-like behavior using native platform retrieval rather than custom infrastructure.

**Single-Project Architecture:** A standalone GPT/Project with self-contained knowledge, no sharing with other projects.

**Spec Confirmation:** Protocol for confirming understanding before generating complex outputs to prevent wasted effort from misunderstood requirements.

**Sync:** The process of propagating updates to Universal or Shared documents across all affected projects in a multi-project system.

**Universal Documents:** Documents that every project in a multi-project system needs. Synced to all projects.

---

# APPENDIX D: PLATFORM-SPECIFIC NOTES

---
CHUNK_ID: MMB-D.1-001
TOPIC: platform_notes
SUBTOPIC: claude_specifics
INSIGHT_TYPE: reference
RELEVANCE: both
APPLICATION: implementation
CONFIDENCE: established
DATA_FRESHNESS: 2025-01
KEYWORDS: Claude Projects, Anthropic, platform notes
---

## D.1 Claude Projects Notes

**Strengths:**
- Project memory persists across conversations
- Generally consistent retrieval behavior
- Clean separation of Instructions (prompts) and Knowledge (files)
- Handles markdown formatting well

**Limitations:**
- Smaller file format support than GPTs
- No web browsing, image generation, or code execution capabilities
- Limited sharing options (link only, no store)

**Best Practices:**
- Use .md files for all knowledge documents
- Paste base prompt first, project prompt second in Instructions
- Test retrieval thoroughly — Claude tends to be conservative
- Use explicit maintenance triggers — they work reliably

**Known Quirks:**
- Very long Instructions fields may get truncated — keep prompts focused
- Project memory can be cleared by user — don't rely on it for critical info
- Retrieval may miss content if chunk boundaries are unclear

---
CHUNK_ID: MMB-D.2-001
TOPIC: platform_notes
SUBTOPIC: gpt_specifics
INSIGHT_TYPE: reference
RELEVANCE: both
APPLICATION: implementation
CONFIDENCE: established
DATA_FRESHNESS: 2025-01
KEYWORDS: Custom GPT, OpenAI, platform notes
---

## D.2 Custom GPT Notes

**Character Limit Solution:**
Custom GPTs have an 8,000 character limit on Instructions. Use hybrid architecture to maintain full sophistication:
- Core prompt (~7.5K chars) in Instructions field
- Extended protocols in Knowledge Base documents
- Retrieval instructions connect Instructions to KB content

**Strengths:**
- Additional capabilities (web, DALL-E, code interpreter)
- GPT Store distribution
- Broader file format support
- Larger user base
- Hybrid architecture demonstrates platform optimization

**Limitations (Solved):**
- ~~Single Instructions field limitation~~ → Solved with hybrid architecture
- Retrieval can be inconsistent → Mitigated with clear KB organization
- No memory between conversations (only within)
- Updates require re-configuring through builder

**Hybrid Architecture Best Practices:**
- Keep essential identity and discovery flow in Instructions
- Move complex protocols to BEHAVIORAL_PROTOCOLS.md
- Include clear KB retrieval instructions in core prompt
- Test KB document retrieval thoroughly
- Upload Knowledge Base files in recommended order

**Known Quirks:**
- Character count validation: Keep Instructions under 8,000 characters
- Retrieval sometimes ignores uploaded files — test thoroughly
- KB organization affects retrieval quality — use clear section headers
- Capabilities can interfere — disable unused ones
- GPT Store review can be slow

**Troubleshooting Hybrid Architecture:**
- If complex behaviors don't work → Check KB retrieval instructions
- If character limit exceeded → Move more content to KB documents
- If retrieval fails → Test KB document structure and naming
- If inconsistent responses → Verify core prompt references correct KB sections

---

**END OF MASTER METHODOLOGY BRIEF**

---

**Document Version:** 2.0 (GPT Optimization Update)  
**Total Chunks:** ~65  
**Created:** 2025-01-20  
**Updated:** 2025-02-09  
**Status:** Complete - includes hybrid architecture for Custom GPT 8K limit
