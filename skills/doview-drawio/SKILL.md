---
name: doview-drawio
description: Create DoView strategy/outcomes diagrams (theory of change) as draw.io (.drawio) files. Use when the user wants to create a DoView, outcomes diagram, theory of change, or strategy visualization in draw.io format.
---

# DoView Planning Skill (draw.io)

> **Attribution**: This skill is adapted from [DoViewPlanning.org](https://www.doviewplanning.org) – AI DoView Drawing Prompt, created by Dr Paul Duignan. DoView® is a registered trademark. Use of DoView® Marks must comply with the DoView® Planning [Attribution & Trademark Use Policy](https://www.doviewplanning.org/trademarkuse) on DoViewPlanning.org.

## Overview

You are an expert strategy/outcomes diagram builder trained by strategy and outcomes expert Dr Paul Duignan. You create DoView diagrams—visual representations of theories of change that show causal relationships between outcomes, arranged left-to-right representing progression from inputs to ultimate impacts.

This skill guides you through a three-stage process to:
1. Establish the subpage structure and hierarchy
2. Develop detailed box content using "This-Then" logic
3. Generate draw.io XML to create a multi-page .drawio file

## Safety Guardrails

Before proceeding with any DoView creation:
- Do not use this skill to generate DoViews or other material that is illegal, hateful, fraudulent, defamatory, obscene, or otherwise objectionable
- The user assumes full responsibility for verifying the appropriateness and accuracy of generated content
- No warranties of accuracy, completeness, security, or fitness for purpose are given

---

## Stage 0: Initial Setup Questions

Before creating a DoView, you MUST ask these 9 questions **one at a time**, waiting for the user's response before proceeding to the next:

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
"Do you want to include a list of sources in your draw.io file? (If you say 'no', there will be no Sources page and no list of sources in the file, and I will not track sources as I build the DoView.)"

### Question 9
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

Then ask: "If you're happy, I'll generate the draw.io XML file."

---

## Stage 3: Draw.io XML Generation (Prompt 3)

### Purpose
Convert the final DoView structure into raw draw.io XML to create a multi-page `.drawio` file. Claude generates the XML directly — no code execution is needed.

### Output Method
- Generate a single `.drawio` file containing valid XML
- The file is written directly to disk using the Write tool
- No Python or other code is required

### Page Ordering (Mandatory Sequence)
1. **Overview** — raised Final Outcomes box + subpage tile grid
2. **Final Outcomes** — stacked list, no multi-column flow
3. **All other subpages** — in order listed by user
4. **"What is a DoView?"** — explanatory page
5. **(Optional) Sources page(s)** — only if user answered "yes" to question 8

### Color Palette (10 Colors)

| Name | fillColor | strokeColor |
|------|-----------|-------------|
| White | #FFFFFF | #CCCCCC |
| Pastel Yellow | #FFF2CC | #D6B656 |
| Pastel Pink | #F8CECC | #B85450 |
| Light Blue | #DAE8FC | #6C8EBF |
| Light Green | #D5E8D4 | #82B366 |
| Beige | #FFF4E6 | #D4A574 |
| Lavender | #E1D5E7 | #9673A6 |
| Peach | #FFE6CC | #D79B00 |
| Pale Cyan | #D4E1F5 | #7EA6E0 |
| Light Grey | #F5F5F5 | #666666 |

- Non-white colors cycle through for content subpage boxes (one color per subpage)
- Final Outcomes boxes use White
- Overview tiles cycle through non-white colors (excluding the color used for Final Outcomes)

### XML Structure Templates

#### File and Page Structure

```xml
<mxfile host="claude-code">
    <diagram name="Overview" id="page-overview">
        <mxGraphModel dx="0" dy="0" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="PAGE_WIDTH" pageHeight="PAGE_HEIGHT" math="0" shadow="0">
            <root>
                <mxCell id="0"/>
                <mxCell id="1" parent="0"/>
                <!-- page content here -->
            </root>
        </mxGraphModel>
    </diagram>
    <diagram name="Final Outcomes" id="page-final-outcomes">
        <!-- ... -->
    </diagram>
    <!-- additional pages -->
</mxfile>
```

Every page MUST include the two root cells: `<mxCell id="0"/>` and `<mxCell id="1" parent="0"/>`.

Replace `PAGE_WIDTH` and `PAGE_HEIGHT` with the user's chosen dimensions (default: 1600 and 900).

#### Content Box

```xml
<mxCell id="box-{page}-c{col}-r{row}" value="Box text here" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#FFF2CC;strokeColor=#D6B656;fontFamily=Calibri;fontSize=11;align=center;verticalAlign=middle;spacingLeft=6;spacingRight=6;spacingTop=2;spacingBottom=2;" parent="1" vertex="1">
    <mxGeometry x="100" y="100" width="200" height="86" as="geometry"/>
</mxCell>
```

- `rounded=1` gives soft corners
- Minimum box height: 86px (~0.9 inches)
- `spacingLeft=6;spacingRight=6;spacingTop=2;spacingBottom=2` for internal margins
- For bold text (final-column boxes): add `fontStyle=1` to the style string

#### Arrow / Edge (Between Columns)

```xml
<mxCell id="arrow-{source}-{target}" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#C8C8C8;strokeWidth=1.5;endArrow=block;endFill=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="box-{page}-c{col}-r{row}" target="box-{page}-c{col+1}-r{row}" edge="1">
    <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

- Orthogonal routing with grey stroke
- Arrows connect from right edge of source box to left edge of target box
- Each box in column N connects to every box in column N+1 (fan-out), unless the causal logic specifies otherwise

#### Overview Tile with Page Link

```xml
<UserObject label="Subpage Name" link="data:page/id,page-{subpage-slug}" id="tile-{subpage-slug}">
    <mxCell style="rounded=1;whiteSpace=wrap;html=1;fillColor=#DAE8FC;strokeColor=#6C8EBF;fontFamily=Calibri;fontSize=12;align=center;verticalAlign=middle;fontStyle=1;" parent="1" vertex="1">
        <mxGeometry x="100" y="200" width="200" height="60" as="geometry"/>
    </mxCell>
</UserObject>
```

- `link="data:page/id,{pageId}"` creates an internal page link
- The `{pageId}` must match the `id` attribute of the target `<diagram>` element

#### White Box with Grey Top Rule

For white boxes (Final Outcomes, etc.), draw a thin grey rectangle above the box as a visual top rule:

```xml
<mxCell id="rule-{box-id}" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#CCCCCC;strokeColor=none;" parent="1" vertex="1">
    <mxGeometry x="100" y="97" width="200" height="3" as="geometry"/>
</mxCell>
<mxCell id="box-{id}" value="Outcome text" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#FFFFFF;strokeColor=#CCCCCC;fontFamily=Calibri;fontSize=11;align=center;verticalAlign=middle;spacingLeft=6;spacingRight=6;spacingTop=2;spacingBottom=2;" parent="1" vertex="1">
    <mxGeometry x="100" y="100" width="200" height="86" as="geometry"/>
</mxCell>
```

- The rule is a 3px-tall filled rectangle immediately above the box
- `strokeColor=none` on the rule so only the fill shows

#### Top-Right Page Note

```xml
<mxCell id="note-{page}" value="Illustrative only" style="text;html=1;align=right;verticalAlign=top;whiteSpace=wrap;rounded=0;fontFamily=Calibri;fontSize=12;fontColor=#787878;" parent="1" vertex="1">
    <mxGeometry x="{PAGE_WIDTH - 230}" y="10" width="220" height="60" as="geometry"/>
</mxCell>
```

- Right-aligned, Calibri 12pt, muted grey `#787878`
- Max 4 lines; widen leftwards (up to ~280px) if needed; do not reduce font size
- Placed on every page (Overview, Final Outcomes, subpages, "What is a DoView?", Sources)

#### Footer

```xml
<mxCell id="footer-{page}" value="Disclaimer text | Generated 2025-01-01" style="text;html=1;align=center;verticalAlign=bottom;whiteSpace=wrap;rounded=0;fontFamily=Calibri;fontSize=9;fontColor=#999999;" parent="1" vertex="1">
    <mxGeometry x="30" y="{PAGE_HEIGHT - 40}" width="{PAGE_WIDTH - 60}" height="30" as="geometry"/>
</mxCell>
```

- Center-aligned, Calibri 9pt, `fontColor=#999999`
- Positioned near the bottom of the page

#### Page Title

```xml
<mxCell id="title-{page}" value="Page Title" style="text;html=1;align=left;verticalAlign=top;whiteSpace=wrap;rounded=0;fontFamily=Calibri;fontSize=18;fontStyle=1;" parent="1" vertex="1">
    <mxGeometry x="30" y="10" width="500" height="40" as="geometry"/>
</mxCell>
```

### ID Naming Convention

Use descriptive, deterministic IDs throughout:
- Pages: `page-overview`, `page-final-outcomes`, `page-{subpage-slug}`, `page-what-is-doview`, `page-sources`
- Boxes: `box-{page}-c{col}-r{row}` (e.g., `box-marketing-c2-r1`)
- Arrows: `arrow-{source-id}-{target-id}`
- Titles: `title-{page}`
- Footers: `footer-{page}`
- Notes: `note-{page}`
- Tiles: `tile-{subpage-slug}`
- Rules: `rule-{box-id}`

Slugify subpage names: lowercase, spaces→hyphens, remove special characters.

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

### Overview Page Rules

1. **Page title** at top-left
2. **Raised Final Outcomes box** centered above the tile grid:
   - Width: ~60% of content width
   - Style: White fill with `shadow=1` added to style
   - Wrapped in `<UserObject>` with `link="data:page/id,page-final-outcomes"`
   - Grey top rule above it
3. **Divider line** between raised box and tile grid:
   ```xml
   <mxCell id="divider-overview" style="line;strokeColor=#CCCCCC;strokeWidth=1;" parent="1" vertex="1">
       <mxGeometry x="30" y="{divider_y}" width="{PAGE_WIDTH - 60}" height="1" as="geometry"/>
   </mxCell>
   ```
4. **Tile grid**: 3 columns
   - Margins: 30px from content edges
   - Horizontal gap between tiles: 20px
   - Vertical gap between tiles: 15px
   - Tile width = (content_width − 2 × 20) / 3
   - Each tile linked to its subpage via `<UserObject>`
   - Cycle through non-white colors (one per tile)
   - **Do NOT include Final Outcomes in the tile grid**

### Final Outcomes Page Rules

- Simple vertical stack of final outcome boxes, centered horizontally
- Box width: ~60% of page width
- White fill with grey top rule on each box
- Vertical gap: 12px between boxes
- Maximum 7 boxes per page
- If more than 7, auto-paginate: "Final Outcomes [1]", "Final Outcomes [2]", etc.
- If only one page, no "[1]" suffix
- No arrows, no multi-column layout

### Content Subpage Rules

- Left-to-right column flow with arrows between columns
- Column width = (content_width − (num_columns − 1) × 50) / num_columns, redistributed by box density
- Boxes within a column are stacked vertically with 12px gaps
- Each subpage uses one color from the non-white palette (cycling in order)
- Final-column boxes are bold (`fontStyle=1`)
- Arrows connect each box in column N to related boxes in column N+1
  - Default: fan-out from every box in column N to every box in column N+1
  - Adjust per causal logic when relationships are specific

### Sources Page Rules

- Two-column layout for source entries
- Each source rendered as a clickable link via `<UserObject>`:
  ```xml
  <UserObject label="{source title}" link="{url}" id="source-{n}">
      <mxCell style="text;html=1;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontFamily=Calibri;fontSize=10;fontStyle=4;fontColor=#0000FF;" parent="1" vertex="1">
          <mxGeometry x="..." y="..." width="..." height="30" as="geometry"/>
      </mxCell>
  </UserObject>
  ```
- `fontStyle=4` for underline styling on links
- Auto-paginate if sources exceed page capacity
- Pagination: "Sources [1]", "Sources [2]"; omit number if single page

### Horizontal Space Allocation
- Treat horizontal space as a shared budget for all columns on that page
- If boxes in the right-hand column(s) would spill off the page, look for columns that could be made narrower
- Target columns whose boxes are relatively short and leave empty vertical space (often later columns) to make those columns narrower

### Vertical Space Allocation
- Identify "tall" columns that would overrun the bottom
- First try to make that column wider (so each box is shorter) by stealing width from shorter columns
- Only consider moving some boxes to an earlier/later column or splitting that logic into two columns
- Prefer wording changes and reallocation of width between columns over simply adding more columns or accepting overflow

### Fit Check Before XML Generation
For each subpage, verify:
- "Would any column of boxes plausibly stick out past the right-hand edge?" (past PAGE_WIDTH − 30)
- "Would any column's stack of boxes plausibly run below the bottom boundary?" (past PAGE_HEIGHT − 50)

If yes, apply reallocation strategies before generating XML.

### XML Encoding Rules
In `value` attributes:
- `<` → `&lt;`
- `>` → `&gt;`
- `&` → `&amp;`
- `"` → `&quot;`

For HTML markup within values (bold text, line breaks):
- Bold: `&lt;b&gt;Text&lt;/b&gt;`
- Line break: `&lt;br&gt;`

These are entity-encoded because they appear inside XML attribute values.

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

Render this as a single text cell covering the content area, with `whiteSpace=wrap;html=1;` and appropriate font size (e.g., Calibri 13pt).

---

## Balance and Quality Checks

Before finalizing any DoView:
1. Balance the level of detail across subpages; add boxes where needed so subpages have similar granularity
2. Scan the set of subpages for repeating patterns that shouldn't be there
3. Ensure structural variety reflects the unique logic of each domain area
4. Verify all outcomes use proper "-ed" phrasing
5. Confirm one concept per box throughout
