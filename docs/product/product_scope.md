# UWE Audio Engine — Product Scope

## Purpose

UWE Audio Engine is a tool that converts written material into high-quality, listenable audio.

The goal is to allow users to take various forms of content and turn them into:
- faithful spoken audio
- or optimized, podcast-style audio

This is a **real product build**, not a demo.

---

## Core Capabilities

The system must support:

### Input Types (initial + planned)
- pasted text (v1)
- markdown (v1)
- plain text (v1)
- PDF documents (planned)
- web links (planned)

---

### Output Modes

#### 1. Exact Read Mode
- reads content faithfully
- preserves structure where possible
- minimal transformation

#### 2. Podcast Mode
- rewrites content for listening
- improves flow and clarity
- removes visual-only artifacts
- preserves meaning and key data

---

### Processing Features

- text cleanup and normalization
- structure detection
- chapter generation
- content chunking for audio
- optional rewriting
- audio generation
- audio merging into final output

---

### Output

- playable audio
- downloadable audio file
- optional chapter metadata (later)
- optional transcript/script (later)

---

## Design Principles

### 1. Simple First
Start with a working baseline before adding complexity.

### 2. Modular System
Each stage of processing should be isolated:
- ingestion
- cleanup
- rewrite
- chaptering
- TTS
- assembly

---

### 3. No Data Loss
Never overwrite:
- original input
- cleaned content
- rewritten content

Each stage must be preserved.

---

### 4. Job-Based Processing
All processing runs as a job:
- trackable
- restartable (later)
- debuggable

---

### 5. Hackable Build
All systems should be:
- easy to modify
- easy to extend
- clearly documented

---

### 6. Privacy First
User content should:
- not be unnecessarily stored
- not be exposed externally
- be handled safely

---

## Non-Goals (for now)

- user accounts
- billing systems
- multi-user management
- cloud scaling
- mobile apps

These can be added later.

---

## Success Criteria (v1)

The product is successful when:

- user can paste text
- choose Exact Read Mode
- generate audio
- play or download the result

No additional features are required for v1 success.

---

## Future Direction

- PDF ingestion
- web link ingestion
- improved podcast rewrite styles
- voice selection expansion
- chapter navigation
- UWE app integration

---

## Integration Goal

This tool must be built so it can:
- run standalone
- or be integrated into the Ultimate Window Engineer Tool (UWE)

No hard coupling should exist in early builds.
