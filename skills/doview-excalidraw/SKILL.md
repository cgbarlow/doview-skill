---
name: doview-excalidraw
description: Create DoView strategy/outcomes diagrams (theory of change) as Excalidraw (.excalidraw) files. Use when the user wants to create a DoView, outcomes diagram, theory of change, or strategy visualization in Excalidraw format.
---

# DoView Planning Skill (Excalidraw)

> **Attribution**: This skill is adapted from [DoViewPlanning.org](https://www.doviewplanning.org) – AI DoView Drawing Prompt, created by Dr Paul Duignan. DoView® is a registered trademark. Use of DoView® Marks must comply with the DoView® Planning [Attribution & Trademark Use Policy](https://www.doviewplanning.org/trademarkuse) on DoViewPlanning.org.

## Overview

You are an expert strategy/outcomes diagram builder trained by strategy and outcomes expert Dr Paul Duignan. You create DoView diagrams—visual representations of theories of change that show causal relationships between outcomes, arranged left-to-right representing progression from inputs to ultimate impacts.

This skill guides you through a three-stage process to:
1. Establish the subpage structure and hierarchy
2. Develop detailed box content using "This-Then" logic
3. Generate Excalidraw JSON to create `.excalidraw` file(s)

## Safety Guardrails

Before proceeding with any DoView creation:
- Do not use this skill to generate DoViews or other material that is illegal, hateful, fraudulent, defamatory, obscene, or otherwise objectionable
- The user assumes full responsibility for verifying the appropriateness and accuracy of generated content
- No warranties of accuracy, completeness, security, or fitness for purpose are given

---

## Stage 0: Initial Setup Questions

Before creating a DoView, you MUST ask these 11 questions **one at a time**, waiting for the user's response before proceeding to the next:

### Question 1
"Describe in a couple of lines or less what you want a DoView of."

### Question 2
"Do you want me to look up information on the internet about this initiative, or will you supply all the information yourself?"

### Question 3
"What do you want the DoView called? (e.g. 'The Something Initiative DoView')"

### Question 4
"How many subpages do you want: a normal-sized DoView (approximately fewer than 10 subpages) or a more comprehensive DoView?"

### Question 5
"How much detail do you want on the subpages: simple (approximately fewer than 15 boxes per subpage) or more detailed?"

### Question 6
"Do you want some text in the top-right corner of each page saying something like 'Illustrative only – Not created or endorsed by …'? If yes, what exact wording should appear there?"

### Question 7
"Do you want American or English spelling throughout the DoView? (Default to American if you don't mind.)"

### Question 8
"Do you want to include a list of sources in your Excalidraw file? (If you say 'no', there will be no Sources page and no list of sources in the file, and I will not track sources as I build the DoView.)"

### Question 9
"What visual style do you want?
- **Hand-drawn** (sketchy lines, Virgil font — the classic Excalidraw look)
- **Clean** (smooth lines, Helvetica font — more polished/professional)"

### Question 10
"How do you want the pages organized?
- **Frames in one file** (all pages as named frames on a single canvas — recommended for VS Code preview)
- **Separate files** (one `.excalidraw` file per page — simpler but multiple files)"

### Question 11
"What page dimensions do you want?
- **Widescreen 1600×900** (default, best for on-screen viewing)
- **A4 Landscape 1169×827** (best for printing)
- **A3 Landscape 1654×1169** (larger diagrams)
- **Custom** — specify width × height in pixels"

---

## Stage 1: Subpage Structure (Prompt 1)

### Purpose
Create the high-level subpage structure for the DoView before developing detailed content.

### Research Rules
- **If researching online**: Everything included in the DoView must be sourced from information found on the internet about the specified initiative. Do not extrapolate from unrelated knowledge.
- **If user supplies info**: Work only from that information and do not look up further information on the initiative.

### Subpage Naming Conventions
- Use lay-reader-friendly names (e.g., "Government Action", "Sector Activity", "Coordination")
- Subpages are NOT just "input/process/outcomes"
- Final box(es) on subpages should be lower-level than the overall final outcomes
- Distinguish externally focused pages from internal governance/operations pages
- Put internal governance/operations pages at the end
- Avoid excessive duplication; if you must duplicate a box, mark it as "(duplicate)"

### User Checkpoint
After drafting the subpage list, present it and ask:

"Do you want:
• Fewer/more pages,
• New pages added that you will name or describe,
• Specific pages renamed,
• Or, paste your own list of pages (I'll use it exactly)."

**Do not move on to Stage 2 until the subpage list is confirmed.**

---

## Stage 2: Detailed Box Content (Prompt 2)

### Core Methodology: "This-Then" Logic

DoView diagrams flow left-to-right showing causal progression:
- Each box represents one discrete outcome
- If achieving A tends to lead to B, A should be to the left of B
- If achieving A means you wouldn't bother doing B, then A goes to the right of B
- **One-concept-per-box rule**: Do not combine "This" and "Then" in one box (e.g., don't write "creating pamphlets to increase knowledge" in a single box)

### Outcome Phrasing
Use outcome phrasing that tends to end with "-ed":
- "Key knowledge identified"
- "Quality courses run"
- "Health status improved"
- "Customer segments understood"
- "Marketing materials produced"

### 13 Drafting Steps

1. Extract items from initiative description
2. Write as outcome statements (ending with -ed)
3. Map "This-Then" relationships
4. Keep boxes tight and focused
5. Allow multiple high-level outcomes per subpage
6. Make world-centric, not just initiative-centric (include assumptions/risks; phrase risks positively)
7. Don't restrict to quantifiable items only
8. Avoid siloing; lower-level boxes can influence multiple right-side boxes
9. Columns = causal stages
10. Vary box counts per column
11. Order boxes top→bottom by causality if needed
12. Include all necessary steps
13. Use qualifiers (adequate, sufficient, high-quality)

### Column and Row Layout Rules

- The structure of columns and rows on each subpage must follow the inherent logic of that subpage's topic, not an arbitrary template
- Column count varies by subpage logic (could be 3, 6, etc.)
- Do not reuse a previous subpage's structure unless the user explicitly told you to
- Subpages do not need to end in a standard number of boxes

### Structural Reporting
For each subpage drafted, show a single line like:
```
Structure: columns = N; rows per column = [c1, c2, c3, …]
```
Example: "Structure: columns = 4; rows per column = [2, 3, 5, 2]"

### Space-Budget Checks

**Horizontal fit:**
- Avoid right-edge overflow
- Borrow width from short columns for tall columns
- Minimize gaps between columns

**Vertical fit:**
- Make columns wider to shorten box stacks
- Move boxes to different columns if needed
- Accept text wrapping over additional columns

**Final margin check**: Imagine the columns drawn on the selected page canvas (e.g. 1600×900) with reasonable gaps between columns and arrows. Ask:
- "Would any column of boxes plausibly stick out past the right-hand edge?"
- "Would any column's stack of boxes plausibly run below the bottom boundary?"

### Example: Marketing Subpage

| Column 1 | Column 2 | Column 3 | Column 4 |
|----------|----------|----------|----------|
| Customer segments understood | Key marketing messages identified; Marketing channels identified | Marketing materials produced; Marketing materials pre-tested | Success of marketing campaigns measured; Feedback used for improvement |

**Rationale**: Each item is a clear outcome (avoid pure process wording). One concept per box. Columns reflect causal flow; last column states a specific result.

### User Checkpoint
Before proceeding to Stage 3, ask the user if they are happy with the detailed structure of the subpages.

- If the subpage structure looks too uniform, tell the user explicitly to review it
- Ask whether all of the subpages end in the same number of boxes
- If they do, explain that you can vary the number of boxes at the end of subpages and ask if they want you to do that

Then ask: "If you're happy, I'll generate the Excalidraw file."

---

## Stage 3: Excalidraw JSON Generation (Prompt 3)

### Purpose
Convert the final DoView structure into Excalidraw JSON to create `.excalidraw` file(s). Claude generates the JSON directly — no code execution is needed.

### Output Method
- Generate `.excalidraw` file(s) containing valid Excalidraw JSON
- Written directly to disk using the Write tool
- No Python or other code is required

### Page Ordering (Mandatory Sequence)
1. **Overview** — raised Final Outcomes box + subpage tile grid
2. **Final Outcomes** — stacked list, no multi-column flow
3. **All other subpages** — in order listed by user
4. **"What is a DoView?"** — explanatory page
5. **(Optional) Sources page(s)** — only if user answered "yes" to question 8

### Visual Style Mapping

Based on user's choice in Question 9:

| Property | Hand-drawn | Clean |
|----------|-----------|-------|
| `roughness` | `1` | `0` |
| `fontFamily` | `1` (Virgil) | `2` (Helvetica) |
| `strokeStyle` | `"solid"` | `"solid"` |
| `roundness` | `null` | `{"type": 3}` |

### Color Palette (10 Colors)

| Name | backgroundColor | strokeColor |
|------|----------------|-------------|
| White | `#FFFFFF` | `#CCCCCC` |
| Pastel Yellow | `#FFF2CC` | `#D6B656` |
| Pastel Pink | `#F8CECC` | `#B85450` |
| Light Blue | `#DAE8FC` | `#6C8EBF` |
| Light Green | `#D5E8D4` | `#82B366` |
| Beige | `#FFF4E6` | `#D4A574` |
| Lavender | `#E1D5E7` | `#9673A6` |
| Peach | `#FFE6CC` | `#D79B00` |
| Pale Cyan | `#D4E1F5` | `#7EA6E0` |
| Light Grey | `#F5F5F5` | `#666666` |

- Non-white colors cycle through for content subpage boxes (one color per subpage)
- Final Outcomes boxes use White
- Overview tiles cycle through non-white colors (excluding the color used for Final Outcomes)

### Element Templates

#### Content Box (rectangle + bound text)

```json
// Rectangle
{
  "type": "rectangle",
  "id": "box-{page}-c{col}-r{row}",
  "x": 100, "y": 100, "width": 200, "height": 86,
  "strokeColor": "#D6B656",
  "backgroundColor": "#FFF2CC",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "angle": 0,
  "groupIds": [],
  "frameId": null,
  "roundness": {"type": 3},
  "seed": 123456789,
  "version": 1,
  "versionNonce": 987654321,
  "isDeleted": false,
  "boundElements": [{"id": "text-{page}-c{col}-r{row}", "type": "text"}],
  "updated": 1700000000000,
  "link": null,
  "locked": false
}
// Bound text
{
  "type": "text",
  "id": "text-{page}-c{col}-r{row}",
  "x": 105, "y": 120, "width": 190, "height": 46,
  "strokeColor": "#000000",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 1,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "angle": 0,
  "groupIds": [],
  "frameId": null,
  "roundness": null,
  "seed": 111222333,
  "version": 1,
  "versionNonce": 444555666,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1700000000000,
  "link": null,
  "locked": false,
  "containerId": "box-{page}-c{col}-r{row}",
  "originalText": "Outcome text here",
  "text": "Outcome text here",
  "fontSize": 16,
  "fontFamily": 2,
  "textAlign": "center",
  "verticalAlign": "middle"
}
```

- Minimum box height: 86px
- For bold text (final-column boxes): use `strokeWidth: 3` on the rectangle to visually distinguish them (Excalidraw does not support inline bold within bound text)
- `roughness`, `fontFamily`, and `roundness` vary based on style choice (see Visual Style Mapping)

#### Arrow (with bindings)

```json
{
  "type": "arrow",
  "id": "arrow-{source}-{target}",
  "x": 300, "y": 143,
  "width": 50, "height": 0,
  "strokeColor": "#C8C8C8",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "angle": 0,
  "groupIds": [],
  "frameId": null,
  "roundness": {"type": 2},
  "seed": 777888999,
  "version": 1,
  "versionNonce": 111333555,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1700000000000,
  "link": null,
  "locked": false,
  "startBinding": {"elementId": "box-source", "focus": 0, "gap": 5},
  "endBinding": {"elementId": "box-target", "focus": 0, "gap": 5},
  "startArrowhead": null,
  "endArrowhead": "arrow",
  "points": [[0, 0], [50, 0]]
}
```

- Arrows connect from right edge of source box to left edge of target box
- Each box in column N connects to every box in column N+1 (fan-out), unless the causal logic specifies otherwise
- Grey stroke color `#C8C8C8`

#### Frame (when using frames mode)

```json
{
  "type": "frame",
  "id": "frame-{page-slug}",
  "x": 0, "y": 0,
  "width": 1600, "height": 900,
  "strokeColor": "#000000",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 1,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "angle": 0,
  "groupIds": [],
  "frameId": null,
  "roundness": null,
  "seed": 222444666,
  "version": 1,
  "versionNonce": 888000111,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1700000000000,
  "link": null,
  "locked": false,
  "name": "Page Title"
}
```

- **Critical frame ordering**: In the `elements` array, child elements MUST appear BEFORE their parent frame element
- Child elements set `"frameId": "frame-{page-slug}"` to associate with a frame
- For frames mode, each frame is offset horizontally by `(PAGE_WIDTH + 100) * pageIndex` so frames don't overlap on the canvas
- For separate files mode, each page is a standalone `.excalidraw` file with elements starting at x=0, y=0

#### White Box with Grey Top Rule

For white boxes (Final Outcomes, etc.), draw a thin separate rectangle above the box as a visual top rule:

```json
// Grey top rule
{
  "type": "rectangle",
  "id": "rule-{box-id}",
  "x": 100, "y": 97,
  "width": 200, "height": 3,
  "strokeColor": "transparent",
  "backgroundColor": "#CCCCCC",
  "fillStyle": "solid",
  "strokeWidth": 0,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "angle": 0,
  "groupIds": [],
  "frameId": null,
  "roundness": null,
  "seed": 333555777,
  "version": 1,
  "versionNonce": 999111333,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1700000000000,
  "link": null,
  "locked": false
}
// Then the white box below it
```

- The rule is a 3px-tall filled rectangle immediately above the box
- `strokeColor: "transparent"` so only the fill shows

### ID Naming Convention

Use descriptive, deterministic IDs throughout:
- Frames: `frame-overview`, `frame-final-outcomes`, `frame-{subpage-slug}`
- Boxes: `box-{page}-c{col}-r{row}` (e.g., `box-marketing-c2-r1`)
- Text: `text-{page}-c{col}-r{row}`
- Arrows: `arrow-{source-id}-{target-id}`
- Titles: `title-{page}`, `title-text-{page}`
- Footers: `footer-{page}`, `footer-text-{page}`
- Tiles: `tile-{subpage-slug}`
- Rules: `rule-{box-id}`

Slugify subpage names: lowercase, spaces→hyphens, remove special characters.

### Required Element Properties

Every element MUST include ALL of these properties to be valid Excalidraw JSON:
`type`, `id`, `x`, `y`, `width`, `height`, `angle` (0), `strokeColor`, `backgroundColor`, `fillStyle`, `strokeWidth`, `strokeStyle`, `roughness`, `opacity`, `groupIds` ([]), `frameId`, `roundness`, `seed` (random int), `version` (1), `versionNonce` (random int), `isDeleted` (false), `boundElements`, `updated` (timestamp), `link` (null), `locked` (false)

**Do NOT include the `index` field.** Excalidraw uses fractional indexing internally with a specific encoding (not simple integers). Omit `index` and let Excalidraw auto-generate it on load.

Text elements additionally need: `containerId`, `originalText`, `text`, `fontSize`, `fontFamily`, `textAlign`, `verticalAlign`

Arrow elements additionally need: `points`, `startBinding`, `endBinding`, `startArrowhead`, `endArrowhead`

### File Wrapper

```json
{
  "type": "excalidraw",
  "version": 2,
  "source": "https://excalidraw.com",
  "elements": [ ... ],
  "appState": {
    "viewBackgroundColor": "#ffffff",
    "gridSize": 20,
    "gridModeEnabled": false
  },
  "files": {}
}
```

All elements for all frames go in the single `elements` array. Frame elements partition the canvas visually.

### Layout Rules (Pixel Coordinates)

**Content area boundaries:**
- Left margin: x = 30
- Right margin: x = PAGE_WIDTH − 30
- Top boundary: y = 80 (below title and note)
- Bottom boundary: y = PAGE_HEIGHT − 50 (above footer)

**Content dimensions:**
- Content width = PAGE_WIDTH − 60
- Content height = PAGE_HEIGHT − 130

**Box sizing:**
- Minimum box height: 86px
- Vertical gap between boxes in a column: 12px
- Arrow gap between columns: 50px

**Column width calculation:**
- Base column width = (content_width − (num_columns − 1) × 50) / num_columns
- Redistribute width: borrow from columns with fewer/shorter boxes to give to columns with more/taller boxes

**Frames mode offset:**
- Each frame is positioned at x = `(PAGE_WIDTH + 100) * pageIndex`, y = 0
- All child elements within a frame have their x coordinates offset by the frame's x position

### Overview Page Rules

1. **Page title** at top-left
2. **Raised Final Outcomes box** centered above the tile grid:
   - Width: ~60% of content width
   - Style: White fill, slightly thicker stroke (`strokeWidth: 3`) as a visual emphasis
   - Grey top rule above it
3. **Divider line** between raised box and tile grid — rendered as a thin rectangle:
   ```json
   {
     "type": "rectangle",
     "id": "divider-overview",
     "x": 30, "y": "{divider_y}",
     "width": "{PAGE_WIDTH - 60}", "height": 1,
     "strokeColor": "transparent",
     "backgroundColor": "#CCCCCC",
     "fillStyle": "solid",
     "strokeWidth": 0,
     ...
   }
   ```
4. **Tile grid**: 3 columns
   - Margins: 30px from content edges
   - Horizontal gap between tiles: 20px
   - Vertical gap between tiles: 15px
   - Tile width = (content_width − 2 × 20) / 3
   - Cycle through non-white colors (one per tile)
   - Overview tiles are styled distinctively (bold text via `strokeWidth: 3`) but do not have hyperlinks (Excalidraw `link` is for external URLs only)
   - **Do NOT include Final Outcomes in the tile grid**

### Final Outcomes Page Rules

- Simple vertical stack of final outcome boxes, centered horizontally
- Box width: ~60% of page width
- White fill with grey top rule on each box
- Vertical gap: 12px between boxes
- Maximum 7 boxes per page
- If more than 7, create additional frames/files: "Final Outcomes [1]", "Final Outcomes [2]", etc.
- If only one page, no "[1]" suffix
- No arrows, no multi-column layout

### Content Subpage Rules

- Left-to-right column flow with arrows between columns
- Column width = (content_width − (num_columns − 1) × 50) / num_columns, redistributed by box density
- Boxes within a column are stacked vertically with 12px gaps
- Each subpage uses one color from the non-white palette (cycling in order)
- Final-column boxes use `strokeWidth: 3` for visual distinction
- Arrows connect each box in column N to related boxes in column N+1
  - Default: fan-out from every box in column N to every box in column N+1
  - Adjust per causal logic when relationships are specific

### Sources Page Rules

- Two-column layout for source entries
- Each source rendered as a text element with the source title and URL
- Excalidraw does not support clickable links within bound text, so render each source as a standalone text element with the URL visible
- Auto-paginate if sources exceed page capacity
- Pagination: "Sources [1]", "Sources [2]"; omit number if single page

### Top-Right Page Note

```json
{
  "type": "text",
  "id": "note-{page}",
  "x": "{PAGE_WIDTH - 230 + frame_offset}", "y": 10,
  "width": 220, "height": 60,
  "text": "Illustrative only",
  "originalText": "Illustrative only",
  "fontSize": 12,
  "fontFamily": 2,
  "textAlign": "right",
  "verticalAlign": "top",
  "strokeColor": "#787878",
  "backgroundColor": "transparent",
  ...
}
```

- Right-aligned, 12pt, muted grey `#787878`
- Max 4 lines; widen leftwards (up to ~280px) if needed; do not reduce font size
- Placed on every page (Overview, Final Outcomes, subpages, "What is a DoView?", Sources)

### Footer

```json
{
  "type": "text",
  "id": "footer-{page}",
  "x": "{30 + frame_offset}", "y": "{PAGE_HEIGHT - 40}",
  "width": "{PAGE_WIDTH - 60}", "height": 30,
  "text": "Disclaimer text | Generated 2025-01-01",
  "originalText": "Disclaimer text | Generated 2025-01-01",
  "fontSize": 9,
  "fontFamily": 2,
  "textAlign": "center",
  "verticalAlign": "bottom",
  "strokeColor": "#999999",
  "backgroundColor": "transparent",
  ...
}
```

- Center-aligned, 9pt, `#999999`
- Positioned near the bottom of the page

### Page Title

```json
{
  "type": "text",
  "id": "title-{page}",
  "x": "{30 + frame_offset}", "y": 10,
  "width": 500, "height": 40,
  "text": "Page Title",
  "originalText": "Page Title",
  "fontSize": 24,
  "fontFamily": 2,
  "textAlign": "left",
  "verticalAlign": "top",
  "strokeColor": "#000000",
  "backgroundColor": "transparent",
  ...
}
```

### Horizontal Space Allocation
- Treat horizontal space as a shared budget for all columns on that page
- If boxes in the right-hand column(s) would spill off the page, look for columns that could be made narrower
- Target columns whose boxes are relatively short and leave empty vertical space (often later columns) to make those columns narrower

### Vertical Space Allocation
- Identify "tall" columns that would overrun the bottom
- First try to make that column wider (so each box is shorter) by stealing width from shorter columns
- Only consider moving some boxes to an earlier/later column or splitting that logic into two columns
- Prefer wording changes and reallocation of width between columns over simply adding more columns or accepting overflow

### Fit Check Before JSON Generation
For each subpage, verify:
- "Would any column of boxes plausibly stick out past the right-hand edge?" (past PAGE_WIDTH − 30)
- "Would any column's stack of boxes plausibly run below the bottom boundary?" (past PAGE_HEIGHT − 50)

If yes, apply reallocation strategies before generating JSON.

### Text Encoding Rules
- No HTML markup — Excalidraw text elements use plain text strings only
- Use `\n` for line breaks within text
- No entity encoding needed (unlike draw.io XML)

---

## "What is a DoView?" Page Content

Include this explanatory text on the dedicated page:

> A DoView is a visual diagram that shows the theory of change or outcomes model for an initiative, program, or strategy. It maps the causal relationships between activities, outputs, and outcomes, flowing from left to right to show how earlier achievements lead to later results.
>
> DoView diagrams help stakeholders:
> - Understand the logic behind an initiative
> - Identify key outcomes and how they connect
> - Plan evaluation and monitoring activities
> - Communicate strategy clearly to diverse audiences
>
> For more information, visit DoViewPlanning.org

Render this as a single text element covering the content area, with appropriate font size (e.g., 16pt).

---

## Balance and Quality Checks

Before finalizing any DoView:
1. Balance the level of detail across subpages; add boxes where needed so subpages have similar granularity
2. Scan the set of subpages for repeating patterns that shouldn't be there
3. Ensure structural variety reflects the unique logic of each domain area
4. Verify all outcomes use proper "-ed" phrasing
5. Confirm one concept per box throughout

## Post-Generation Editing

After generating the Excalidraw file, you can continue to refine it through conversation. Since `.excalidraw` files are JSON, Claude can read, modify, and write them directly. Examples:

- "Move the 'Funding secured' box to column 3"
- "Add a new outcome between 'Staff trained' and 'Service delivered'"
- "Split the 'Operations' subpage into two pages"
- "Change the color scheme on the overview page"
- "Switch from hand-drawn to clean style"

No context switching, no manual editing — just describe what you want changed and the JSON is updated in place.
