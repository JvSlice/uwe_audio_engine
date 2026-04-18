# UWE Audio Engine — Phase Plan

## Build Philosophy

We build in layers:

1. Working baseline
2. Improve stability
3. Expand features
4. Harden system
5. Prepare for integration

---

## Phase 0 — Planning Lock

Goal:
- define system clearly before coding

Deliverables:
- architecture docs
- folder structure
- API design
- UX layout
- timeline

Exit:
- full system flow understood

---

## Phase 1 — Exact Read Baseline

Goal:
- working audio generation from pasted text

Scope:
- text input
- cleanup
- chunking
- TTS generation
- audio merge
- playback/download

Exit:
- user can paste text and get audio

---

## Phase 2 — Processing Improvements

Goal:
- improve reliability and quality

Scope:
- better cleanup
- better structure handling
- improved chunking
- error handling
- logging improvements

Exit:
- long inputs work consistently

---

## Phase 3 — Podcast Mode v1

Goal:
- add rewrite capability

Scope:
- rewrite pipeline
- script generation
- mode switching
- improved listening flow

Exit:
- same input supports two modes

---

## Phase 4 — PDF Input

Goal:
- support document ingestion

Scope:
- PDF upload
- text extraction
- cleanup integration

Exit:
- PDF can generate audio

---

## Phase 5 — Web Link Input

Goal:
- support URL ingestion

Scope:
- fetch content
- extract readable text
- cleanup integration

Exit:
- article links convert to audio

---

## Phase 6 — System Hardening

Goal:
- make system reliable

Scope:
- retries
- failure handling
- storage rules
- logging
- config cleanup

Exit:
- system is stable and predictable

---

## Phase 7 — Integration Readiness

Goal:
- prepare for UWE integration

Scope:
- API stabilization
- modular frontend structure
- compatibility planning

Exit:
- system can embed into UWE

---

## Priority Order (Critical)

1. Exact Read baseline
2. Stability improvements
3. Podcast Mode
4. PDF input
5. Web links
6. Hardening
7. Integration

---

## Key Rule

Do not move forward until:
- current phase is stable
- outputs are predictable
- system is understandable
