# DoView Planning Skills

Claude Code skills for generating DoView strategy/outcomes diagrams (theory of change visualizations).

## What is DoView?

DoView is a visual diagram methodology that shows the theory of change for an initiative, program, or strategy. It maps causal relationships between activities, outputs, and outcomes, flowing left-to-right to show how earlier achievements lead to later results.

*DoView is Open and Free to Use.* The methodology is open and free for anyone to use. You just need to acknowledge that you are using DoView Planning and building DoView diagrams. See the **Attribution** section below.

## Available Skills

| Skill | Output Format | Path |
|-------|--------------|------|
| **doview** | PowerPoint (`.pptx`) | [`skills/doview/SKILL.md`](skills/doview/SKILL.md) |
| **doview-drawio** | draw.io (`.drawio`) | [`skills/doview-drawio/SKILL.md`](skills/doview-drawio/SKILL.md) |

### doview (PowerPoint)

Generates Python code using `python-pptx` to produce a PowerPoint presentation. Requires `pip install python-pptx`.

### doview-drawio (draw.io)

Generates draw.io XML directly — no code execution or dependencies required. The output `.drawio` file can be opened in [draw.io](https://app.diagrams.net), diagrams.net, or the VS Code draw.io extension.

**Why draw.io?** Because `.drawio` files are plain XML, CLI coding agents like Claude Code can read, write, and edit them directly in your IDE. This means you can have a fully interactive workflow — create a DoView, preview it in your editor, then ask the agent to make changes through conversation:

- "Move the 'Funding secured' box to column 3"
- "Add a new outcome between 'Staff trained' and 'Service delivered'"
- "Split the 'Operations' subpage into two pages"
- "Change the color scheme on the overview page"
- "Rename all boxes on the Governance page to use British spelling"

No context switching, no manual editing — just describe what you want changed and the agent updates the XML in place. Combined with a draw.io preview extension (such as the [VS Code draw.io extension](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio)), you get a live visual feedback loop: ask, update, preview, iterate.

## How It Works

Both skills follow the same three-stage interactive workflow:

1. **Setup questions** — understand your initiative, naming, scope, and preferences
2. **Subpage structure** — draft and refine the high-level page layout with user approval
3. **Detailed content** — develop box content using "This-Then" causal logic, then generate the output file

After generation, the draw.io skill supports ongoing refinement — keep the conversation going to reshape the diagram iteratively.

## Features

- Interactive question-based workflow with user checkpoints
- "This-Then" causal logic for outcome mapping
- Outcome-focused phrasing (ending in "-ed")
- Automatic page/slide ordering and layout
- Color-coded boxes with proper formatting
- Arrow connectors showing causal flow
- Overview, Final Outcomes, and Sources pages
- Configurable spelling, disclaimers, and page dimensions
- **draw.io**: post-generation editing via natural language conversation
- **draw.io**: no runtime dependencies — output is pure XML

## Installation

Copy the `SKILL.md` file for the skill you want into your Claude Code commands directory:

```bash
# PowerPoint skill
cp skills/doview/SKILL.md ~/.claude/commands/doview.md

# draw.io skill
cp skills/doview-drawio/SKILL.md ~/.claude/commands/doview-drawio.md
```

Then invoke with `/doview` or `/doview-drawio` in Claude Code.

## Attribution

This skill is adapted from [DoViewPlanning.org](https://www.doviewplanning.org) – AI DoView Drawing Prompt, created by Dr Paul Duignan.

DoView® is a registered trademark. Use of DoView® Marks must comply with the DoView® Planning [Attribution & Trademark Use Policy](https://www.doviewplanning.org/trademarkuse) on DoViewPlanning.org.

## License

Free to use, copy, share, and adapt for any purpose (including commercial) with attribution. See the skill files for full terms.
