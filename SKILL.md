---
name: product-flow-ux-analysis
description: Analyze product UX and user execution flows from screenshots, links, prototypes, or live pages. Use when the user wants to deeply experience a product, map user journeys, identify friction points, evaluate feature value vs redundancy, and produce structured UX reports or HTML documents.
---

# Product Flow UX Analysis

## Overview

Use this skill to analyze a product by following the user's real execution flow, not by listing screens in isolation. The output should explain what the user is trying to accomplish, which product functions appear at each stage, where the flow is smooth or confusing, and what practical changes would improve the experience.

This skill is especially suited for screenshot/link based product teardown, competitor UX analysis, AI product workflow analysis, travel/productivity tools, dashboards, onboarding flows, planning tools, and multi-step user workflows.

## Core Principle

Analyze from the user's journey first, feature inventory second.

Do not only describe what is visible on the screen. Explain:

- What stage of the user's task this screen belongs to
- What the user is trying to decide or complete
- Which functions support that task
- Which functions feel redundant, premature, hidden, or too heavy
- How the product could use agent/AI capabilities to reduce user effort

## Workflow

### 1. Establish The User Journey

Start by building a lifecycle map before detailed screen analysis. For travel/planning products, use this default journey unless the product suggests another:

1. Pre-trip inspiration and rough planning
2. Detailed itinerary construction
3. Booking and confirmation
4. In-trip use
5. Navigation and viewing, including offline access when relevant
6. Real-time recording and adjustment
7. Post-trip整理, sharing, exporting, or reflection

For other products, adapt the lifecycle to the domain, but preserve the logic:

```text
Need appears -> rough exploration -> structured setup -> execution -> monitoring/adjustment -> completion -> sharing/export/reflection
```

For each stage, map:

- User goal
- Typical user actions
- Product modules used
- Key decision points
- Potential friction

### 2. Analyze Each Screen Or Module

For every screenshot, link, or page state, structure the analysis as:

- **Page/module goal**: what this screen should help the user accomplish
- **User execution flow**: the steps a user naturally takes
- **Function inventory**: visible controls, inputs, menus, tabs, actions
- **Value**: what each function helps with
- **Friction/cost**: why the user may hesitate, get confused, duplicate work, or abandon
- **UX judgment**: whether the function is necessary for mainstream users, only useful for advanced users, or redundant
- **Improvement**: concrete changes that could be built

Prefer tables when comparing multiple controls or modules.

### 3. Separate Objective Description From Product Critique

First describe the product's likely intent fairly. Then add the critique.

Example:

```text
The overview "places" module can act as a candidate pool before scheduling.

Core critique: for lightweight users, this may feel redundant because daily itinerary nodes already support adding places directly. The module should be weakened, folded, or renamed "Unscheduled places" to avoid conflict with the formal itinerary.
```

### 4. Track Redundancy And Information Architecture

Pay special attention to repeated entry points. Ask:

- Can the same action be done in multiple places?
- Do these places represent different user stages, or are they accidental duplication?
- Does the naming clarify the difference?
- Should a module be default, folded, renamed, or made advanced?

Common patterns:

- **Candidate pool vs scheduled item**: useful for heavy planners, confusing for lightweight users
- **Shortcut vs menu duplicate**: okay if one is high-frequency and one is management, confusing if identical
- **AI chat vs product action**: weak if only advice, strong if it writes back into the product
- **Booking/search/import/manage**: must clearly distinguish commercial actions from record-keeping

### 5. Evaluate Agent/AI Opportunities

When the product has AI or could benefit from AI, focus on executable assistance.

Weak AI:

- Gives generic advice
- Generates text that users must manually copy
- Does not know the current product state
- Cannot write back to the workflow

Strong agentic AI:

- Asks for missing user preference signals
- Generates a first editable draft
- Explains why it made choices
- Converts answers into product actions
- Detects missing information and conflicts
- Offers one-click repair actions

Use this pattern for recommendations:

```text
User problem -> agent capability -> product action -> expected UX benefit
```

Example:

```text
User does not know which attractions to pick.
Agent asks for travel style, companions, pace, budget, and interests.
It creates a first editable itinerary with reasons and route order.
The user edits instead of starting from a blank trip.
```

### 6. Build Practical Recommendations

Recommendations must be implementable, not slogans.

Include:

- What to change in the UI
- What data or user signal is needed
- What product action should happen
- Which user segment benefits
- Whether the priority is high, medium, or low

Prefer:

```text
Add a 3-step preference capture after destination/date: interests, pace, companions/budget. Use it to generate an editable first itinerary.
```

Avoid:

```text
Improve personalization.
```

## Report Structure

Use this default structure for longer analyses:

1. **User Journey Map**
   - Stage
   - User goal
   - Typical actions
   - Product modules used
   - Experience concerns

2. **Screen/Module Analysis**
   - One section per major page or workflow
   - Include screenshots when available
   - Analyze user flow, value, friction, and improvement

3. **Key Friction Summary**
   - Cluster recurring issues instead of repeating screen-level details

4. **Agentic Improvement Opportunities**
   - Practical improvements using AI/agent capabilities
   - Explain what the agent reads, decides, and writes back

5. **Prioritized Recommendations**
   - Table with improvement, implementation idea, impacted modules, priority

## HTML Report Guidance

When the user wants a document or visual report:

- Create an HTML report in an outputs directory when available.
- Copy user-provided screenshots into the same output folder and reference them with relative paths.
- Use clean sections, tables, and captions.
- Keep screenshots near the analysis they support.
- Make sure the report can be opened directly in a browser.
- If exporting to desktop, copy the HTML and any required assets or keep assets embedded/nearby as appropriate.

## Tone And Judgment

Be direct and product-minded.

It is acceptable to say a module may be unnecessary for mainstream users when the flow supports that conclusion. Do not over-rationalize every feature. A good analysis should distinguish:

- Useful for all users
- Useful only for heavy users
- Useful but shown too early
- Redundant with another path
- Commercially useful but UX-ambiguous
- Powerful but too complex without guidance

## Common Output Phrases

Use precise language such as:

- "This is useful as a candidate pool, but conflicts with the daily itinerary mental model."
- "The product is solving a heavy-planner workflow, but default exposure may overload lightweight users."
- "The AI feature becomes stronger if it can write back into the itinerary instead of only answering questions."
- "This entry point mixes search, booking, import, and management; the UI should clarify which action the user is taking."
- "The next product step should be to turn blank-state creation into preference capture and editable first-draft generation."

## Validation Checklist

Before finalizing an analysis, check:

- Did the report follow the user's actual task flow?
- Did it map functions to user stages?
- Did it identify both value and friction?
- Did it include strong critiques where warranted?
- Did recommendations include concrete UI/data/action changes?
- If AI/agent improvements were proposed, can they write back into product state?
- If screenshots were used, are they referenced near the relevant analysis?
