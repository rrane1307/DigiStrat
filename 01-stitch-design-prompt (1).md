# Digital Archaeologist — Design Prompt (Stitch MCP)

Paste this single prompt into Stitch (via MCP inside Antigravity) to generate the full visual reference before any code is written.

---

Design the visual language for "Digital Archaeologist," an AI-powered digital archaeology tool that reconstructs the history of a project from messy folders, documents, source files, notes, screenshots, archives, and other digital artifacts.

IMPORTANT DESIGN REQUIREMENT:

This product MUST NOT visually resemble a typical developer dashboard, SaaS dashboard, code editor, AI chat interface, or the previously designed "Code Roaster" interface.

Do not reuse the same workstation layout, top-bar structure, two-column editor/report structure, footer status bar, or visual composition.

The interface should feel like a completely different product.

The primary metaphor is:

"AN ARCHAEOLOGICAL EXCAVATION SITE FOR DIGITAL ARTIFACTS."

Think of:
- an archaeologist's excavation table
- museum artifact cataloging
- forensic evidence mapping
- an old research archive
- a wall covered with photographs and evidence
- a curator's collection database
- historical maps with annotations
- strings connecting physical evidence on an investigation board

The interface should feel exploratory, visual, investigative, and slightly mysterious.

Do NOT make it feel like an AI coding assistant.

---

## CORE VISUAL CONCEPT

The main interface is a large "ARCHAEOLOGICAL SITE MAP".

Instead of a conventional dashboard, the user enters a virtual excavation environment.

Artifacts appear as physical-looking digital specimens distributed across a large canvas.

Examples:

final.py
README_old.md
notes.txt
config.json
screenshot_03.png
archive.zip
database.sql
final_REAL.py

Artifacts should not simply appear as rows in a sidebar.

They should appear as individual evidence objects/cards positioned across a visual workspace.

Some artifacts are connected by thin lines representing relationships.

The user should be able to visually understand:

WHAT EXISTED
↓
WHAT CHANGED
↓
WHAT DISAPPEARED
↓
WHAT WAS REPLACED
↓
WHAT THE PROJECT BECAME

The primary screen should therefore feel closer to an interactive evidence board than a software dashboard.

---

## AESTHETIC DIRECTION

Visual direction:

"ARCHAEOLOGICAL FIELD STATION × DIGITAL FORENSICS × MUSEUM ARCHIVE"

Use an editorial, tactile, archival visual language.

The interface should resemble a carefully documented excavation rather than a polished SaaS product.

Use:

- large open canvas areas
- asymmetrical compositions
- paper-like surfaces
- annotation marks
- thin connecting lines
- evidence pins
- handwritten-style annotation accents used sparingly
- catalog numbers
- specimen labels
- archival stamps
- coordinate references
- measurement marks
- subtle grid/ruler elements
- layered cards
- photographic/document frames
- irregular positioning

Avoid a perfectly symmetrical dashboard.

Avoid repeated rounded cards.

Avoid giant centered panels.

Avoid generic SaaS spacing.

Avoid gradients.

Avoid glassmorphism.

Avoid purple AI aesthetics.

Avoid chat bubbles.

Avoid conventional sidebar navigation.

Avoid the previous Code Roaster layout.

---

## COLOR SYSTEM

Create a completely different palette from the previous Code Roaster design.

Use a dark archival environment with warm artifact surfaces.

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

Accent colors should appear only on important evidence, discoveries, warnings, and active selections.

---

## TYPOGRAPHY

Use a completely different typographic hierarchy from the original product.

Primary display font:
- IBM Plex Serif or another editorial serif typeface

Secondary UI font:
- IBM Plex Sans

Technical metadata:
- IBM Plex Mono

Use serif typography for major historical discoveries and project titles.

Use sans-serif for navigation and interface controls.

Use monospace only for:
- filenames
- paths
- timestamps
- hashes
- coordinates
- artifact IDs
- technical metadata

This creates a museum/archive feeling instead of a developer-tool feeling.

---

# SCREEN 1 — EXCAVATION MAP

The primary screen should be an immersive full-window excavation environment.

Do NOT use a traditional centered application card.

The entire viewport should function as the workspace.

### TOP LEFT

Display:

DIGITAL
ARCHAEOLOGIST

with a small excavation number:

SITE 07 / PROJECT ARCHIVE

Under it, display:

"Reconstructing the history of a digital artifact collection."

Keep this area editorial and minimal.

---

### TOP RIGHT

Use compact floating controls:

IMPORT
EXCAVATE
FILTER
ZOOM

Do not place them inside a conventional SaaS navigation bar.

They should appear like tools floating over the excavation canvas.

---

## MAIN EXCAVATION CANVAS

The majority of the screen is an open archaeological map.

Use a subtle coordinate grid.

Add small coordinate markings around the edges:

X: 014
Y: 083

GRID 04

SECTION B

The canvas should contain artifact specimens positioned at different locations.

Example:

┌─────────────────────┐
│ SPECIMEN 014        │
│                     │
│ final.py            │
│ 12.4 KB             │
│ 2024.02.14          │
│                     │
│ OBSERVED            │
└─────────────────────┘

Another:

┌─────────────────────┐
│ SPECIMEN 027        │
│                     │
│ final_REAL.py       │
│ 18.1 KB             │
│ 2024.03.18          │
│                     │
│ VERIFIED            │
└─────────────────────┘

Artifacts should have slightly different sizes and positions.

They should feel like objects placed on an investigation table.

---

## EVIDENCE CONNECTIONS

Connect related artifacts using thin lines.

For example:

final.py
      \
       \
        → AUTH SYSTEM
       /
README.md

and:

final.py ─────→ final_v2.py ─────→ final_REAL.py

Use small labels along the lines:

MODIFIED

REPLACED

REFERENCED

DUPLICATED

UNKNOWN

Do not use conventional graph-node styling.

The relationships should feel like physical evidence connected with investigation string.

---

# FLOATING DISCOVERY CARD

When the AI detects something important, show a floating archival card.

Example:

DISCOVERY 014

THE FIRST ARCHITECTURE SHIFT

━━━━━━━━━━━━━━━━━━

Three artifacts indicate that the
authentication layer was redesigned
between February 14 and March 18.

EVIDENCE

final.py
final_REAL.py
README_old.md

CONFIDENCE 87%

[ INSPECT EVIDENCE ]

This card should visually resemble a curator's research note.

---

# SCREEN 2 — THE ARCHAEOLOGICAL REPORT

The second screen should NOT be another dashboard.

It should feel like a large historical research document spread across the screen.

Use a split-page editorial composition.

Left side:

PROJECT HISTORY

Large serif title.

Example:

"THE EVOLUTION
OF PROJECT ATLAS"

Below it:

FIRST RECORDED
FEB 11 2024

LAST RECORDED
MAR 18 2024

ARTIFACTS
47

DOCUMENTED EVENTS
12

---

Right side:

A vertical historical timeline.

Do not use conventional dashboard cards.

Instead, make the timeline look like an archival catalog.

Example:

2024

02.11
────────────────────
PROJECT INITIALIZED

README.md
notes.txt

The first documented project
structure appears.

OBSERVED


02.14
────────────────────
FIRST PROTOTYPE

final.py

Initial implementation
identified.

OBSERVED


02.21
────────────────────
ARCHITECTURE SHIFT

config.json
auth.py
database.sql

Multiple artifacts indicate
a significant restructuring.

INFERRED


03.03
────────────────────
MISSING PERIOD

No artifacts recovered.

UNKNOWN


03.18
────────────────────
FINAL KNOWN STATE

final_REAL.py

Last known artifact
in the collection.

OBSERVED

---

# ARTIFACT DETAIL VIEW

Clicking an artifact should open a large overlay resembling a museum specimen catalog.

Example:

SPECIMEN 027

FINAL_REAL.PY

━━━━━━━━━━━━━━━━━━━━

TYPE
SOURCE CODE

SIZE
18.1 KB

LAST MODIFIED
2024.03.18 17:42

LOCATION
/archive/project/

HASH
a92f...71c

━━━━━━━━━━━━━━━━━━━━

ARCHAEOLOGICAL INTERPRETATION

This artifact appears to represent
the latest known implementation of
the authentication system.

━━━━━━━━━━━━━━━━━━━━

EVIDENCE

→ references auth module
→ modifies database schema
→ referenced by README_final.md

━━━━━━━━━━━━━━━━━━━━

STATUS

OBSERVED

[ VIEW RELATIONSHIPS ]

---

# BEFORE / AFTER EXCAVATION

Create an interactive artifact comparison mode.

Instead of conventional code diff panels, use an archival comparison sheet.

LEFT:

EARLIER SPECIMEN

final.py

FEB 14 2024

RIGHT:

LATER SPECIMEN

final_REAL.py

MAR 18 2024

Between them show a large arrow:

──────────────→

with labels:

ADDED

REMOVED

RENAMED

RESTRUCTURED

Then below show the historical interpretation.

---

# EVIDENCE WALL

Create a separate view called:

"THE EVIDENCE WALL"

This view should look like a physical investigation wall.

Arrange:

- artifact photographs
- document fragments
- filenames
- timestamps
- notes
- AI discoveries
- relationships

in an irregular but intentional collage.

Use thin lines connecting related items.

Some items can be rotated by 1–2 degrees.

Use small archival tape/pin visual elements sparingly.

The result should feel like a detective investigation board combined with a museum archive.

---

# UNKNOWN / MISSING EVIDENCE

Create a visually distinctive "MISSING EVIDENCE" section.

Instead of a normal empty card, show a gap in the timeline.

Example:

━━━━━━━━━━━━━━━━━━━━

ARCHIVAL GAP

FEB 22 → MAR 02

9 DAYS UNACCOUNTED FOR

━━━━━━━━━━━━━━━━━━━━

KNOWN BEFORE

Authentication prototype exists.

KNOWN AFTER

Authentication architecture
has been completely replaced.

RECOVERED EVIDENCE

0 artifacts

STATUS

UNKNOWN

Do not allow the AI to invent what happened during the missing period.

---

# EXCAVATION STATES

Design the following states as distinct visual experiences.

## INITIAL STATE

Show a large empty excavation field.

At the center:

NO SITE EXCAVATED

"Import a collection of digital artifacts
to begin reconstruction."

Below:

[ IMPORT ARTIFACTS ]

Add small archival notation:

SITE STATUS: UNEXCAVATED

---

## EXCAVATING STATE

Do not use a conventional circular loading spinner.

Instead, show an animated scanning line moving across the excavation map.

Display:

EXCAVATION IN PROGRESS

INDEXING ARTIFACTS

47 / 132

Then show changing activity labels:

CATALOGING FILES

MAPPING RELATIONSHIPS

RECONSTRUCTING TIMELINE

SEARCHING FOR MISSING EVIDENCE

The visual should feel like a scientific scanning instrument.

---

## DISCOVERY STATE

When an important discovery occurs, briefly highlight connected artifacts.

Show:

NEW DISCOVERY

EVENT 014

"Possible architecture migration
detected."

Then visually illuminate the relevant evidence connections.

---

## ERROR STATE

Do not use a generic error dashboard.

Show an archival interruption notice:

EXCAVATION INTERRUPTED

The artifact collection could not
be completely reconstructed.

RECOVERED:
83 / 91 ARTIFACTS

MISSING:
8 ARTIFACTS

[ RESUME EXCAVATION ]

---

# NAVIGATION

Do not use a standard left sidebar.

Use a minimal floating navigation strip.

Views:

SITE
EVIDENCE
TIMELINE
RELATIONSHIPS
REPORT

The active view should look like a catalog tab or field marker.

---

# INTERACTION LANGUAGE

Interactions should feel like investigating physical evidence.

Clicking an artifact:
→ opens specimen catalog

Dragging an artifact:
→ repositions it on the evidence map

Clicking a connection:
→ reveals why the artifacts are related

Clicking a timeline event:
→ highlights supporting evidence

Selecting multiple artifacts:
→ enables "CONNECT EVIDENCE"

Selecting two artifacts:
→ enables "COMPARE SPECIMENS"

Clicking a discovery:
→ reveals its evidence chain

Zooming:
→ moves from project-level history into individual artifacts

---

# INFORMATION CLASSIFICATION

Every AI-generated conclusion must clearly identify its epistemic status.

OBSERVED

Directly supported by artifact metadata or content.

INFERRED

Reconstructed from multiple pieces of evidence.

UNKNOWN

Cannot be established from available evidence.

Never visually present an inference as an established fact.

---

# VISUAL DETAILS

Use subtle visual details that reinforce the archaeological metaphor:

- specimen numbers
- catalog stamps
- coordinate references
- measurement ticks
- archive labels
- evidence pins
- paper edges
- document fragments
- archival tape
- thin investigation lines
- date stamps
- collection numbers
- excavation zones
- section markers
- faded annotations

Keep these details restrained.

The interface must remain highly usable.

---

# RESPONSIVE BEHAVIOR

On smaller screens, the excavation map should transform into a vertical evidence stream rather than becoming a conventional dashboard.

Artifacts become stacked specimens.

Connections become expandable relationship sections.

The timeline becomes a vertical archival chronology.

The evidence wall becomes a scrollable collection.

---

# COMPONENT SYSTEM

Export a complete design system including:

- typography scale
- color tokens
- spacing tokens
- artifact specimen cards
- archival labels
- evidence pins
- discovery cards
- timeline markers
- evidence connections
- status indicators
- catalog overlays
- comparison sheets
- floating controls
- navigation tabs
- buttons
- input fields
- filters
- excavation progress indicators
- missing evidence blocks
- annotation components

The components should feel like parts of an archaeological research instrument, not generic SaaS components.

---

# DESIGN QUALITY BAR

The final design should immediately communicate:

"Someone is investigating the history of a digital project."

It should NOT communicate:

"Someone is using an AI code review dashboard."

The visual identity must be clearly distinct from the Code Roaster design.

Do not reuse the Code Roaster:
- centered workstation
- two-column editor/report layout
- top control bar
- bottom status bar
- off-white SaaS cards
- burnt-orange-on-paper palette
- generic bordered dashboard panels

Create a completely new composition and visual system.

The final interface should feel closer to:

ARCHAEOLOGICAL FIELD NOTEBOOK
+
FORENSIC EVIDENCE WALL
+
MUSEUM ARCHIVE
+
DIGITAL RESEARCH LAB

than:

SAAS DASHBOARD
+
CODE EDITOR
+
AI CHAT.

---

Export the complete color tokens, typography system, spacing system, component styles, interaction states, and layout rules so they can be handed to a coding agent to implement in Tailwind CSS.

Ensure the generated screens are visually distinctive, cohesive, and sufficiently detailed that a coding agent can reproduce the design without reverting to generic SaaS patterns.

---

After Stitch finishes: keep the generated screens, design tokens, typography references, artifact components, timeline patterns, evidence-wall layout, and interaction states open. These will be referenced directly while running the coding prompt in `02-antigravity-build-prompt.md`, ensuring the implementation preserves the archaeological visual language rather than drifting toward a conventional AI dashboard.