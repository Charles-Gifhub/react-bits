---
name: react-bits
description: Add, install, select, integrate, customize, debug, or optimize animated React Bits components from reactbits.dev. Use when a user mentions React Bits, reactbits.dev, animated React components, interactive backgrounds, text animations, or asks to bring a React Bits effect into a React, Vite, Next.js, JavaScript, TypeScript, CSS, or Tailwind project.
---

# React Bits

Add React Bits as source-owned components that match the target project's stack and conventions.

## Workflow

1. Inspect the target project before changing it.
   - Read `package.json`, framework config, source layout, and nearby components.
   - Detect React version, JavaScript versus TypeScript, CSS versus Tailwind, package manager, and any local `AGENTS.md`.
   - Check whether the requested component or an equivalent already exists.

2. Resolve the component and variant.
   - Use the component named by the user. If the request describes an effect instead of a component, identify the closest React Bits option from its documentation or registry.
   - Select exactly one variant: `JS-CSS`, `JS-TW`, `TS-CSS`, or `TS-TW`.
   - Read [references/component-guide.md](references/component-guide.md) when choosing among effects or evaluating performance tradeoffs.

3. Install only the selected component.
   - Prefer the React Bits shadcn registry command because it copies editable source into the project.
   - Use the project's existing package manager and do not install or clone the entire React Bits website as an application dependency.
   - Read [references/installation.md](references/installation.md) for exact commands, naming rules, and fallbacks.
   - Inspect the generated files and dependency changes before integration. Preserve unrelated worktree changes.

4. Integrate with the existing UI.
   - Place the component in the project's established component directory.
   - Keep the public API from the installed component unless the user requests a wrapper or simplification.
   - Adapt imports, colors, spacing, container sizing, and content to existing tokens instead of creating a parallel design system.
   - For Next.js, add `"use client"` only where browser APIs, hooks, canvas, WebGL, or animation libraries require it.

5. Harden motion and runtime behavior.
   - Respect `prefers-reduced-motion` or provide a static/low-motion fallback for continuous or large movement.
   - Do not make essential content depend on hover, cursor position, WebGL, or animation completion.
   - Give canvas and background effects explicit container dimensions and keep foreground content readable.
   - Pause expensive animation when hidden where practical; avoid creating duplicate render loops, listeners, or WebGL contexts.
   - Preserve keyboard behavior, visible focus, semantic HTML, and sufficient contrast around interactive components.

6. Verify proportionally.
   - Run the relevant build or typecheck and targeted lint command.
   - Exercise the component at mobile and desktop widths and check browser console errors.
   - Verify reduced-motion behavior for animation-heavy components.
   - Report the installed React Bits component, chosen variant, files changed, dependencies added, and checks run.

## Guardrails

- Never guess a registry slug. Confirm the component's display name and variant before running the installer.
- Do not overwrite an existing component without inspecting the diff and preserving project-specific changes.
- Do not add React Bits effects merely as decoration when they impair reading, interaction, or performance.
- Do not claim an installation succeeded until the generated source exists and a relevant project check passes.
