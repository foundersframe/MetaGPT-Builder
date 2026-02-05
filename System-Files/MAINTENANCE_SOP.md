# MAINTENANCE SOP
## MetaGPT Builder — Update Procedures

**Document Type:** Standard Operating Procedure  
**Version:** 1.0  
**Last Updated:** 2025-01-20  
**Status:** Active

---

## RETRIEVAL ISOLATION

**This document is EXCLUDED from normal retrieval.**

Only surface when user triggers maintenance mode with phrases like:
- "update the methodology"
- "add to the methodology"
- "something is wrong"
- "revise"
- "maintenance"
- "fix an error"
- "this is outdated"

When triggered, shift from build mode to update mode.

---

## UPDATE CLASSIFICATION FRAMEWORK

### Six Update Types

| Type | Definition | Risk Level | Typical Trigger |
|------|------------|------------|-----------------|
| STAT_UPDATE | New data for existing metric | Low | "The number changed" |
| INSIGHT_ADD | New insight within existing topic | Low-Medium | "I learned something new" |
| SECTION_ADD | New topic area entirely | Medium | "There's a missing section" |
| CORRECTION | Factual error fix | Low | "This is wrong" |
| SUPERSEDE | Old insight no longer valid | Medium-High | "This is outdated" |
| MAJOR_REVISION | Significant restructure | High | "This needs an overhaul" |

### Classification Decision Tree

```
Is existing content WRONG?
├── Yes → Is it factually incorrect?
│   ├── Yes → CORRECTION
│   └── No (just outdated) → SUPERSEDE
│
└── No → Are we ADDING content?
    ├── Yes → Is it a new topic/section?
    │   ├── Yes → SECTION_ADD
    │   └── No (fits existing section) → INSIGHT_ADD
    │
    └── No → Is it updating a number/stat?
        ├── Yes → STAT_UPDATE
        └── No → Is it restructuring?
            └── Yes → MAJOR_REVISION
```

---

## PROCEDURES BY UPDATE TYPE

### STAT_UPDATE

**Risk:** Low  
**Typical time:** 5-10 minutes

**Procedure:**
1. Locate the chunk containing the statistic
2. Update the value
3. Update DATA_FRESHNESS metadata to current date
4. Add changelog entry:
   ```
   | [Date] | [CHUNK_ID] | STAT_UPDATE | Updated [metric] from [old] to [new] | — |
   ```
5. Verify no other chunks reference the old value

**Example:**
"Platform retrieval limits changed from 10 files to 20 files"
→ Find chunk, update number, update freshness, log change

---

### INSIGHT_ADD

**Risk:** Low-Medium  
**Typical time:** 15-30 minutes

**Procedure:**
1. Determine which section the insight belongs in
2. Determine if it's a new subsection or addition to existing
3. Write the new content (600-1000 tokens)
4. Add full metadata block:
   ```
   ---
   CHUNK_ID: [DOC]-[Section].[Subsection]-[Next Number]
   TOPIC: [Match section topic]
   SUBTOPIC: [Specific focus]
   INSIGHT_TYPE: [Appropriate type]
   RELEVANCE: [Who needs this]
   APPLICATION: [What phase]
   CONFIDENCE: [Level]
   DATA_FRESHNESS: [Current date or evergreen]
   KEYWORDS: [Relevant terms]
   ---
   ```
5. Apply boundary overlap if needed (connect to adjacent content)
6. Update Table of Contents if new subsection
7. Add changelog entry:
   ```
   | [Date] | [CHUNK_ID] | INSIGHT_ADD | Added [description] to Section [X] | — |
   ```

**Example:**
"New technique for handling conversation starters in GPTs"
→ Add to Section 12 (Implementation), create chunk, metadata, log

---

### SECTION_ADD

**Risk:** Medium  
**Typical time:** 1-2 hours

**Procedure:**
1. Determine where new section fits in document structure
2. Assign section number (may require renumbering)
3. Plan subsections (aim for 3-6 chunks)
4. Write all content with proper chunking
5. Add metadata to each chunk
6. Apply boundary overlap at section boundaries
7. Update Table of Contents
8. Update any cross-references in other sections
9. Add changelog entry:
   ```
   | [Date] | — | SECTION_ADD | Added Section [X]: [Title] | Updated TOC |
   ```
10. Consider if new section affects any lens documents (for multi-project users)

**Example:**
"Need a section on voice/audio GPT considerations"
→ Plan section, write chunks, integrate into structure, update TOC

---

### CORRECTION

**Risk:** Low  
**Typical time:** 5-15 minutes

**Procedure:**
1. Locate the incorrect content
2. Verify what the correct information is
3. Make the correction
4. Update DATA_FRESHNESS if factual content
5. Add changelog entry with explanation:
   ```
   | [Date] | [CHUNK_ID] | CORRECTION | Fixed: [what was wrong] → [what's correct] | — |
   ```
6. Check if error propagated to other chunks
7. If error was significant, consider adding a note about what was wrong (helps others who may have learned the incorrect version)

**Example:**
"Custom GPTs actually support 20 files, not 10"
→ Find all references, correct them, log with explanation

---

### SUPERSEDE

**Risk:** Medium-High  
**Typical time:** 30-60 minutes

**Procedure:**
1. Locate the outdated chunk
2. Determine why it's outdated (platform change, better practice emerged, etc.)
3. Create new chunk with current information:
   - New CHUNK_ID
   - Full metadata
   - Complete content
4. Update old chunk:
   - Add at top: `**SUPERSEDED:** See [NEW_CHUNK_ID] for current guidance.`
   - Keep old content (for reference)
   - Update metadata: add `SUPERSEDED_BY: [NEW_CHUNK_ID]`
5. Update any chunks that referenced the old content
6. Add changelog entry:
   ```
   | [Date] | [OLD_ID] | SUPERSEDE | Replaced by [NEW_ID]: [reason] | [List affected chunks] |
   ```

**Why keep old content:**
- Users may have learned the old way
- Provides context for why things changed
- Helps troubleshoot if someone is following outdated guidance

**Example:**
"The recommended chunk size changed from 500-800 to 600-1000 tokens"
→ Create new chunk with new guidance, mark old as superseded, update references

---

### MAJOR_REVISION

**Risk:** High  
**Typical time:** 2-4 hours

**Procedure:**

**Before starting:**
1. Create archive of current version:
   - Copy entire document
   - Save as `[FILENAME]_archive_[DATE].md`
   - Store in Archives folder
2. Document scope of revision:
   - What's changing
   - Why it's changing
   - What's staying the same

**During revision:**
3. Make structural changes
4. Renumber sections/chunks as needed
5. Rewrite affected content
6. Update all metadata
7. Rebuild Table of Contents
8. Update all internal cross-references

**After revision:**
9. Run full test suite (all retrieval tests)
10. Verify no broken references
11. Add comprehensive changelog entry:
    ```
    | [Date] | — | MAJOR_REVISION | [Summary of changes] | See detailed notes below |
    
    ### Major Revision Notes — [Date]
    **Reason:** [Why revision was needed]
    **Scope:** [What changed]
    **Breaking changes:** [What users need to know]
    **Migration:** [Any steps users should take]
    ```
12. Increment version number (e.g., 1.0 → 2.0)

**Example:**
"Restructuring to add multi-modal GPT support throughout"
→ Archive, plan scope, revise systematically, test, document thoroughly

---

## DATA FRESHNESS MANAGEMENT

### Freshness Thresholds

| Content Type | Review Trigger | Action |
|--------------|----------------|--------|
| Platform features | 6 months | Verify current, update or flag |
| Best practices | 12 months | Review for continued relevance |
| Tool capabilities | 6 months | Check for changes |
| Core concepts | Never | Evergreen — no review needed |
| Examples | 12 months | Verify still representative |

### Freshness Review Process

**Monthly scan:**
- Check DATA_FRESHNESS on time-sensitive chunks
- Flag any approaching thresholds
- Prioritize verification for frequently-retrieved chunks

**Quarterly review:**
- Systematic review of all non-evergreen content
- Update DATA_FRESHNESS on verified content
- Create update tasks for stale content

### Freshness Metadata Update

When verifying content is still current:
```
Before: DATA_FRESHNESS: 2024-07
After:  DATA_FRESHNESS: 2025-01

Changelog: | 2025-01-20 | [CHUNK_ID] | STAT_UPDATE | Verified current, updated freshness | — |
```

---

## CHANGELOG MANAGEMENT

### Changelog Format

```markdown
## CHANGELOG

| Date | Chunk ID | Type | Description | Linked Changes |
|------|----------|------|-------------|----------------|
| 2025-01-20 | MMB-4.2-003 | STAT_UPDATE | Updated retrieval limit | — |
| 2025-01-18 | MMB-6.1-001 | INSIGHT_ADD | Added boundary overlap technique | — |
| 2025-01-15 | — | SECTION_ADD | Added Section 13: Voice GPTs | Updated TOC |
```

### Changelog Location

- **Primary:** Top of each document, after title/metadata
- **Detailed notes:** Below table for MAJOR_REVISION entries

### Changelog Entry Requirements

Every entry must include:
- **Date:** YYYY-MM-DD format
- **Chunk ID:** Specific chunk, or "—" for structural changes
- **Type:** From classification framework
- **Description:** Specific, brief description of change
- **Linked Changes:** Other affected chunks/documents, or "—"

---

## VERSION CONTROL

### Version Numbering

Format: MAJOR.MINOR

- **MAJOR:** Increment for MAJOR_REVISION (structural changes, breaking changes)
- **MINOR:** Increment for significant SECTION_ADD or multiple related updates

Examples:
- 1.0 → 1.1: Added new section
- 1.1 → 1.2: Multiple insight additions
- 1.2 → 2.0: Major restructure

### Version in Documents

Update in document header:
```markdown
**Version:** 2.0
**Last Updated:** 2025-01-20
```

---

## ARCHIVE PROCEDURES

### When to Archive

- Before any MAJOR_REVISION
- Quarterly (scheduled preservation)
- Before experimental changes

### Archive Process

1. Copy complete document
2. Name: `[FILENAME]_archive_[YYYY-MM-DD].md`
3. Store in: `Archives/` folder (outside active project)
4. Do NOT upload archives to Claude Project KB

### Archive Retention

- Keep last 4 quarterly archives (1 year)
- Keep all pre-MAJOR_REVISION archives
- Delete older archives annually (keep one per year for history)

---

## QUALITY CHECKLIST

Before finalizing any update:

### Content Quality
- [ ] Information is accurate
- [ ] Writing is clear and concise
- [ ] Chunk size is appropriate (600-1000 tokens)
- [ ] Examples are relevant and helpful

### Structural Quality
- [ ] Metadata is complete and accurate
- [ ] CHUNK_ID follows convention
- [ ] Boundary overlap applied where needed
- [ ] Table of Contents updated (if applicable)

### Documentation Quality
- [ ] Changelog entry added
- [ ] Version updated (if applicable)
- [ ] DATA_FRESHNESS updated
- [ ] Cross-references checked

### Retrieval Quality
- [ ] Keywords support findability
- [ ] TOPIC/SUBTOPIC are consistent
- [ ] RELEVANCE and APPLICATION are accurate

---

## EMERGENCY PROCEDURES

### Discovered Critical Error

If methodology contains guidance that could cause significant problems:

1. **Immediate:** Add warning to affected chunk
   ```
   **⚠️ WARNING:** [Brief description of issue]. See [CHUNK_ID] for corrected guidance.
   ```
2. **Fast follow:** Create corrected chunk
3. **Document:** Changelog with explanation
4. **Notify:** If users may have been affected, note in prominent location

### Corrupted or Lost Content

If content is accidentally deleted or corrupted:

1. Check Archives folder for recent backup
2. Restore from archive
3. Re-apply any changes made since archive date
4. Document incident in changelog

### Conflicting Updates

If two updates conflict:

1. Pause both updates
2. Identify the conflict
3. Determine correct resolution
4. Implement single coherent update
5. Document decision in changelog

---

## MAINTENANCE SCHEDULE

### Ongoing (As Needed)
- CORRECTION — Immediately when found
- STAT_UPDATE — When new data available

### Monthly
- Freshness scan
- Review any flagged content
- Process accumulated INSIGHT_ADD requests

### Quarterly
- Full freshness review
- Archive current version
- Review structure for needed improvements
- Process SECTION_ADD requests

### Annually
- Comprehensive methodology review
- Consider MAJOR_REVISION needs
- Clean up archives
- Update examples for currency

---

**END OF MAINTENANCE SOP**
