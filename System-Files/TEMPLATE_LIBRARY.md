# TEMPLATE LIBRARY
## MetaGPT Builder - Templates & Examples

**Document Type:** Knowledge Base (GPT-Optimized)
**Version:** 2.0 (GPT Hybrid Architecture)
**Last Updated:** 2025-02-09
**Purpose:** Complete template library for Custom GPT hybrid architecture

**Usage:** Referenced by GPT_CORE_SYSTEM_PROMPT.md for template generation tasks

---

## TABLE OF CONTENTS

1. [System Prompt Templates](#section-1-system-prompt-templates)
2. [Knowledge Base Templates](#section-2-knowledge-base-templates)
3. [Metadata Schema Examples](#section-3-metadata-schema-examples)
4. [File Structure Templates](#section-4-file-structure-templates)
5. [Implementation Guide Templates](#section-5-implementation-guide-templates)
6. [Testing Templates](#section-6-testing-templates)

---

# SECTION 1: SYSTEM PROMPT TEMPLATES

## Base System Prompt Template

```markdown
# BASE SYSTEM PROMPT
## [Project Name] — Universal Behavioral Layer

**Document Type:** System Prompt (Base Layer)  
**Version:** 1.0  
**Last Updated:** [DATE]  
**Position:** Paste FIRST in Instructions field

---

## CORE IDENTITY

You are [AGENT NAME], an expert system for [PRIMARY PURPOSE].

**Your expertise:**
- [Expertise area 1]
- [Expertise area 2]
- [Expertise area 3]
- [Expertise area 4]

**Your approach:**
- [Approach principle 1]
- [Approach principle 2]
- [Approach principle 3]
- [Approach principle 4]

**Your relationship to users:**
[Description of how you interact with and serve users]

---

## RETRIEVAL CONFIGURATION

### Standard Mode (Default)

Retrieve from [PRIMARY_KB_NAME].md based on query relevance:

| Query Type | Priority Sections |
|------------|-------------------|
| [Query type 1] | [Section reference] |
| [Query type 2] | [Section reference] |
| [Query type 3] | [Section reference] |

**Exclusions:**
Do NOT retrieve [RESTRICTED_DOCS] unless [TRIGGER_CONDITION].

---

## RESPONSE STANDARDS

### Content Quality
- Use active voice and clear language
- Provide specific examples when possible
- Reference knowledge sections appropriately
- Include implementation guidance, not just theory

### Formatting
- Use headers to organize complex responses
- Employ tables for structured information
- Use bullet points for lists (when appropriate)
- Code blocks for templates and technical content

### Length Guidelines
- Explanatory responses: 2-4 paragraphs
- Generated content: Match requested specifications
- [Additional guidelines based on agent type]

---

## ERROR HANDLING

### Missing Information
When you lack information needed to respond well:
1. Acknowledge what you can answer
2. Identify specifically what's missing
3. Ask a focused clarifying question
4. Do not fabricate or guess

### Outside Scope
**In scope:** [List what's included]
**Outside scope:** [List what's excluded]

---

**END OF BASE SYSTEM PROMPT**
```

## Project System Prompt Template

```markdown
# PROJECT PROMPT: [Project Name]
## Project-Specific Behavioral Layer

**Document Type:** System Prompt (Project Layer)  
**Version:** 1.0  
**Last Updated:** [DATE]  
**Position:** Paste SECOND in Instructions field (after Base System Prompt)

---

## PROJECT MISSION

[Detailed description of what this specific project does]

**You transform user requirements into:**
- [Deliverable type 1]
- [Deliverable type 2]
- [Deliverable type 3]

**This project is for:**
- [Use case 1]
- [Use case 2]
- [Use case 3]

**This project is NOT for:**
- [Exclusion 1] → [Alternative]
- [Exclusion 2] → [Alternative]

---

## KB INTEGRATION

| Document | Priority | Use For |
|----------|----------|---------|
| [PRIMARY_KB].md | PRIMARY | [Usage description] |
| [SECONDARY_KB].md | SUPPORTING | [Usage description] |
| [REFERENCE_KB].md | REFERENCE | [Usage description] |

---

## BEHAVIORAL GUIDANCE

### Tone
- [Tone characteristic 1]
- [Tone characteristic 2]
- [Tone characteristic 3]

### Always
- [Always rule 1]
- [Always rule 2]
- [Always rule 3]

### Never
- [Never rule 1]
- [Never rule 2]
- [Never rule 3]

---

**END OF PROJECT PROMPT**
```

## Combined System Prompt Template (Single Project)

```markdown
# SYSTEM PROMPT: [Project Name]
## Complete Behavioral System

**Document Type:** System Prompt (Combined)  
**Version:** 1.0  
**Last Updated:** [DATE]  
**Platform:** [Claude Projects / Custom GPT]

---

## CORE IDENTITY
[Combined identity section from base + project]

## MISSION & SCOPE
[Project-specific mission and boundaries]

## KNOWLEDGE INTEGRATION
[How to use knowledge base documents]

## BEHAVIORAL STANDARDS
[Combined behavioral guidelines]

## RESPONSE PROTOCOLS
[Platform-specific response standards]

---

**END OF SYSTEM PROMPT**
```

---

# SECTION 2: KNOWLEDGE BASE TEMPLATES

## Master Information Brief (MIB) Template

```markdown
# [DOMAIN] KNOWLEDGE BASE
## Master Information Brief

**Document Type:** Knowledge Base  
**Version:** 1.0  
**Last Updated:** [DATE]  
**Agent:** [Agent Name]  
**Scope:** [Single Project / Universal Base / Shared Resource]

---

## CHANGELOG

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | [DATE] | Initial creation | [CREATOR] |

---

## TABLE OF CONTENTS

1. [Section 1 Title](#section-1-title)
2. [Section 2 Title](#section-2-title)
3. [Section 3 Title](#section-3-title)
[etc.]

---

# SECTION 1: [TITLE]

---
CHUNK_ID: [ID]
TOPIC: [topic]
SUBTOPIC: [subtopic]
INSIGHT_TYPE: [type]
RELEVANCE: [relevance]
APPLICATION: [application]
CONFIDENCE: [confidence]
DATA_FRESHNESS: [freshness]
KEYWORDS: [keywords]
---

## 1.1 [Subsection Title]

[Content - 600-1000 tokens]

[Include specific procedures, frameworks, examples relevant to the topic]

---
CHUNK_ID: [NEXT_ID]
[Next chunk metadata]
---

## 1.2 [Subsection Title]

[Continue pattern for all content]

---

# SECTION 2: [TITLE]
[Continue section pattern]

---

## APPENDIX A: QUICK REFERENCE
[Key information for rapid access]

## APPENDIX B: STATISTICS AND DATA
[Easily updatable numerical information]

## APPENDIX C: GLOSSARY
[Key terms and definitions]

---

**END OF KNOWLEDGE BASE**
```

## Lens Document Template (Multi-Project)

```markdown
# LENS DOCUMENT: [Project Name]
## Project-Specific Knowledge View

**Document Type:** Lens  
**Version:** 1.0  
**Last Updated:** [DATE]  
**Parent KB:** [MASTER_KB_NAME]  
**Project Focus:** [Specific focus area]

---

## PROJECT OVERVIEW

**Primary Function:** [What this project does]  
**Target Audience:** [Who uses it]  
**Key Outputs:** [What it produces]  
**Knowledge Priority:** [What information is most important]

---

## RETRIEVAL WEIGHTS

This lens prioritizes content from the master KB based on project needs:

| Content Category | Weight | Reason |
|------------------|--------|---------|
| [Category 1] | HIGH | [Why important for this project] |
| [Category 2] | MEDIUM | [Why moderately important] |
| [Category 3] | LOW | [When needed] |
| [Category 4] | EXCLUDE | [Why not relevant] |

---

## CHUNK REFERENCES

### High Priority Chunks
- [CHUNK_ID]: [Brief description of why prioritized]
- [CHUNK_ID]: [Brief description of why prioritized]

### Medium Priority Chunks  
- [CHUNK_ID]: [Brief description]
- [CHUNK_ID]: [Brief description]

### Context-Specific Chunks
- [CHUNK_ID]: [When to use]
- [CHUNK_ID]: [When to use]

---

## PROJECT-SPECIFIC GUIDANCE

### Behavioral Modifications
[How this project's behavior differs from universal base]

### Output Formatting
[Specific formatting requirements for this project]

### Constraint Handling
[Project-specific limitations or requirements]

---

## GAP ASSESSMENT

### Covered Well
[What the master KB handles well for this project]

### Potential Gaps
[What might be missing or need enhancement]

### Future Expansion
[Areas for potential growth]

---

**END OF LENS DOCUMENT**
```

---

# SECTION 3: METADATA SCHEMA EXAMPLES

## Complete 9-Field Schema

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

## Field Definitions

**CHUNK_ID:** Unique identifier for cross-referencing
- Format: [DOC]-[Section].[Subsection]-[Number]
- Example: MIB-2.3-001

**TOPIC:** Primary category for broad filtering
- Examples: procedures, frameworks, examples, policies

**SUBTOPIC:** Specific focus for narrow filtering  
- Examples: customer_onboarding, pricing_strategy, quality_control

**INSIGHT_TYPE:** Content classification
- concept: Foundational ideas and principles
- framework: Structured approaches and methodologies
- procedure: Step-by-step instructions
- example: Specific instances and case studies
- template: Reusable formats and structures
- warning: Important caveats and cautions

**RELEVANCE:** Project applicability
- single_project: Only relevant to standalone projects
- multi_project: Only relevant to multi-project systems
- both: Relevant to any project type

**APPLICATION:** Usage context
- discovery: Used during requirements gathering
- architecture: Used during system design
- generation: Used during content creation
- implementation: Used during deployment
- maintenance: Used during updates and improvements

**CONFIDENCE:** Certainty level
- established: Proven, widely accepted
- recommended: Best practice, strong evidence
- experimental: Promising but unproven

**DATA_FRESHNESS:** Currency information
- YYYY-MM: Last verified date for time-sensitive content
- evergreen: Content that doesn't age

**KEYWORDS:** Retrieval optimization terms
- Comma-separated list of relevant search terms
- Include synonyms and related concepts

## Example Metadata Blocks

### Concept Example
```
---
CHUNK_ID: MIB-1.2-003
TOPIC: knowledge_architecture
SUBTOPIC: retrieval_optimization
INSIGHT_TYPE: concept
RELEVANCE: both
APPLICATION: architecture
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: chunking, metadata, retrieval, optimization, knowledge base
---
```

### Procedure Example
```
---
CHUNK_ID: MIB-3.1-007
TOPIC: content_processing
SUBTOPIC: document_chunking
INSIGHT_TYPE: procedure
RELEVANCE: both
APPLICATION: generation
CONFIDENCE: established
DATA_FRESHNESS: evergreen
KEYWORDS: chunking, segmentation, boundaries, tokens, processing
---
```

### Warning Example
```
---
CHUNK_ID: MIB-4.2-012
TOPIC: platform_limitations
SUBTOPIC: custom_gpt_constraints
INSIGHT_TYPE: warning
RELEVANCE: single_project
APPLICATION: implementation
CONFIDENCE: established
DATA_FRESHNESS: 2025-02
KEYWORDS: custom gpt, limitations, character limit, constraints
---
```

---

# SECTION 4: FILE STRUCTURE TEMPLATES

## Single Project Structure
```
[PROJECT_NAME]/
├── README.md                    # Project overview and setup
├── SYSTEM_PROMPT.md             # Combined behavioral instructions
├── [DOMAIN]_KNOWLEDGE_BASE.md   # Main information repository
├── MAINTENANCE_SOP.md           # Update procedures
├── CHANGELOG.md                 # Version history
├── FILE_MAP.md                  # Architecture reference
├── TEST_SUITE.md               # Validation protocols
└── IMPLEMENTATION_GUIDE.md      # Platform-specific setup
```

## Multi-Project Structure
```
[SYSTEM_NAME]/
├── README.md                           # System overview
├── ARCHITECTURE_OVERVIEW.md           # System design document
├── Universal/
│   ├── MASTER_[DOMAIN]_BRIEF.md       # Shared knowledge base
│   ├── BASE_SYSTEM_PROMPT.md          # Universal behaviors
│   └── MAINTENANCE_SOP.md             # System-wide procedures
├── Shared/
│   ├── [SHARED_RESOURCE_1].md
│   └── [SHARED_RESOURCE_2].md
├── Projects/
│   ├── Project_01_[NAME]/
│   │   ├── LENS_01_[NAME].md
│   │   └── PROJECT_PROMPT_01.md
│   ├── Project_02_[NAME]/
│   │   ├── LENS_02_[NAME].md
│   │   └── PROJECT_PROMPT_02.md
│   └── [Additional projects...]
├── Documentation/
│   ├── FILE_MAP.md
│   ├── CHANGELOG.md
│   └── TEST_SUITE.md
└── Implementation/
    ├── CLAUDE_SETUP_GUIDE.md
    └── GPT_SETUP_GUIDE.md
```

## GPT-Optimized Structure
```
[PROJECT_NAME]_GPT_OPTIMIZED/
├── README.md                           # Setup overview
├── Core_System/
│   └── GPT_CORE_SYSTEM_PROMPT.md     # <8K instructions
├── Knowledge_Base/
│   ├── BEHAVIORAL_PROTOCOLS.md        # Advanced behaviors
│   ├── GENERATION_PROCEDURES.md       # Content workflows
│   ├── TEMPLATE_LIBRARY.md           # Templates & examples
│   ├── PLATFORM_GUIDES.md            # Implementation specifics
│   └── [DOMAIN]_KNOWLEDGE_BASE.md    # Domain expertise
├── Documentation/
│   ├── SETUP_GUIDE.md                 # Platform configuration
│   ├── ARCHITECTURE_NOTES.md          # Hybrid design explanation
│   └── TEST_SUITE.md                 # Validation protocols
└── Reference/
    ├── FILE_MAP.md                    # Architecture reference
    └── CHANGELOG.md                   # Version history
```

---

# SECTION 5: IMPLEMENTATION GUIDE TEMPLATES

## Claude Project Implementation

```markdown
## IMPLEMENTATION: Claude Project

### Step 1: Create Project
1. Go to claude.ai → Projects → New Project
2. Name: "[PROJECT_NAME]"
3. Description: "[PROJECT_DESCRIPTION]"

### Step 2: Configure Instructions
1. Click "Set custom instructions"
2. Paste the following in order:
   - **First:** Complete contents of `BASE_SYSTEM_PROMPT.md`
   - **Second:** Complete contents of `PROJECT_PROMPT_[NAME].md`

### Step 3: Upload Knowledge Base
Upload these files to the project knowledge:
- `[PRIMARY_KB].md` (main knowledge repository)
- `MAINTENANCE_SOP.md` (update procedures)
- `CHANGELOG.md` (version tracking)
[Additional files as needed]

### Step 4: Local Reference Files
Keep these files locally (do NOT upload):
- `FILE_MAP.md` (your architecture reference)
- `TEST_SUITE.md` (for manual validation)
- `IMPLEMENTATION_GUIDE.md` (this document)

### Step 5: Initial Testing
Test with these validation queries:
1. **Basic Function:** "[Test query 1]"
2. **Knowledge Retrieval:** "[Test query 2]"
3. **Edge Case:** "[Test query 3]"

### Step 6: Ongoing Maintenance
- Review `MAINTENANCE_SOP.md` for update procedures
- Check `CHANGELOG.md` for version history
- Run test queries after any updates

**Expected Results:** [Description of what successful responses look like]
```

## Custom GPT Implementation

```markdown
## IMPLEMENTATION: Custom GPT

### Step 1: Create GPT
1. Go to chat.openai.com → Explore GPTs → Create a GPT
2. Name: "[PROJECT_NAME]"
3. Description: "[PROJECT_DESCRIPTION]"

### Step 2: Configure Instructions
1. Go to Configure tab
2. In Instructions field, paste complete contents of:
   `GPT_SYSTEM_PROMPT.md` (combined base + project prompt)

### Step 3: Upload Knowledge Files
Upload these files to Knowledge:
- `[PRIMARY_KB].md` (main knowledge repository)
- `MAINTENANCE_SOP.md` (update procedures)
- `CHANGELOG.md` (version tracking)
[Additional files as needed]

### Step 4: Set Conversation Starters
Add these starter prompts:
- "[Starter 1 relevant to main function]"
- "[Starter 2 for getting started]"
- "[Starter 3 for specific use case]"
- "[Starter 4 for learning about system]"

### Step 5: Configure Capabilities
**Recommended settings:**
- Web Browsing: [ON/OFF based on needs]
- DALL-E Image Generation: [Usually OFF]
- Code Interpreter: [ON/OFF based on needs]

### Step 6: Local Reference Files
Keep these files locally (do NOT upload):
- `FILE_MAP.md` (your architecture reference)
- `TEST_SUITE.md` (for manual validation)
- `IMPLEMENTATION_GUIDE.md` (this document)

### Step 7: Initial Testing
Test with these validation queries:
1. **Basic Function:** "[Test query 1]"
2. **Knowledge Retrieval:** "[Test query 2]"  
3. **Edge Case:** "[Test query 3]"

### Step 8: Publishing (Optional)
- Set privacy to Public if sharing
- Add appropriate category
- Include clear description and usage instructions

**Expected Results:** [Description of what successful responses look like]
```

## GPT-Optimized Implementation

```markdown
## IMPLEMENTATION: Custom GPT (Optimized)

### Step 1: Create GPT
1. Go to chat.openai.com → Explore GPTs → Create a GPT
2. Name: "[PROJECT_NAME] - Optimized"
3. Description: "[PROJECT_DESCRIPTION] (Platform-optimized hybrid architecture)"

### Step 2: Configure Core Instructions
1. Go to Configure tab
2. In Instructions field, paste complete contents of:
   `GPT_CORE_SYSTEM_PROMPT.md` (~7.5K characters)

### Step 3: Upload Knowledge Base (Critical)
Upload these files to Knowledge in this order:
1. `BEHAVIORAL_PROTOCOLS.md` (advanced behaviors)
2. `GENERATION_PROCEDURES.md` (content workflows)
3. `TEMPLATE_LIBRARY.md` (templates & examples)
4. `PLATFORM_GUIDES.md` (implementation guidance)
5. `[DOMAIN]_KNOWLEDGE_BASE.md` (domain expertise)
[Additional files as needed]

**Important:** The core instructions rely on these KB documents for full functionality.

### Step 4: Test Hybrid Architecture
Verify that instructions properly reference KB documents:
1. **Test retrieval:** Ask for complex procedure → Should reference BEHAVIORAL_PROTOCOLS.md
2. **Test generation:** Ask for template → Should reference TEMPLATE_LIBRARY.md  
3. **Test implementation:** Ask about setup → Should reference PLATFORM_GUIDES.md

### Step 5: Configure Conversation Starters
Add these optimized starters:
- "[Starter showing main function]"
- "[Starter demonstrating KB retrieval]"
- "[Starter for platform-specific guidance]"
- "[Starter for learning about hybrid approach]"

### Step 6: Validation Testing
Run complete test suite to ensure hybrid architecture works:
- Core behavioral responses
- Knowledge base retrieval
- Complex procedure handling
- Template generation
- Platform-specific guidance

**Architecture Note:** This version uses Instructions + KB hybrid to work within Custom GPT's 8K character limit while maintaining full sophistication.
```

---

# SECTION 6: TESTING TEMPLATES

## Basic Test Suite Template

```markdown
# TEST SUITE
## [Project Name] Validation Protocols

**Document Type:** Testing  
**Version:** 1.0  
**Last Updated:** [DATE]  
**Purpose:** Validation tests for [project type]

---

## TEST CATEGORIES

### Category 1: Basic Functionality
**Purpose:** Verify core behaviors work correctly

**Test 1.1: Primary Function**
- **Query:** "[Test main function]"
- **Expected:** [Description of correct response]
- **Pass Criteria:** [Specific requirements]

**Test 1.2: Identity Recognition**
- **Query:** "What are you?"
- **Expected:** [Correct identity response]
- **Pass Criteria:** [Identity accuracy requirements]

### Category 2: Knowledge Retrieval
**Purpose:** Verify knowledge base integration works

**Test 2.1: Direct Knowledge Query**
- **Query:** "[Ask for specific information from KB]"
- **Expected:** [Accurate information retrieval]
- **Pass Criteria:** [Information accuracy and completeness]

**Test 2.2: Complex Knowledge Query**
- **Query:** "[Ask for synthesis of multiple KB sections]"
- **Expected:** [Comprehensive response drawing from multiple sources]
- **Pass Criteria:** [Synthesis quality and accuracy]

### Category 3: Edge Cases
**Purpose:** Verify proper handling of unusual situations

**Test 3.1: Out of Scope Request**
- **Query:** "[Ask for something outside scope]"
- **Expected:** [Polite decline with scope clarification]
- **Pass Criteria:** [Clear boundary communication]

**Test 3.2: Ambiguous Request**
- **Query:** "[Unclear or ambiguous request]"
- **Expected:** [Clarifying question]
- **Pass Criteria:** [Appropriate clarification seeking]

### Category 4: Platform-Specific
**Purpose:** Verify platform-appropriate behavior

[Platform-specific tests based on Claude vs GPT deployment]

---

## REGRESSION TEST SUITE

**Critical tests to run after any updates:**

### REG-001: Core Function
[Most important functionality test]

### REG-002: Knowledge Integration
[Most important retrieval test]

### REG-003: Behavioral Standards
[Most important behavior test]

---

## TESTING PROCEDURES

### Before Deployment
1. Run complete test suite
2. Verify all tests pass
3. Document any failures or unexpected behaviors
4. Address issues before going live

### After Updates
1. Run regression test suite minimum
2. Run full suite for major changes
3. Update test suite if new functionality added
4. Document test results

### Periodic Validation
1. Monthly: Run regression tests
2. Quarterly: Run full test suite
3. Annually: Review and update test suite

---

**END OF TEST SUITE**
```

## GPT-Optimized Test Template

```markdown
# HYBRID ARCHITECTURE TEST SUITE
## GPT-Optimized Version Validation

### Test Category: Instructions + KB Integration

**Test H.1: KB Document Retrieval**
- **Query:** "I need help with maintenance mode"
- **Expected:** References BEHAVIORAL_PROTOCOLS.md Section 3
- **Pass Criteria:** Correctly retrieves and applies maintenance procedures

**Test H.2: Template Generation**  
- **Query:** "Give me a system prompt template"
- **Expected:** References TEMPLATE_LIBRARY.md
- **Pass Criteria:** Provides complete template from KB

**Test H.3: Complex Generation**
- **Query:** "Help me build a complete project"
- **Expected:** References GENERATION_PROCEDURES.md for workflow
- **Pass Criteria:** Follows proper generation sequence from KB

### Test Category: Character Limit Compliance

**Test C.1: Instructions Field Size**
- **Verification:** Count characters in GPT_CORE_SYSTEM_PROMPT.md
- **Pass Criteria:** Under 8,000 characters

**Test C.2: Functionality Preservation**
- **Verification:** Compare outputs to full system version
- **Pass Criteria:** Equivalent quality and capability

---

**END OF HYBRID TESTS**
```

---

**END OF TEMPLATE LIBRARY**

**Related Documents:**
- GPT_CORE_SYSTEM_PROMPT.md (references this library)
- BEHAVIORAL_PROTOCOLS.md (uses these templates)
- GENERATION_PROCEDURES.md (implements these templates)
- PLATFORM_GUIDES.md (deployment using these templates)
