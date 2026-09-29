# Digital Archaeologist — Full Build Prompt (Antigravity)

One single prompt that builds the entire app end-to-end. Paste it into Antigravity's agent after you've run the Stitch design prompt and have the reference screens open. The agent should scaffold the project, then create every file described below, in order, in one session.

---

```text
Build "Digital Archaeologist" from scratch: a single-page web app that accepts a collection of digital artifacts—source files, markdown files, configuration files, notes, screenshots, metadata, and archived files—and uses AI to reconstruct the history and evolution of the project.

One-line pitch:

"Drop in the digital remains. Reconstruct what happened."

The product is NOT a code-review tool, AI coding assistant, repository manager, or chatbot.

The core experience is digital archaeology: the user provides a messy collection of project artifacts, and the application identifies artifacts, reconstructs chronology, detects relationships and turning points, identifies gaps in the historical record, and produces an evidence-backed project history.

Problem: old project folders are often messy and difficult to understand. Files such as `final.py`, `final_v2.py`, `final_REAL.py`, old READMEs, screenshots, configuration files, and notes may contain fragments of a project's history, but the chronology and reasoning behind changes are lost.

Goal: turn an unstructured digital artifact collection into an understandable archaeological reconstruction showing:
- what artifacts exist
- when they appeared or changed
- how artifacts relate to each other
- what changed over time
- important turning points
- abandoned or replaced ideas
- missing periods in the record
- what can be directly observed
- what can reasonably be inferred
- what remains unknown

Audience: students, developers, hackathon participants, researchers, educators, archivists, and anyone who discovers an old project folder and wants to understand its history.

Non-goals:
- no authentication/accounts
- no persistence/history/database
- no GitHub integration
- no automatic repository cloning
- no collaboration features
- no continuous background indexing
- no automatic modification of user files
- no pretending that inferred events are historical facts
- no generic AI chat interface
- no code-review scoring system

Tech stack:
- IDE/agent: Antigravity (you)
- Framework: Next.js 16, App Router
- UI: React 19 + TypeScript
- Styling: Tailwind CSS v4
- AI: Google Gemini via the official `@google/genai` SDK, model "gemini-3.5-flash-lite"
- Hosting target: Vercel (keep it deployable, no Vercel-specific work needed now)
- Secrets: the Gemini API key must live in `.env.local` and be read ONLY on the server — it must never reach the browser bundle.

---

VISUAL DIRECTION:

Follow the Stitch design reference I'm showing you.

The visual identity is:

"ARCHAEOLOGICAL FIELD STATION × DIGITAL FORENSICS × MUSEUM ARCHIVE"

This must be visually distinct from the previous Code Roaster interface.

Do NOT reuse the Code Roaster:
- centered workstation card
- 55/45 editor/report split
- conventional top control bar
- bottom status bar
- off-white SaaS dashboard
- architectural blueprint aesthetic
- Code Roaster burnt-orange-on-paper palette
- code editor as the primary visual element
- roast/report card composition

The primary interface should be a full-window archaeological excavation environment.

Think:
- excavation table
- museum specimen catalog
- forensic evidence wall
- historical research archive
- field notebook
- digital evidence mapping
- annotated research documents

The main screen should be an open excavation canvas rather than a conventional dashboard.

Color tokens:
- excavation background: #1C1B18
- deep surface: #24231F
- artifact paper: #E8E0D0
- aged paper highlight: #D7C7A9
- faded ink: #35342F
- archival text: #B9B09F
- excavation orange: #C56A35
- evidence red: #A84235
- verified green: #71866A
- uncertain yellow: #C0A45B
- historical blue: #657B86
- line/grid: #4A4841

Typography:
- display/editorial font: IBM Plex Serif
- interface font: IBM Plex Sans
- technical metadata: IBM Plex Mono

Use IBM Plex Serif for major historical titles and discoveries.

Use IBM Plex Sans for navigation, controls, and interface text.

Use IBM Plex Mono for:
- filenames
- paths
- timestamps
- hashes
- artifact IDs
- coordinates
- technical metadata
- status labels

The typography should feel like an archival research publication rather than a developer dashboard.

Create a subtle dark excavation-grid background using low-opacity 1px linear gradients.

Use thin coordinate/ruler markings around the excavation canvas.

Use very restrained texture and annotation details.

Avoid:
- gradients
- glassmorphism
- excessive rounded corners
- floating AI chat bubbles
- purple AI aesthetics
- generic SaaS cards
- giant hero sections
- excessive shadows
- excessive decorative illustrations

Use mostly sharp or minimally rounded geometry.

---

CORE USER FLOW:

1. User imports or pastes a collection of digital artifacts.
2. The application catalogs each artifact.
3. The application extracts basic metadata.
4. The user starts an excavation.
5. The server sends the artifact metadata/content to Gemini with a structured archaeological-analysis prompt and fixed JSON response schema.
6. Gemini identifies:
   - artifact relationships
   - probable chronology
   - project phases
   - turning points
   - changes
   - abandoned ideas
   - evidence gaps
   - observations
   - inferences
   - unknowns
7. The UI displays the artifacts across an interactive excavation canvas.
8. Related artifacts are visually connected.
9. Important discoveries appear as evidence annotations.
10. The user can inspect artifacts, relationships, timeline events, comparisons, and the final reconstructed project history.

The application must clearly distinguish:

OBSERVED
Directly supported by artifact content or metadata.

INFERRED
A conclusion reconstructed from multiple pieces of evidence.

UNKNOWN
Something that cannot be established from the available evidence.

Never present an inference as a confirmed historical fact.

---

SUPPORTED ARTIFACT TYPES:

Support these initial artifact categories:

- source code
- markdown/documentation
- plain text
- JSON/configuration
- CSV/data
- screenshots/images
- log files
- package/dependency manifests
- archive metadata
- unknown files

For the first implementation, artifacts can be represented through imported text and metadata.

Do not attempt to build a full desktop filesystem crawler.

The initial product should work entirely within the browser.

---

FEATURES:

Artifact import:
- drag-and-drop artifact zone
- multi-file selection
- artifact list
- file type detection
- filename
- extension
- size
- modified timestamp when available
- artifact ID
- import status

Excavation:
- "EXCAVATE" primary action
- analysis progress
- artifact indexing
- relationship reconstruction
- chronology reconstruction
- discovery detection

Evidence:
- observed evidence
- inferred evidence
- unknown/missing evidence
- evidence references
- artifact relationships

Timeline:
- reconstructed chronological events
- event confidence
- supporting artifacts
- project phases
- gaps in the record

Comparison:
- compare two artifacts
- show metadata differences
- show content-level changes where applicable
- explain likely historical significance

Evidence Wall:
- visual arrangement of artifacts and discoveries
- connecting evidence lines
- investigation annotations

Report:
- project history
- timeline
- turning points
- abandoned ideas
- missing evidence
- final archaeological interpretation

Limits:
- maximum 50 artifacts per excavation
- maximum 10,000 characters per text artifact
- maximum 100,000 total characters sent to the AI
- enforce limits client-side and server-side

---

ARCHITECTURE:

Stateless, no database, no auth.

ArtifactImporter
→ ExcavationWorkspace
→ lib/api.ts
→ POST /api/excavate
→ lib/gemini.ts
→ lib/prompt.ts
→ lib/schema.ts
→ Gemini API
→ ExcavationResult JSON
→ ExcavationCanvas / Timeline / EvidenceWall / ArchaeologicalReport

---

NOW BUILD THESE FILES EXACTLY AS SPECIFIED:

=== 1. Scaffold ===

Create a new Next.js 16 App Router project, React 19, TypeScript, Tailwind v4, using `@google/genai`.

Set up fonts in app/layout.tsx per the visual direction.

Use:
- IBM Plex Serif
- IBM Plex Sans
- IBM Plex Mono

Map all three into Tailwind v4 through `@theme` / `@theme inline` in globals.css.

Root layout metadata:
title = `${APP.name} — Digital Archaeology`
description = APP.tagline

<html> gets font variables + `h-full antialiased`.

<body> gets `min-h-full`.

app/page.tsx should render the full-page `<ExcavationWorkspace />`.

Do NOT center the entire application inside a 1360px card.

The application should occupy the full viewport.

Add .gitignore excluding:
- node_modules
- .next
- .env.local

Create `.env.example` with:

GEMINI_API_KEY=

and a comment linking to:

https://aistudio.google.com/apikey

Do NOT create or write into `.env.local` yourself.

---

=== 2. config/app.config.ts ===

The single source of truth imported by both browser and server.

Never put secrets here.

Export:

APP = {
  name: "Digital Archaeologist",
  version: "v1",
  tagline: "Drop in the digital remains. Reconstruct what happened."
}

AI = {
  model: "gemini-3.5-flash-lite",
  modelLabel: "Gemini 3.5 Flash-Lite",
  maxAttempts: 3
}

ANALYSIS_MODES = [
  {
    id: "overview",
    label: "Overview",
    description: "Fast reconstruction of the project's broad history."
  },
  {
    id: "deep",
    label: "Deep Excavation",
    description: "Detailed artifact relationships and historical reconstruction."
  },
  {
    id: "forensic",
    label: "Forensic",
    description: "Maximum evidence tracing and uncertainty analysis."
  }
] as const

ARTIFACT_TYPES = [
  "SOURCE",
  "DOCUMENT",
  "CONFIG",
  "DATA",
  "IMAGE",
  "LOG",
  "DEPENDENCY",
  "ARCHIVE",
  "UNKNOWN"
] as const

EVIDENCE_STATUS = [
  "OBSERVED",
  "INFERRED",
  "UNKNOWN"
] as const

ARTIFACT_STATUS = [
  "DISCOVERED",
  "CONNECTED",
  "ISOLATED",
  "MISSING"
] as const

LIMITS = {
  maxArtifacts: 50,
  maxArtifactLength: 10_000,
  maxTotalCharacters: 100_000
}

DEFAULTS = {
  analysisMode: "deep"
} as const

SAMPLE_ARTIFACTS should contain a small fictional project with artifacts such as:

- README_old.md
- notes.txt
- final.py
- final_v2.py
- final_REAL.py
- config.json

The sample should demonstrate a project evolving through multiple stages.

---

=== 3. types/archaeology.ts ===

Derive types FROM the config arrays.

Create:

ArtifactType
AnalysisMode
EvidenceStatus
ArtifactStatus

Then define:

Artifact {
  id: string
  name: string
  type: ArtifactType
  extension: string
  size: number
  modifiedAt?: string
  path?: string
  content?: string
  status: ArtifactStatus
}

EvidenceReference {
  artifactId: string
  reason: string
}

Discovery {
  id: string
  title: string
  description: string
  status: EvidenceStatus
  confidence: number
  evidence: EvidenceReference[]
}

TimelineEvent {
  id: string
  date: string
  title: string
  description: string
  status: EvidenceStatus
  confidence: number
  artifactIds: string[]
}

ArtifactRelationship {
  sourceId: string
  targetId: string
  relationship:
    | "MODIFIED"
    | "REPLACED"
    | "REFERENCED"
    | "DUPLICATED"
    | "DERIVED"
    | "UNKNOWN"
  explanation: string
  status: EvidenceStatus
}

ProjectPhase {
  id: string
  title: string
  dateRange: string
  description: string
  artifactIds: string[]
}

MissingEvidence {
  id: string
  period: string
  knownBefore: string
  knownAfter: string
  explanation: string
}

ArchaeologicalReport {
  projectTitle: string
  summary: string
  timeline: TimelineEvent[]
  discoveries: Discovery[]
  relationships: ArtifactRelationship[]
  phases: ProjectPhase[]
  missingEvidence: MissingEvidence[]
  turningPoints: string[]
  abandonedIdeas: string[]
  confidenceSummary: string
}

ExcavationRequest {
  artifacts: Artifact[]
  analysisMode: AnalysisMode
}

ExcavationResult {
  report: ArchaeologicalReport
}

ExcavationState =
  | "empty"
  | "loading"
  | "results"
  | "error"

---

=== 4. lib/prompt.ts ===

Build the archaeological AI personality.

Export:

ARCHAEOLOGIST_SYSTEM_INSTRUCTION

The instruction must establish:

"You are a Digital Archaeologist. Your job is to reconstruct the history of a digital project from a collection of artifacts."

Personality:
- analytical
- curious
- evidence-driven
- concise
- historically cautious
- clear
- never sensational
- never invents missing information

The AI should behave like a forensic archivist examining evidence.

Critical rules:

1. OBSERVED means directly supported by artifact metadata or content.
2. INFERRED means a conclusion supported by multiple pieces of evidence.
3. UNKNOWN means the available evidence is insufficient.

Never convert UNKNOWN into an invented narrative.

Never claim that a developer "intended" something unless the artifacts explicitly establish intent.

Never invent dates.

Never invent files.

Never invent relationships.

Never fabricate evidence.

When dates are unavailable, explicitly state that chronology is uncertain.

When multiple interpretations are possible, preserve the uncertainty.

Analyze:
- chronology
- artifact relationships
- project phases
- architecture changes
- feature additions
- removed functionality
- renamed files
- duplicated artifacts
- abandoned ideas
- documentation changes
- dependency changes
- major turning points
- missing periods

The AI should prefer evidence-backed statements such as:

"Observed: `final_REAL.py` has a later modification timestamp than `final.py`."

rather than unsupported claims such as:

"`final.py` was abandoned because it was broken."

If an inference is useful, mark it:

"Inferred: the later artifact likely represents a replacement implementation because it introduces the same module with a substantially different structure."

The AI must return valid JSON conforming exactly to the requested schema.

Export:

buildUserPrompt({ artifacts, analysisMode })

The prompt should include:
- analysis mode
- artifact metadata
- artifact content
- artifact IDs
- paths
- timestamps
- file types

Use clear delimiters around each artifact.

---

=== 5. lib/schema.ts ===

Using `Type` / `Schema` from `@google/genai`, export:

excavationResponseSchema

The schema must represent:

{
  report: {
    projectTitle: string,
    summary: string,
    timeline: [],
    discoveries: [],
    relationships: [],
    phases: [],
    missingEvidence: [],
    turningPoints: [],
    abandonedIdeas: [],
    confidenceSummary: string
  }
}

Timeline event fields:

- id
- date
- title
- description
- status
- confidence
- artifactIds

Discovery fields:

- id
- title
- description
- status
- confidence
- evidence

Relationship fields:

- sourceId
- targetId
- relationship
- explanation
- status

Phase fields:

- id
- title
- dateRange
- description
- artifactIds

Missing evidence fields:

- id
- period
- knownBefore
- knownAfter
- explanation

Use enums for:
- OBSERVED
- INFERRED
- UNKNOWN

No unnecessary properties.

---

=== 6. lib/gemini.ts ===

Server-only.

Never import this module client-side.

Export:

analyzeArtifacts(
  request: ExcavationRequest
): Promise<ExcavationResult>

Read:

process.env.GEMINI_API_KEY

Throw:

"GEMINI_API_KEY is missing. Copy .env.example to .env.local, add your key, and restart the server."

Create:

new GoogleGenAI({ apiKey })

Call:

ai.models.generateContent

using:
- model: AI.model
- contents: buildUserPrompt(request)
- systemInstruction: ARCHAEOLOGIST_SYSTEM_INSTRUCTION
- responseMimeType: "application/json"
- responseSchema: excavationResponseSchema

Retry:
- ApiError status 503
- maximum AI.maxAttempts
- increasing backoff

Create a friendlyErrorMessage helper mapping:

400
403
404
429
503
default

to actionable messages.

Parse response.text as JSON.

Throw clear errors on:
- empty response
- invalid JSON
- missing report

Return defensive fallbacks so the UI never crashes on partial answers.

---

=== 7. scripts/check-api.ts ===

Standalone script.

Import:

analyzeArtifacts
SAMPLE_ARTIFACTS
AI

Run a sample excavation.

Use analysis mode:

"deep"

Log:

- project title
- artifact count
- timeline event count
- discovery count

On failure:
- log error
- process.exit(1)

Add npm script:

"check:api": "tsx --env-file=.env.local scripts/check-api.ts"

---

=== 8. app/api/excavate/route.ts ===

POST handler.

Parse JSON body.

Return 400 on malformed JSON.

Read:

artifacts
analysisMode

Validate:

- artifacts must be an array
- empty artifacts → "No artifacts provided."
- artifact count > LIMITS.maxArtifacts → appropriate message
- individual content length > LIMITS.maxArtifactLength → appropriate message
- total content > LIMITS.maxTotalCharacters → appropriate message

If analysisMode is invalid, silently fall back to DEFAULTS.analysisMode.

Call:

analyzeArtifacts(...)

On success:

200 + JSON result

On failure:

console.error

return:

500 + { error: message }

---

=== 9. lib/api.ts ===

Browser-only fetch helper.

Export:

requestExcavation(
  payload: ExcavationRequest
): Promise<ExcavationResult>

POST:

/api/excavate

Handle network failure with:

"Could not reach the excavation server. Is `npm run dev` still running?"

Parse JSON defensively.

Return server error messages when available.

---

=== 10. components/ExcavationWorkspace.tsx ===

"use client"

This is the ONLY state owner.

State:

- artifacts
- analysisMode
- excavationState
- excavationResult
- selectedArtifactId
- selectedArtifactIds
- selectedDiscoveryId
- activeView
- apiError
- evidenceWallMode
- comparisonMode

activeView:

"site"
"evidence"
"timeline"
"relationships"
"report"

handleImport:
- add artifacts
- assign stable IDs
- detect file type
- calculate size
- preserve metadata

handleExcavate:
- validate artifact collection
- set loading state
- call requestExcavation
- store result
- set results state
- handle errors

handleSelectArtifact:
- open specimen detail
- highlight related artifacts

handleCompare:
- require exactly two artifacts
- open comparison view

Render the application as a full viewport.

Do NOT render a centered workstation card.

Main composition:

FloatingHeader
+
ExcavationCanvas
+
FloatingNavigation
+
ContextPanels / overlays

The canvas should remain the dominant visual element.

---

=== 11. components/FloatingHeader.tsx ===

A minimal floating archival header.

Left:

DIGITAL
ARCHAEOLOGIST

Below:

SITE / {project identifier}

Right:

IMPORT
EXCAVATE
FILTER

Do not create a traditional horizontal SaaS navbar.

The header should visually float over the excavation canvas.

---

=== 12. components/ExcavationCanvas.tsx ===

This is the primary visual component.

Props:

- artifacts
- relationships
- discoveries
- selectedArtifactId
- onSelectArtifact
- onSelectRelationship

Create a large open canvas with:

- dark excavation background
- subtle coordinate grid
- coordinate markings
- artifact specimens
- relationship lines
- discovery annotations

Artifact positions should be deterministic based on artifact IDs so they do not randomly jump between renders.

Each artifact should render as a specimen object.

Example:

SPECIMEN 014

final.py

SOURCE
12.4 KB

2024.02.14

OBSERVED

Use different visual treatments for:

SOURCE
DOCUMENT
CONFIG
IMAGE
LOG
UNKNOWN

Relationships should render as thin SVG lines.

Selected artifacts should illuminate their connected evidence.

Do not turn the graph into a conventional node graph.

The visual metaphor should remain an evidence table.

---

=== 13. components/ArtifactSpecimen.tsx ===

Props:

- artifact
- selected
- related
- onClick

Render:

- specimen number
- filename
- type
- size
- timestamp
- status

Use an archival paper-like surface.

Add subtle catalog markings.

Hover should reveal:

VIEW SPECIMEN

Do not use excessive border-radius.

---

=== 14. components/SpecimenDetail.tsx ===

A large overlay/panel for inspecting one artifact.

Display:

SPECIMEN {id}

filename

TYPE
SIZE
PATH
TIMESTAMP
EXTENSION

Then:

ARCHAEOLOGICAL INTERPRETATION

Show AI interpretation only when available.

Then:

EVIDENCE CONNECTIONS

List relationships involving the artifact.

Actions:

VIEW ON SITE
COMPARE
CLOSE

---

=== 15. components/FloatingNavigation.tsx ===

Do not use a sidebar.

Create a floating navigation strip.

Views:

SITE
EVIDENCE
TIMELINE
RELATIONSHIPS
REPORT

The active view should look like an archival catalog tab.

---

=== 16. components/DiscoveryCard.tsx ===

Props:

- discovery
- onSelect

Render an editorial evidence card.

Header:

DISCOVERY {id}

Title in IBM Plex Serif.

Body description.

Evidence references.

Confidence.

Status:

OBSERVED
INFERRED
UNKNOWN

Use:
- green for observed/verified
- amber for inferred
- red/neutral treatment for unknown

Make the distinction extremely obvious.

---

=== 17. components/EvidenceWall.tsx ===

Create an evidence-wall composition.

Arrange artifacts and discoveries in a visually irregular but intentional collage.

Use:

- specimen cards
- document fragments
- discovery cards
- evidence lines
- annotations
- catalog labels

Do not make this a normal grid.

Allow the user to select an item and highlight related evidence.

Include:

"CONNECT EVIDENCE"

when multiple artifacts are selected.

---

=== 18. components/TimelineView.tsx ===

Create a full-screen archival timeline.

Do not use a standard dashboard timeline component.

Use a large editorial timeline.

Display years prominently.

Each event contains:

DATE

EVENT TITLE

DESCRIPTION

STATUS

CONFIDENCE

SUPPORTING ARTIFACTS

Clicking an event highlights its supporting artifacts on the excavation map.

Use visual differences for:

OBSERVED
INFERRED
UNKNOWN

---

=== 19. components/RelationshipView.tsx ===

Show artifact relationships as an investigation map.

Relationships:

MODIFIED
REPLACED
REFERENCED
DUPLICATED
DERIVED
UNKNOWN

When a relationship is selected, show:

SOURCE ARTIFACT

RELATIONSHIP

TARGET ARTIFACT

EXPLANATION

EVIDENCE STATUS

Never claim a relationship as confirmed when it is inferred.

---

=== 20. components/ComparisonView.tsx ===

Props:

- firstArtifact
- secondArtifact
- onClose

Create an archival comparison sheet.

Left:

EARLIER SPECIMEN

filename
date
type

Right:

LATER SPECIMEN

filename
date
type

Between them:

→

Then:

ADDED

REMOVED

CHANGED

RENAMED

RESTRUCTURED

If content is available, show a readable text difference.

Below:

ARCHAEOLOGICAL INTERPRETATION

Explain what the change may mean.

Clearly label interpretation as:

OBSERVED

or

INFERRED

Never fabricate changes that cannot be established.

---

=== 21. components/ArchaeologicalReport.tsx ===

Create a large editorial report view.

Do NOT make it look like a dashboard.

Opening section:

THE ARCHAEOLOGY OF

{projectTitle}

Then:

SUMMARY

{summary}

Then sections:

01 // PROJECT HISTORY

02 // TIMELINE

03 // TURNING POINTS

04 // ABANDONED IDEAS

05 // MISSING EVIDENCE

06 // FINAL RECONSTRUCTION

Use large serif headings.

Use monospace metadata.

Include supporting artifact references wherever possible.

---

=== 22. components/MissingEvidence.tsx ===

Render archival gaps as explicit breaks in the timeline.

Example:

ARCHIVAL GAP

FEB 22 → MAR 02

9 DAYS UNACCOUNTED FOR

KNOWN BEFORE

Authentication prototype exists.

KNOWN AFTER

Authentication architecture changed.

RECOVERED EVIDENCE

0 artifacts

STATUS

UNKNOWN

Do not allow missing periods to be filled with invented narratives.

---

=== 23. components/ImportPanel.tsx ===

Create an immersive import experience.

Empty state:

NO SITE EXCAVATED

"Import a collection of digital artifacts to begin reconstruction."

Button:

IMPORT ARTIFACTS

Support:

- drag and drop
- file picker
- multiple files

Show imported specimens before excavation.

Each imported artifact gets:

- filename
- type
- size
- timestamp
- remove button

---

=== 24. components/ExcavationProgress.tsx ===

Do NOT use a conventional circular spinner.

Create a scanning-line animation.

Display:

EXCAVATION IN PROGRESS

Then rotating activity labels:

INDEXING ARTIFACTS

MAPPING RELATIONSHIPS

RECONSTRUCTING CHRONOLOGY

SEARCHING FOR TURNING POINTS

IDENTIFYING ARCHIVAL GAPS

Show:

ARTIFACTS PROCESSED

{count} / {total}

The visual should resemble a scientific scanning instrument.

---

=== 25. components/EmptyState.tsx ===

Full excavation canvas empty state.

Display:

SITE STATUS: UNEXCAVATED

NO ARTIFACTS FOUND

"Import a collection of digital artifacts to begin reconstruction."

Button:

IMPORT ARTIFACTS

Do not use the old Code Roaster "{}" icon.

---

=== 26. components/ErrorState.tsx ===

Display:

EXCAVATION INTERRUPTED

The artifact collection could not be completely reconstructed.

Show:

RECOVERED
{count}

MISSING
{count}

Then:

{error}

Button:

RESUME EXCAVATION

---

=== 27. components/StatusStrip.tsx ===

Do NOT recreate the old bottom Code Roaster status bar.

Instead, use small contextual status labels around the application.

Examples:

SITE STATUS: ACTIVE

ARTIFACTS: 47

DISCOVERIES: 12

EVIDENCE LINKS: 31

LAST EXCAVATION: 14:32

These should appear as small archival metadata elements rather than a conventional footer.

---

=== 28. components/SectionLabel.tsx ===

Props:

number
title

Render:

01 // ARTIFACTS

or:

04 // TURNING POINTS

Use monospace uppercase tracked-out typography.

This is a reusable visual motif across the report.

---

=== 29. components/ArtifactFilters.tsx ===

Filters:

ALL

SOURCE

DOCUMENT

CONFIG

IMAGE

LOG

DATA

UNKNOWN

Also allow:

OBSERVED

INFERRED

UNKNOWN

Do not use large pill-shaped filters.

Use compact archival tabs.

---

=== 30. components/DiscoveryOverlay.tsx ===

When a major discovery is selected, display a floating overlay:

NEW DISCOVERY

EVENT 014

THE FIRST ARCHITECTURE SHIFT

Then:

EVIDENCE

final.py
final_REAL.py
README_old.md

CONFIDENCE

87%

STATUS

INFERRED

Action:

INSPECT EVIDENCE

When selected, highlight all supporting artifacts on the excavation map.

---

=== 31. app/globals.css ===

Implement the Stitch visual system.

Important:

Do not use the previous Code Roaster canvas colors.

Use the dark excavation environment.

Create:

- dark grid
- archival paper surfaces
- thin evidence lines
- serif display typography
- monospace metadata
- restrained accent colors
- thin borders
- minimal shadows
- sharp geometry

Add accessible focus states.

Add thin custom scrollbar styling.

Avoid excessive rounded corners.

---

=== 32. Final interaction requirements ===

Confirm:

1. User can import multiple artifacts.
2. Artifact metadata appears immediately.
3. User can remove artifacts before excavation.
4. EXCAVATE sends the artifact collection to the server.
5. Gemini returns structured archaeological analysis.
6. Loading state shows the scanning excavation animation.
7. Results populate the excavation canvas.
8. Related artifacts become visually connected.
9. Clicking an artifact opens specimen detail.
10. Clicking a relationship highlights both artifacts.
11. Clicking a timeline event highlights supporting artifacts.
12. Clicking a discovery reveals its evidence chain.
13. User can compare exactly two artifacts.
14. Evidence status is always visible.
15. OBSERVED, INFERRED, and UNKNOWN are visually distinct.
16. Missing evidence is explicitly represented.
17. No AI-generated conclusion is presented as certain when it is only inferred.
18. The application never invents missing artifacts or dates.
19. The application works without authentication.
20. No database is required.
21. API key is server-side only.
22. The app builds with no TypeScript errors.
23. `npm run dev` works.
24. `npm run check:api` works when `.env.local` contains a valid key.
25. The interface remains visually distinct from the previous Code Roaster design.

Do not add features that are not described above.

Do not turn this into a generic AI chatbot.

Do not turn this into a conventional SaaS dashboard.

Do not add a code editor as the primary interface.

The excavation canvas, artifacts, evidence relationships, timeline, and archaeological report are the core product.

---

FINAL DESIGN PRINCIPLE:

The user should feel like they have discovered an old digital project and are physically examining its remains.

The experience should communicate:

"Something happened here. Let's find out what."

It should feel like:

ARCHAEOLOGICAL FIELD NOTEBOOK
+
FORENSIC EVIDENCE WALL
+
MUSEUM ARCHIVE
+
DIGITAL RESEARCH LAB

and NOT:

AI CHAT
+
CODE EDITOR
+
SAAS DASHBOARD.

After this finishes: create `.env.local` yourself (don't let the agent do it), paste your real Gemini key, run `npm run check:api`, then `npm run dev` and test at http://localhost:3000.
```
