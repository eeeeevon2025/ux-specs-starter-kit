# ux-specs-starter-kit
# Spec-Driven UX Starter Kit

A lightweight starter kit for designers, product teams, and AI-assisted builders who want to stop asking AI to design from vague intent.

AI can generate UI quickly.

That does not mean it knows what the interface is supposed to do.

This starter kit helps you define the user outcome, scope, constraints, states, and acceptance criteria before asking an AI agent to design or implement a product experience.

## Why this exists

AI-generated design work can look polished while still being wrong.

Common failure modes:

* The interface looks cleaner, but the primary action is still unclear.
* The layout improves visually, but the user goal is not better supported.
* The AI invents new features, routes, data, or components.
* Important edge cases are ignored.
* Empty, loading, error, and success states are missing.
* Prior product decisions are accidentally undone.
* Design review turns into taste review instead of outcome review.

Spec-driven UX creates a small layer of product intent before AI starts generating the surface.

## Use this when

Use this workflow before asking an AI agent to:

* Redesign a screen
* Improve a flow
* Create UI components
* Rewrite product copy
* Generate a product spec
* Implement a design in code
* Audit an existing experience
* Simplify a dashboard
* Create onboarding, empty states, error states, or settings experiences
* Work inside an existing product where prior decisions matter

## The basic idea

Before prompting AI to create or change a product experience, define:

1. The user outcome
2. The primary user
3. The primary action
4. The scope
5. The constraints
6. The prior decisions
7. The required states
8. The acceptance criteria

The goal is not more documentation.

The goal is to prevent vague prompts from becoming vague products.

---

# Design Intent Check

Use this before asking AI to design, redesign, or implement UI.

```md
## Design intent check

### Intended user outcome

What should the user be able to understand, decide, or do after this change?

### Primary user

Who is this experience for?

### User goal

What is the user trying to accomplish?

### Primary action

What is the most important action the interface should support?

### In scope

- What can change?
- What can be redesigned?
- What UX decisions can be revisited?

### Out of scope

- What should not change?
- What should not be added?
- What existing behavior should remain intact?

### Constraints

- Design system:
- Brand/tone:
- Accessibility:
- Responsive behavior:
- Technical limitations:
- Product or roadmap constraints:

### Prior decisions

- Decision:
  - Why it was made:
  - Preserve or revisit?

### Ambiguities

- What is unclear?
- What assumption would the AI make if this is not clarified?
- What could go wrong?
```

---

# UX Spec Template

```md
# UX Spec: [screen, flow, feature, or component]

## Outcome

[Describe what the user should be able to understand, decide, or do after this change. Focus on the user outcome, not visual preference.]

## User context

Primary user:
- [Who is using this?]

User goal:
- [What are they trying to accomplish?]

User mindset:
- [What do they likely know, not know, feel, or need at this moment?]

## Product intent

This experience should help the product:
- [Business or product goal]
- [User behavior this should support]
- [What this should make easier, faster, clearer, safer, or more trustworthy]

## In scope

- [Screen, flow, section, or component to improve]
- [UX decisions that may be revisited]
- [Copy, hierarchy, IA, layout, visual design, interaction, states, etc.]

## Out of scope for this version

- [What should not be redesigned]
- [What should not be added]
- [What behavior should not change]
- [Future idea that should not leak into this version]

## Constraints

Design system:
- [Components, tokens, patterns, file references]

Brand and tone:
- [Voice, visual direction, personality]

Accessibility:
- [Keyboard support, contrast, focus states, readable copy, screen reader expectations]

Responsive behavior:
- [Desktop, tablet, mobile expectations]

Technical constraints:
- [Routes, data, APIs, framework, unavailable functionality]

Product constraints:
- [Business, user, compliance, roadmap, or strategy limits]

## Prior decisions

- [Decision]&#58; [Why it was made. Preserve this unless explicitly told otherwise.]
- [Decision]&#58; [Why it was made. Preserve this unless explicitly told otherwise.]

## UX requirements

### Always active

- The experience SHALL make the primary user goal clear.
- The interface SHALL make the primary action visually obvious.
- The interface SHALL distinguish primary actions from secondary actions.
- The design SHALL reuse existing patterns before introducing new ones.
- The solution SHALL avoid adding features not listed in scope.
- The solution SHALL preserve prior product decisions unless explicitly instructed otherwise.

### Event-driven

- WHEN the user lands on the screen, the interface SHALL communicate what the screen is for.
- WHEN the user needs to take action, the interface SHALL make the next best action clear.
- WHEN supporting information is present, the interface SHALL make it scannable before it is detailed.
- WHEN the user completes an action, the interface SHALL provide clear confirmation.
- WHEN the user cannot continue, the interface SHALL explain why and provide a recovery path.

### State and edge case behavior

- IF data is loading, the interface SHALL show a loading state.
- IF data is unavailable, the interface SHALL show an empty state that explains what is missing and what the user can do next.
- IF an action fails, the interface SHALL explain the issue in plain language.
- IF information is uncertain, the interface SHALL label it as uncertain rather than presenting it as fact.
- IF the user lacks permission, the interface SHALL explain the limitation and available next steps.

### Content and hierarchy

- The interface SHALL use plain language over internal jargon.
- The page SHALL have one dominant purpose.
- The most important information SHALL appear before supporting detail.
- Labels, headings, and calls to action SHALL describe user value, not only system function.
- Copy SHALL be concise, specific, and action-oriented.

## Acceptance criteria

- [ ] A first-time user can explain what this screen is for within 10 seconds.
- [ ] The primary action is visually obvious.
- [ ] Secondary actions do not compete with the primary action.
- [ ] The design supports the stated user goal.
- [ ] The design does not introduce out-of-scope features, routes, data, or workflows.
- [ ] Empty, loading, error, success, and edge states are addressed.
- [ ] The solution works across required breakpoints.
- [ ] The solution uses existing design system components where possible.
- [ ] Accessibility requirements are considered.
- [ ] The final recommendation explains the product reasoning behind the design.
```

---

# EARS-style UX requirements

EARS stands for Easy Approach to Requirements Syntax.

In plain language, it helps turn vague design intent into testable behavior.

Instead of:

```md
Make the empty state more helpful.
```

Write:

```md
IF no results are available, the interface SHALL explain what was searched and provide one clear next step.
```

Instead of:

```md
Make the dashboard more actionable.
```

Write:

```md
WHEN a user lands on the dashboard, the interface SHALL make the highest-priority action visible without requiring the user to interpret every metric.
```

## Useful patterns

Always active:

```md
The interface SHALL make the primary action visually distinct from secondary actions.
```

Event-driven:

```md
WHEN the user lands on the page, the interface SHALL communicate what the page is for.
```

Unwanted behavior:

```md
IF an action fails, the interface SHALL explain what happened and provide a recovery path.
```

State-driven:

```md
WHILE data is loading, the interface SHALL show progress without shifting the layout.
```

Conditional:

```md
WHERE information is inferred, the interface SHALL label it as inferred.
```

---

# Prompt to give your AI agent

```md
Use this UX spec as the source of truth.

Before creating or changing any design, do the following:

1. Restate the intended user outcome in your own words.
2. List ambiguities, missing information, or risky assumptions.
3. Identify what is in scope and out of scope.
4. Identify any prior decisions that must be preserved.
5. Identify the required states and edge cases.
6. Do not introduce new features, routes, data, components, or workflows unless the spec explicitly allows it.

After that, propose the solution.

Your output should include:

- UX diagnosis of the current experience
- Recommended design direction
- Information hierarchy
- Primary and secondary actions
- Copy changes
- Required states
- Accessibility considerations
- Responsive behavior
- Tradeoffs and risks
- Final checklist against the acceptance criteria

Do not optimize for visual polish before solving the UX problem.

Optimize first for clarity, decision support, cognitive load, and user action.
```

---

# Optional Cursor rule

Add this file to your project:

```txt
.cursor/rules/design-spec-gatekeeper.mdc
```

Use it when working with Cursor on UX, product design, IA, flows, UI implementation, or AI-generated product surfaces.

The rule should instruct Cursor to clarify user outcome, scope, constraints, prior decisions, states, and acceptance criteria before generating or changing UI.

---

# What good looks like

A good AI-assisted design process does not start with:

```md
Make this screen better.
```

It starts with:

```md
The user needs to understand what happened, what needs attention, and what action to take next.

The primary action is to review the highest-priority issue.

Do not add new analytics, filters, or navigation.

Preserve the existing product map.

The interface must cover loading, empty, error, and success states.

The design is successful when a first-time user can explain the purpose of the screen within 10 seconds and identify the next best action without help.
```

That is the difference between asking AI for a prettier surface and giving it a product direction it can actually follow.

---

# License

Use, adapt, remix, and improve this for your own work.

Attribution is appreciated, but not required.
