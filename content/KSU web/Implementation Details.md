# Implementation Details

The KSU homepage is implemented using modern web technologies.

## Technology Stack
- **Framework:** [Next.js](https://nextjs.org/) (App Router)
- **Language:** TypeScript
- **Styling:** [Tailwind CSS](https://tailwindcss.com/)
- **Icons:** SVG / Heroicons pattern
- **Fonts:** Google Fonts (Prompt, Sarabun) via `next/font`

## Key Files
- `src/app/page.tsx`: Main homepage component.
- `src/app/layout.tsx`: Root layout with font configurations.
- `tailwind.config.ts`: Custom theme definitions (colors, fonts).

## Custom Tailwind Config
```typescript
// tailwind.config.ts (Excerpts)
theme: {
  extend: {
    colors: {
      'ksu-navy': '#003366',
      'ksu-primary': '#4AA8D8',
      'ksu-accent': '#2E8B57',
      'ksu-soft-bg': '#F4F7F9',
    },
    fontFamily: {
      heading: ['var(--font-prompt)', 'sans-serif'],
      body: ['var(--font-sarabun)', 'sans-serif'],
    },
  },
}
```

#tags #implementation #code #nextjs #tailwind
