# Installation reference

## Choose the variant

| Project | Variant suffix |
|---|---|
| JavaScript + plain CSS | `JS-CSS` |
| JavaScript + Tailwind | `JS-TW` |
| TypeScript + plain CSS | `TS-CSS` |
| TypeScript + Tailwind | `TS-TW` |

React Bits registry names use the PascalCase component name followed by the suffix, for example `BlurText-TS-TW` and `SplitText-JS-CSS`.

## Preferred shadcn commands

Use the package manager already locked by the target project:

```bash
npx shadcn@latest add @react-bits/BlurText-TS-TW
pnpm dlx shadcn@latest add @react-bits/BlurText-TS-TW
yarn shadcn@latest add @react-bits/BlurText-TS-TW
bun x --bun shadcn@latest add @react-bits/BlurText-TS-TW
```

Replace `BlurText-TS-TW` with the confirmed component and variant. The URL form is also supported:

```bash
npx shadcn@latest add https://reactbits.dev/r/BlurText-TS-TW
```

## jsrepo alternative

Use jsrepo when the project already uses it or the shadcn registry cannot be used:

```bash
npx jsrepo@latest add https://reactbits.dev/r/BlurText-TS-TW
pnpm dlx jsrepo@latest add https://reactbits.dev/r/BlurText-TS-TW
```

Both methods fetch component source. Do not add `react-bits` as a normal npm runtime dependency.

## Manual fallback

When CLI installation is blocked:

1. Open the component's page at `https://reactbits.dev/<category>/<component-slug>`.
2. Select the project's language and styling variant.
3. Copy every component and stylesheet file shown by the documentation.
4. Install only the dependencies listed for that component.
5. Preserve the target project's import aliases and directory conventions.

## Pre-install checks

- Confirm the target directory is the intended React project.
- Read the lock file to determine npm, pnpm, Yarn, or Bun.
- Check `components.json` when using shadcn so generated paths and aliases are predictable.
- Search for the component name and destination filename before installing.
- Record the pre-install git status and do not mix unrelated edits.

## Post-install checks

- Inspect the added component source and CSS.
- Confirm all new imports resolve and peer dependencies match the React version.
- Run the project's build/typecheck and targeted lint.
- Test interactive effects with pointer, touch, keyboard, and reduced motion as applicable.
