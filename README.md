# 🎨 SCSS Color Scheme

A **semantic color token system** defined as an SCSS mixin for building consistent and scalable UI.

This file (`scheme.scss`) provides a structured set of CSS variables covering:

* brand colors
* background layers
* text hierarchy
* borders
* status states
* shadows

---

## 🧠 Concept

this system uses **semantic variables**:

```text
color = purpose + state
```

Example:

```scss
--color-background-secondary
--color-background-secondary-hover
```

This ensures:

* consistency across components
* predictable usage
* easier scaling and theming

---

## ⚙️ Usage

Import the mixin and apply it at root level:

```scss
@use 'dark-scheme.scss' as dark;
@use 'light-scheme.scss' as light;

:root {
    .dark-mode {
        @include dark.color-mixin();
    }

    .light-mode {
        @include light.color-mixin();
    }
}
```

Then use variables in your components:

```scss
.card {
  background: var(--color-background-secondary);

  &:hover {
    background: var(--color-background-secondary-hover);
  }
}
```

---

## 🧩 Structure Overview

### Brand

Primary and secondary action colors (buttons, highlights)

### Background

Layered surfaces:

* primary → base/elevated
* secondary → cards/containers
* tertiary → nested layers
* muted → low emphasis

Each supports hover states.

---

### Text

Defines hierarchy:

* primary → main content
* secondary → supporting text
* muted → hints / metadata
* inverse → for dark/colored backgrounds

---

### Border

* primary → default borders
* secondary → subtle separators
* focus → active states

---

### Status

Includes full variants for:

* success
* warning
* error
* info

Each has:

* foreground
* background
* border
* hover + muted states

---

### Effects

Shadow system:

* sm / md / lg → elevation levels
* button → interactive shadows

---

## 💡 Notes

* `muted` = low emphasis (not disabled)
* Hover states should follow a consistent visual delta
* All tokens are reusable across components (not tied to specific layouts)

---

## 🚀 Goal

Provide a **predictable and scalable color system** that works well in:

* complex UIs
* multi-developer environments
* future theming setups

---
