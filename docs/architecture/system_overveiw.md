# UWE Audio Engine — System Overview

## Architecture Style

The system is built as a **modular monolith backend with a separate frontend**.

This allows:
- fast development
- easier debugging
- clean separation of concerns
- future scalability

---

## High-Level Components

### 1. Frontend Application
Responsible for:
- user input
- mode selection
- job submission
- status display
- audio playback/download

---

### 2. Backend Service
Responsible for:
- processing pipeline
- job orchestration
- content transformation
- audio generation
- storage
- API handling

---

## Core Backend Modules

### Ingestion Module
- accepts raw input
- normalizes source format

---

### Extraction Module
- cleans raw content
- prepares structured text

---

### Processing Pipeline
- coordinates all steps
- routes based on mode
- prepares data for TTS

---

### Rewrite Module
(Podcast Mode only)
- converts text to spoken-style script

---

### Chaptering Module
- detects logical sections
- creates chapters

---

### TTS Module
- converts text into audio chunks
- interacts with external TTS providers

---

### Audio Assembly Module
- merges chunks into final file
- prepares output format

---

### Storage Module
- stores all intermediate and final data
- supports debugging and traceability

---

### Job Orchestration Module
- tracks job state
- manages processing steps
- logs events

---

### API Layer
- exposes backend functionality
- connects frontend to backend

---

## Processing Flow

1. User submits content
2. Job is created
3. Content is normalized
4. Text is cleaned
5. Mode selected:
   - Exact Read
   - Podcast Mode
6. Chapters generated
7. Text chunked
8. Audio generated per chunk
9. Audio merged
10. Output stored
11. Job marked complete

---

## Data Separation Strategy

Each stage must be stored separately:

- Raw Input
- Cleaned Text
- Rewritten Script (if used)
- Audio Chunks
- Final Audio Output

---

## Key Design Rules

### 1. No Overwrites
Each stage must be preserved.

---

### 2. Isolated Modules
Each module should:
- do one job
- be replaceable later

---

### 3. Provider Abstraction
External services must be abstracted:
- TTS provider
- rewrite provider
- extraction provider

---

### 4. Observable Pipeline
System must be:
- debuggable
- traceable
- transparent

---

## Deployment Strategy (Initial)

- local development first
- local storage
- no cloud dependency required

---

## Future Evolution

- background workers
- distributed processing
- cloud storage
- API authentication
- scaling services

---

## Integration Direction

The backend should be:
- standalone
- API-driven
- compatible with embedding into UWE later
