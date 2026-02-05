# DoView Planning Skill

A Claude skill for generating DoView strategy/outcomes diagrams in PowerPoint format.

## What is DoView?

DoView is a visual diagram methodology that shows the theory of change for an initiative, program, or strategy. It maps causal relationships between activities, outputs, and outcomes, flowing left-to-right to show how earlier achievements lead to later results.

## Usage

*DoView is Open and Free to Use.*

The DoView Planning methodology is open and free for anyone to use. The methodology is easy to use in PowerPoint or Google Slides. You just need to acknowledge that you are using DoView Planning and building DoView diagrams if you do. DoView Planning can provide a top-end to project planning, and could be vertically integrated into project planning platforms and other widely used systems. 

You are encouraged to use the terms DoView Planning and DoViews, with acknowledgment, just as long as you do not imply endorsement by us. See **Attribution** section for appropriate acknowledgment and use.

### Getting Started

Add the `SKILL.md` file to your Claude custom instructions or project knowledge to enable DoView diagram generation.

When activated, the skill will:

1. **Ask 8 setup questions** to understand your requirements
2. **Create subpage structure** with user approval checkpoints
3. **Develop detailed content** using "This-Then" causal logic
4. **Generate Python code** using `python-pptx` to create PowerPoint slides

## Features

- Interactive question-based workflow
- Outcome-focused phrasing (ending in "-ed")
- Automatic slide ordering and layout
- Color-coded boxes with proper formatting
- Arrow connectors showing causal flow
- Overview, Final Outcomes, and Sources slides
- Configurable spelling and disclaimer text

## Requirements

For PowerPoint generation, you'll need:

```bash
pip install python-pptx
```

## Attribution

This skill is adapted from [DoViewPlanning.org](https://www.doviewplanning.org) – AI DoView Drawing Prompt, created by Dr Paul Duignan. 

DoView® is a registered trademark. Use of DoView® Marks must comply with the DoView® Planning [Attribution & Trademark Use Policy](https://www.doviewplanning.org/trademarkuse) on DoViewPlanning.org.

## License

Free to use, copy, share, and adapt for any purpose (including commercial) with attribution. See the skill file for full terms.
