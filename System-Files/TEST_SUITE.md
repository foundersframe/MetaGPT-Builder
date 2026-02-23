# TEST SUITE
## MetaGPT Builder — Validation Tests

**Document Type:** Test Suite  
**Version:** 2.0 (GPT Optimization Update)  
**Last Updated:** 2025-02-09  
**Status:** Active

---

## PURPOSE

This test suite validates that the MetaGPT Builder:
1. Retrieves correct content for queries
2. Follows behavioral protocols
3. Handles edge cases gracefully
4. Maintains quality after updates

**Usage:** Run tests after initial setup and after any significant updates. Document results in Test Run History.

---

## RETRIEVAL TESTS

### R-001: Foundations Retrieval
**Query:** "What's the difference between a knowledge system and a chatbot?"  
**Expected:** Content from Section 1 (Foundations), specifically chunk MMB-1.1-001  
**Pass Criteria:** Response explains knowledge systems vs chatbots, mentions retrieval optimization

### R-002: Discovery Retrieval
**Query:** "What questions should I ask before building a GPT?"  
**Expected:** Content from Section 2 (Discovery), question sequence  
**Pass Criteria:** Response includes discovery questions in logical sequence

### R-003: Agent Taxonomy Retrieval
**Query:** "What type of agent should I use for a customer support bot?"  
**Expected:** Content from Section 3 (Agent Taxonomy)  
**Pass Criteria:** Response identifies Support/Communication as primary type, explains implications

### R-004: System Prompt Retrieval
**Query:** "How do I structure a system prompt?"  
**Expected:** Content from Section 4 (System Prompts)  
**Pass Criteria:** Response explains two-layer system (base + project), lists key sections

### R-005: KB Design Retrieval
**Query:** "Should I use one big document or multiple small files?"  
**Expected:** Content from Section 5 (KB Design), consolidation vs separation  
**Pass Criteria:** Response explains when to consolidate vs separate, gives criteria

### R-006: Chunking Retrieval
**Query:** "How big should my chunks be?"  
**Expected:** Content from Section 6 (Chunking), specifically chunk size guidance  
**Pass Criteria:** Response states 600-1000 tokens, explains why

### R-007: Boundary Overlap Retrieval
**Query:** "How do I preserve context between sections?"  
**Expected:** Content from Section 6 (Chunking), boundary overlap technique  
**Pass Criteria:** Response explains boundary overlap with example

### R-008: Metadata Retrieval
**Query:** "What metadata should I add to my chunks?"  
**Expected:** Content from Section 7 (Metadata), 9-field schema  
**Pass Criteria:** Response lists all 9 fields with purposes

### R-009: Lens Document Retrieval
**Query:** "What is a lens document?"  
**Expected:** Content from Section 8 (Lens Documents)  
**Pass Criteria:** Response explains lens documents, when needed, structure

### R-010: Maintenance Retrieval
**Query:** "How do I update my GPT's knowledge base?"  
**Expected:** Content from Section 9 (Maintenance)  
**Pass Criteria:** Response explains update types, general procedures

### R-011: Testing Retrieval
**Query:** "How do I test if my GPT is working correctly?"  
**Expected:** Content from Section 10 (Testing)  
**Pass Criteria:** Response explains test categories, gives examples

### R-012: Implementation Retrieval
**Query:** "How do I set up a Claude Project?"  
**Expected:** Content from Section 12 (Implementation), Claude-specific  
**Pass Criteria:** Response gives step-by-step Claude Project setup

### R-013: Template Retrieval
**Query:** "Give me a template for a system prompt"  
**Expected:** Content from Appendix A (Templates)  
**Pass Criteria:** Response provides complete, usable template

### R-014: Example Retrieval
**Query:** "Show me an example of a multi-project system"  
**Expected:** Content from Appendix B (Example Build)  
**Pass Criteria:** Response describes AI Consultancy example structure

### R-015: Glossary Retrieval
**Query:** "What does RAG mean?"  
**Expected:** Content from Appendix C (Glossary)  
**Pass Criteria:** Response provides definition from glossary

### R-016: Platform Differences Retrieval
**Query:** "What's the difference between Claude Projects and Custom GPTs?"  
**Expected:** Content from updated platform sections showing hybrid architecture for Custom GPTs  
**Pass Criteria:** Response explains Claude uses full prompts, Custom GPT uses hybrid architecture (core + KB), both deliver equivalent functionality

---

## BEHAVIORAL TESTS

### B-001: Single vs Multi-Project Question
**Query:** "I want to build a GPT"  
**Expected:** First question asks about single vs multi-project  
**Pass Criteria:** Response asks "Is this a single GPT/Project, or a system of multiple related projects?" (or equivalent)

### B-002: Discovery Flow Initiation
**Query:** "Help me create a customer support bot"  
**Expected:** Initiates discovery flow, doesn't jump to building  
**Pass Criteria:** Response asks clarifying questions before generating any documents

### B-003: Spec Confirmation
**Query:** "Build me a complete GPT for managing recipes with a knowledge base of cooking techniques, for home cooks, on Claude"  
**Expected:** Confirms spec before generating  
**Pass Criteria:** Response restates understanding and asks for confirmation

### B-004: Simple Query No Confirmation
**Query:** "What is chunking?"  
**Expected:** Direct answer without confirmation request  
**Pass Criteria:** Response explains chunking directly, no unnecessary confirmation

### B-005: Platform Clarification
**Query:** "I want to build a GPT" (without specifying platform)  
**Expected:** Asks which platform  
**Pass Criteria:** Response asks about Claude Project vs Custom GPT

### B-006: Agent Type Determination
**Query:** "I'm building something to help people learn Spanish"  
**Expected:** Identifies Educational/Tutoring as primary type  
**Pass Criteria:** Response identifies agent type and explains behavioral implications

### B-007: Complete Deliverable Generation
**Query:** "Create a system prompt for a simple FAQ bot for a coffee shop" (after discovery completed)  
**Expected:** Complete, usable system prompt  
**Pass Criteria:** Response provides full prompt with all sections, no placeholders

### B-008: Implementation Guidance
**Query:** (After generating documents) "How do I set this up?"  
**Expected:** Platform-specific implementation steps  
**Pass Criteria:** Response provides step-by-step setup instructions

### B-009: Maintenance Mode Trigger
**Query:** "I need to update the methodology"  
**Expected:** Shifts to maintenance mode  
**Pass Criteria:** Response acknowledges maintenance mode, asks about update type

### B-010: Maintenance Mode Classification
**Query:** "The chunk size recommendation is wrong"  
**Expected:** Classifies as CORRECTION  
**Pass Criteria:** Response identifies update type, follows correction procedure

### B-011: Data Freshness Flagging
**Query:** "What's the Custom GPT character limit for instructions?"  
**Expected:** Provides information with current data  
**Pass Criteria:** Response states 8,000 characters and mentions hybrid architecture solution

### B-012: Confidence Weighting
**Query:** "What's the best chunk size?"  
**Expected:** Presents as recommended (not absolute)  
**Pass Criteria:** Response frames as "recommended" or "best practice," not absolute rule

### B-013: Multi-Project Architecture
**Query:** "I have 5 related tools that share the same company knowledge"  
**Expected:** Recommends multi-project architecture  
**Pass Criteria:** Response identifies multi-project need, explains Universal/Shared/Project-Specific structure

### B-014: Resistance to Skipping Discovery
**Query:** "Just build me a GPT, don't ask questions"  
**Expected:** Politely insists on minimal discovery  
**Pass Criteria:** Response explains why discovery matters, asks essential questions

---

## HYBRID ARCHITECTURE TESTS

### HA-001: Custom GPT Architecture Selection
**Query:** "I want to build a sophisticated Custom GPT"  
**Expected:** Recommends hybrid architecture approach  
**Pass Criteria:** Response explains hybrid approach, mentions character limit solution

### HA-002: KB Document Retrieval Test
**Query:** "Help me with maintenance mode"  
**Expected:** Retrieves from BEHAVIORAL_PROTOCOLS.md  
**Pass Criteria:** Response provides maintenance mode procedures from KB document

### HA-003: Template Generation via KB
**Query:** "Give me a system prompt template"  
**Expected:** Retrieves from TEMPLATE_LIBRARY.md  
**Pass Criteria:** Response provides complete template from KB document

### HA-004: Platform Guide Retrieval  
**Query:** "How should I build for Custom GPT versus Claude?"  
**Expected:** Retrieves platform guidance  
**Pass Criteria:** Response explains different architectures for different platforms

### HA-005: Character Limit Awareness
**Query:** "My system prompt is too long for Custom GPT"  
**Expected:** Recommends hybrid architecture  
**Pass Criteria:** Response explains 8K limit and hybrid solution

---

## MAINTENANCE TRIGGER TESTS

### MT-001: Layer 1 — Clear Trigger (Immediate)
**Query:** "Update the methodology"  
**Expected:** Enters maintenance mode immediately  
**Pass Criteria:** Response acknowledges maintenance mode, asks about update type, does NOT ask for clarification

### MT-002: Layer 1 — Clear Trigger Variant
**Query:** "Maintenance mode"  
**Expected:** Enters maintenance mode immediately  
**Pass Criteria:** Response acknowledges maintenance mode without clarification question

### MT-003: Layer 2 — User Content Signal (Never Trigger)
**Query:** "Help me revise this document I'm working on"  
**Expected:** Treats as content assistance request, NOT maintenance  
**Pass Criteria:** Response offers to help with the document, does NOT mention maintenance mode or KB updates

### MT-004: Layer 2 — "My" Signal (Never Trigger)
**Query:** "Fix this paragraph in my draft"  
**Expected:** Treats as content assistance, NOT maintenance  
**Pass Criteria:** Response asks about the paragraph or offers editing help, no maintenance mode

### MT-005: Layer 2 — "This" Signal (Never Trigger)
**Query:** "Update this section to sound more professional"  
**Expected:** Treats as content assistance, NOT maintenance  
**Pass Criteria:** Response helps with the content, no maintenance mode trigger

### MT-006: Layer 3 — Ambiguous (Asks Clarification)
**Query:** "I need to make a revision"  
**Expected:** Asks for clarification before proceeding  
**Pass Criteria:** Response asks whether user wants to update the KB/methodology OR work on their own content

### MT-007: Layer 3 — Ambiguous Variant
**Query:** "Something is wrong"  
**Expected:** Asks for clarification  
**Pass Criteria:** Response asks what's wrong — the methodology/KB or something the user is working on

### MT-008: Layer 3 — Ambiguous "Fix an Error"
**Query:** "Fix an error"  
**Expected:** Asks for clarification  
**Pass Criteria:** Response asks whether error is in the methodology or in user's content

---

## CONTEXT ASSESSMENT TESTS

### CA-001: Context Questions Asked
**Query:** "I want to build a GPT for my business" (after Step 1 answered)  
**Expected:** Asks context assessment questions (Step 2)  
**Pass Criteria:** Response asks about who's involved, starting point, and/or project stage

### CA-002: "Who's Involved" Question
**Query:** (During discovery)  
**Expected:** Question about solo vs team vs clients  
**Pass Criteria:** Response asks some form of "Is this just for you, your team, or external clients?"

### CA-003: "Starting Point" Question
**Query:** (During discovery)  
**Expected:** Question about expertise level  
**Pass Criteria:** Response asks about domain expertise — expert, learning, or organizing existing docs

### CA-004: "Project Stage" Question
**Query:** (During discovery)  
**Expected:** Question about prototype vs production  
**Pass Criteria:** Response asks about stage — prototype, functional/evolving, or production-ready

### CA-005: Blended Role Acknowledgment
**Query:** "I'm a founder building for myself and my team, and I'm learning as I go"  
**Expected:** Acknowledges the blend, confirms calibration  
**Pass Criteria:** Response explicitly acknowledges the multi-faceted context and explains how it will calibrate the build

### CA-006: Context Affects Output Recommendation
**Query:** (After stating: solo + learning + prototype)  
**Expected:** Architecture recommendations reflect context  
**Pass Criteria:** Response recommends simpler architecture, mentions room to grow, doesn't over-engineer

### CA-007: Client Context Increases Polish
**Query:** (After stating: building for clients + production-ready)  
**Expected:** Recommendations emphasize polish and documentation  
**Pass Criteria:** Response mentions professional polish, comprehensive documentation, handoff materials

---

## KNOWLEDGE COMPLETENESS TESTS

### KC-001: Completeness Question Asked
**Query:** (During Step 5 - Knowledge Sources)  
**Expected:** Asks about knowledge completeness  
**Pass Criteria:** Response asks whether KB is complete or user plans to expand over time

### KC-002: "Complete" Response — No Lecture
**Query:** "My knowledge base is complete for now"  
**Expected:** Accepts answer, proceeds without lecturing  
**Pass Criteria:** Response acknowledges, mentions freshness protocols, does NOT suggest they need more content

### KC-003: "Starting Lean" Response — Expansion Structure
**Query:** "I'm starting lean and will expand later"  
**Expected:** Acknowledges strategy, promises expansion-friendly structure  
**Pass Criteria:** Response validates the approach, mentions structuring for easy expansion

### KC-004: "Not Sure" Response — Gentle Flagging
**Query:** "I'm not sure if my knowledge base is complete"  
**Expected:** Offers to flag gaps, doesn't block progress  
**Pass Criteria:** Response offers to identify potential gaps during build, makes clear user decides whether to address now or later

### KC-005: No Blocking on Incomplete KB
**Query:** "I only have a few documents but want to start building"  
**Expected:** Proceeds without requiring more content  
**Pass Criteria:** Response accommodates the approach, structures for growth, does NOT require more content before building

### KC-006: Employee with Company Docs — Respect Boundary
**Query:** "I'm using our company's existing documentation, that's what we have"  
**Expected:** Respects the boundary, doesn't push for more  
**Pass Criteria:** Response accepts the knowledge source without suggesting they need additional research

---

## STARTING FROM ZERO TESTS

### SZ-001: No Documents Detection
**Query:** "I don't have any existing documents"  
**Expected:** Offers three methods (Deep Research, Self-Interview, Hybrid)  
**Pass Criteria:** Response presents all three options with brief explanations, doesn't block or require documents

### SZ-002: No Documents — Deep Research Path
**Query:** (After SZ-001) "I'll try the Deep Research approach"  
**Expected:** Provides Deep Research prompt template  
**Pass Criteria:** Response provides complete research prompt template, explains how to use it, sets expectation for return

### SZ-003: No Documents — Self-Interview Path
**Query:** (After SZ-001) "I want to do the Self-Interview"  
**Expected:** Provides Self-Interview prompt template  
**Pass Criteria:** Response provides interview prompt AND transcript conversion prompt, explains 60-90 minute process

### SZ-004: No Documents — Hybrid Path
**Query:** (After SZ-001) "The Hybrid approach sounds good"  
**Expected:** Provides both prompts with workflow guidance  
**Pass Criteria:** Response provides both prompts, explains sequence (research first, then interview), mentions synthesis step

### SZ-005: Deep Research Best-For Explanation
**Query:** "What is Deep Research good for?"  
**Expected:** Explains appropriate use cases  
**Pass Criteria:** Response mentions industry best practices, regulatory/compliance, foundational knowledge; notes it's NOT good for proprietary/company-specific info

### SZ-006: Self-Interview Best-For Explanation
**Query:** "What is the Self-Interview good for?"  
**Expected:** Explains appropriate use cases  
**Pass Criteria:** Response mentions personal processes, decision frameworks, lessons learned, policies/pricing, tacit knowledge

### SZ-007: Continue Without Content
**Query:** "I'll gather content and come back — can we continue with the other stuff?"  
**Expected:** Offers to proceed with system prompt, structure while user gathers content  
**Pass Criteria:** Response confirms approach, offers to continue with other deliverables, sets expectation for content processing on return

---

## PHASED EXPANSION TESTS

### PE-001: MVKB Concept Retrieval
**Query:** "What's the minimum I need to launch?"  
**Expected:** Explains Minimum Viable Knowledge Base  
**Pass Criteria:** Response mentions MVKB, lists core requirements (purpose content, top 10 questions, constraints, error handling)

### PE-002: Four Phases Retrieval
**Query:** "How should I grow my knowledge base over time?"  
**Expected:** Explains four-phase expansion framework  
**Pass Criteria:** Response describes phases (Launch, Fill Gaps, Deepen, Expand) with timing and triggers

### PE-003: Gap Identification Guidance
**Query:** "How do I know what's missing from my knowledge base?"  
**Expected:** Explains gap signals  
**Pass Criteria:** Response lists signals (retrieves wrong info, partial answers, users rephrase, etc.) with corresponding actions

### PE-004: Gap Tracking Template
**Query:** "How should I track gaps I find?"  
**Expected:** Provides gap tracking approach  
**Pass Criteria:** Response provides tracking format or template, mentions monthly review

### PE-005: Expansion vs Depth Decision
**Query:** "Should I add a new section or expand an existing one?"  
**Expected:** Provides decision framework  
**Pass Criteria:** Response explains when to add new sections vs. deepen existing, gives criteria for each

### PE-006: When NOT to Expand
**Query:** "Should I add everything users ask about?"  
**Expected:** Explains when NOT to expand  
**Pass Criteria:** Response mentions one-time questions, out-of-scope requests, highly personalized items as reasons NOT to expand

---

## EDGE CASE TESTS

### E-001: Outside Scope Request
**Query:** "Help me build a custom RAG pipeline with Pinecone"  
**Expected:** Acknowledges limitation, offers relevant help  
**Pass Criteria:** Response explains this is outside scope, offers chunking/metadata guidance that would apply

### E-002: Conflicting Requirements
**Query:** "I want comprehensive responses that are also very brief"  
**Expected:** Surfaces conflict, asks for resolution  
**Pass Criteria:** Response identifies the conflict, presents options

### E-003: Vague Request
**Query:** "Make my GPT better"  
**Expected:** Asks clarifying questions  
**Pass Criteria:** Response asks what specifically needs improvement

### E-004: Missing Information
**Query:** "What's the best way to structure this?" (no context given)  
**Expected:** Asks for context  
**Pass Criteria:** Response asks what they're trying to structure

### E-005: Platform-Specific When Wrong Platform
**Query:** "How do I add conversation starters to my Claude Project?"  
**Expected:** Clarifies that conversation starters are a GPT feature  
**Pass Criteria:** Response explains this is a Custom GPT feature, not Claude Projects

### E-006: Outdated Assumption
**Query:** "I read that chunks should be 300-500 tokens"  
**Expected:** Provides current guidance, acknowledges evolution  
**Pass Criteria:** Response gives current recommendation (600-1000), notes practices evolve

### E-007: Request for Single File Deliverable
**Query:** "Give me everything I need in one document"  
**Expected:** Explains why multiple files are better, or provides combined if simple  
**Pass Criteria:** Response either explains file separation rationale or provides appropriate combined output

### E-008: Complex Multi-Project Cold Start
**Query:** "I need to build 10 related GPTs for my consulting business"  
**Expected:** Initiates discovery, doesn't overwhelm  
**Pass Criteria:** Response starts with manageable discovery questions, doesn't dump entire methodology

---

## REGRESSION TESTS

Run these after any update to ensure core functionality intact:

### REG-001: Discovery Still Works
**Test:** R-002 + B-001 + B-002  
**Pass:** All three pass

### REG-002: Retrieval Still Works
**Test:** R-001, R-006, R-008, R-013  
**Pass:** All four pass

### REG-003: Generation Still Works
**Test:** B-007  
**Pass:** Complete deliverable generated

### REG-004: Maintenance Mode Still Works
**Test:** B-009 + B-010  
**Pass:** Both pass

### REG-005: Edge Cases Still Handled
**Test:** E-001, E-002, E-003  
**Pass:** All three pass

### REG-006: Maintenance Trigger Layering Works
**Test:** MT-001, MT-003, MT-006  
**Pass:** All three pass (clear trigger works, user content doesn't trigger, ambiguous asks)

### REG-007: Context Assessment Works
**Test:** CA-001, CA-005  
**Pass:** Both pass (questions asked, blends acknowledged)

### REG-008: Knowledge Completeness Works
**Test:** KC-001, KC-002, KC-003  
**Pass:** All three pass (question asked, complete respected, lean accommodated)

### REG-009: Hybrid Architecture Works
**Test:** HA-001, HA-002, HA-005  
**Pass:** All three pass (architecture selection, KB retrieval, character limit awareness)

### REG-010: Starting From Zero Works
**Test:** SZ-001, SZ-002, SZ-003  
**Pass:** All three pass (no docs detected, research path works, interview path works)

### REG-011: Phased Expansion Works
**Test:** PE-001, PE-002, PE-003  
**Pass:** All three pass (MVKB explained, phases explained, gap signals explained)

---

## TEST RUN HISTORY

| Date | Version | Tests Run | Passed | Failed | Notes |
|------|---------|-----------|--------|--------|-------|
| 2025-02-09 | 2.0 | — | — | — | GPT Optimization Update: Added HA (5) hybrid architecture tests + REG-009 |
| 2025-01-28 | 1.2 | — | — | — | Added SZ (7), PE (6) tests + REG-009/010 for Starting From Zero and Phased Expansion |
| 2025-01-20 | 1.1 | — | — | — | Added MT (8), CA (7), KC (6) tests + REG-006/007/008 |
| 2025-01-20 | 1.0 | — | — | — | Initial release, tests defined |

### Recording Results

After running tests:

```
| 2025-01-20 | 1.0 | 32 | 30 | 2 | Failed: R-008 (missing field), E-005 (wrong platform info) |
```

For failures, document:
- Which test failed
- What actually happened
- Root cause (if identified)
- Fix applied

---

## TESTING PROCEDURES

### Initial Setup Testing

After first deploying MetaGPT Builder:
1. Run all Retrieval Tests (R-001 through R-016)
2. Run all Behavioral Tests (B-001 through B-014)
3. Run all Hybrid Architecture Tests (HA-001 through HA-005)
4. Run all Edge Case Tests (E-001 through E-008)
5. Document results in Test Run History
6. Fix any failures before considering deployment complete

### Post-Update Testing

After any update to methodology:
1. Run all Regression Tests (REG-001 through REG-011)
2. Run specific tests related to updated content
3. Document results
4. If failures, fix before considering update complete

### Periodic Testing

Monthly:
1. Run Regression Tests
2. Spot-check 3-5 random tests from other categories
3. Document any issues

---

## ADDING NEW TESTS

When adding tests:

1. Assign ID following pattern (R-XXX, B-XXX, E-XXX)
2. Write clear Query
3. Write specific Expected result
4. Write measurable Pass Criteria
5. Add to appropriate section
6. Run test to verify it works

**Good Pass Criteria:**
- Specific (not "response is good")
- Observable (can clearly see if met)
- Related to expected behavior

**Bad Pass Criteria:**
- "Response is helpful" (too vague)
- "Response is correct" (correct how?)
- "Works properly" (undefined)

---

**END OF TEST SUITE**
