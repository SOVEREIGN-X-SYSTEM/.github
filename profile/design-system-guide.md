# Design System Guide

This guide documents the design tokens, typography, colors, shadows,
gradients, spacing, layout, accessibility, and theme architecture
extracted from the uploaded `global.css`.

## Foundations

-   Color tokens (`--gray-*`, `--accent-*`)
-   Typography tokens (`--text-*`, `--font-*`)
-   Shadows (`--shadow-sm`, `--shadow-md`, `--shadow-lg`)
-   Gradients (`--gradient-*`)
-   Layout utilities (`.wrapper`, `.stack`)
-   Spacing utilities (`.gap-*`)
-   Theme support via `.theme-dark`

## Recommended Semantic Tokens

``` css
:root {
  --color-background: var(--gray-999);
  --color-surface: var(--gray-900);
  --color-text-primary: var(--gray-100);
  --color-text-secondary: var(--gray-300);
  --color-primary: var(--accent-regular);
}
```
