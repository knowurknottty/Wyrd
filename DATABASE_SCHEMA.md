# WYRD DATABASE SCHEMA
## Version 1.0 - Expansion Protocol

**Created:** 2026-03-06  
**Purpose:** Structured etymological knowledge base for linguistic liberation

---

## CORE TABLES

### 1. WORD_ENTRIES (Primary)
```
entry_id: UNIQUE ID
word: string (the term)
language: string (source language)
pronunciation: string (IPA or guide)
word_type: enum (noun, verb, adjective, concept, mantra, mudra)
status: enum (draft, validated, published, archived)
confidence: enum (high, medium, speculative)
created_at: timestamp
updated_at: timestamp
word_count: integer (for tracking)
```

### 2. ETYMOLOGY_CHAIN
```
entry_id: FK to WORD_ENTRIES
step_order: integer (1, 2, 3... chronological)
form: string (the word form at this stage)
language: string
period: string (century or era)
meaning: string (what it meant then)
phonetic_shift: string (optional sound changes)
source_attribution: string (dictionary, scholar, text)
```

### 3. ROOT_ANALYSIS
```
entry_id: FK
root_type: enum (PIE, Sanskrit, Latin, Greek, Proto-Germanic, etc.)
root_form: string (the reconstructed root)
root_meaning: string (core sense)
root_phonetics: string (IPA)
cognates: array[string] (related words across languages)
semantic_field: array[string] (conceptual clusters)
```

### 4. LIBERATION_ANGLE
```
entry_id: FK
surface_reading: text (common modern meaning)
hidden_structure: text (what the etymology reveals)
inversion_insight: text (how this liberates)
power_dynamic: text (who benefits from the surface reading)
reclaiming_strategy: text (how to use this knowledge)
```

### 5. CROSS_REFERENCES
```
entry_id: FK
related_entry_id: FK
relationship_type: enum (cognate, opposite, derived_from, antonym, synonym)
notes: text
```

### 6. SOURCES
```
source_id: UNIQUE
entry_id: FK
source_type: enum (academic, traditional, textual, folk)
author: string
title: string
year: integer
url: string
reliability: enum (peer_reviewed, authoritative, contested, speculative)
```

---

## WORKFLOW: EXPLORE → RESEARCH → EXPAND → VALIDATE

### PHASE 1: EXPLORE (2 min per word)
- Identify target word
- Note surface meaning
- Initial curiosity: What does this word hide?
- Tag with word_type and priority

### PHASE 2: RESEARCH (5 min per word)
- Query etymological dictionaries (OED, Watkins, etymonline)
- Trace to earliest attested form
- Identify PIE/Sanskrit/Proto root
- Map phonetic shifts
- Document cognates

### PHASE 3: EXPAND (5 min per word)
- Write root analysis
- Develop liberation angle
- Connect to power structures
- Draft reclaiming strategy
- Cross-reference related terms

### PHASE 4: VALIDATE (3 min per word)
- Verify sources
- Check confidence level
- Review for accuracy
- Flag speculative claims
- Mark status

**Target rate:** 15 minutes per entry = 4 entries per hour  
**Sprint target:** 30 minutes = 2 high-quality entries minimum, aim for 3-4 rapid entries

---

## OUTPUT FORMAT

Each entry produces:
1. **Entry Block** (markdown)
2. **Database records** (JSON/structured)
3. **Cross-reference links**
4. **Word count tracking**

---

## SPRINT METRICS

| Sprint | Words Added | Time | Rate |
|--------|-------------|------|------|
| 1 | TBD | 30 min | TBD |

