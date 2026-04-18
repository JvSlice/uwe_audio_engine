# UWE Audio Engine — Data Model

## Purpose

Defines the core data structures of the system.

These represent how information flows through the pipeline.

---

## Core Entities

---

## Job

Represents a single processing request.

Fields:
- job_id
- status
- current_stage
- created_at
- updated_at
- error_message

---

## SourceDocument

Original input.

Fields:
- source_id
- job_id
- source_type
- raw_content
- metadata

---

## ProcessedDocument

Cleaned version of input.

Fields:
- processed_id
- job_id
- cleaned_text
- structure_info

---

## ScriptDocument

Final text used for audio.

Fields:
- script_id
- job_id
- script_text
- mode (exact | podcast)

---

## Chapter

Represents content sections.

Fields:
- chapter_id
- job_id
- title
- start_index
- end_index

---

## AudioSegment

Individual generated audio chunk.

Fields:
- segment_id
- job_id
- text_chunk
- file_path
- duration

---

## AudioOutput

Final merged audio.

Fields:
- output_id
- job_id
- file_path
- duration
- format

---

## ProcessingEvent

Tracks job progress.

Fields:
- event_id
- job_id
- stage
- message
- timestamp

---

## Relationships

- Job → SourceDocument (1:1)
- Job → ProcessedDocument (1:1)
- Job → ScriptDocument (1:1)
- Job → Chapters (1:N)
- Job → AudioSegments (1:N)
- Job → AudioOutput (1:1)
- Job → ProcessingEvents (1:N)

---

## Rules

### 1. No overwriting
Each stage must be stored separately.

---

### 2. Traceability
Must be able to trace:
raw → cleaned → script → audio

---

### 3. Debuggable
All stages must be inspectable.

---

### 4. Expandable
Models should allow:
- new fields
- new relationships

---

## Storage Strategy (Initial)

- local filesystem
- simple file paths
- metadata stored alongside files

---

## Future Evolution

- database integration
- indexing
- search
- multi-user support
