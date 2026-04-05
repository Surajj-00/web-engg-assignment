# Web Engg Assignment — Vue 3 + Tailwind CSS

A responsive single-page application built with Vue 3, Vue Router, and Tailwind CSS v4.

---

## Tech Stack

- [Vue 3](https://vuejs.org/) — Composition API with `<script setup>`
- [Vite](https://vite.dev/) — Build tool and dev server
- [Tailwind CSS v4](https://tailwindcss.com/) — Utility-first CSS framework
- [Vue Router](https://router.vuejs.org/) — Client-side routing
- [Lucide Vue](https://lucide.dev/) — Icon library

---

## Prerequisites

Make sure you have the following installed before running the project:

- [Node.js](https://nodejs.org/) — v18 or higher
- npm — comes with Node.js

Check your versions:

```bash
node -v
npm -v
```

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Surajj-00/web-engg-assignment.git
```

### 2. Navigate into the Project

```bash
cd web-engg-assignment
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start the Development Server

```bash
npm run dev
```

Open your browser and visit: `http://localhost:5173`

---

## Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build locally |

---

## Project Structure

```
src/
├── assets/
│   ├── images/          # Logo and image files
│   └── base.css         # Global styles + Tailwind theme, layer tokens
│
├── components/
│   ├── layouts/
│   │   ├── Navbar.vue        # Top navigation with responsive sidemenu drawer
│   │   └── Footer.vue        # Footer with columns
│   │
│   ├── sections/
│   │   ├── HeroSection.vue             # Hero banner
│   │   ├── AnalyticsConvergence.vue    # Tabbed section
│   │   ├── ServiceGrid.vue             # 3x3 service cards grid
│   │   ├── StatsSection.vue            # Stats counter
│   │   ├── FaqSection.vue              # Accordion FAQ
│   │   └── CtaBanner.vue               # Call to action section
│   │
│   └── ui/
│       ├── Button.vue          # Reusable button component
│
├── views/
│   └── HomeView.vue     # Main page — assembles all sections
│
├── router/
│   └── index.js         # Route definitions
│
├── App.vue              # Root component
└── main.js              # App entry point
```

---

## Design Tokens

Custom design tokens are defined in `src/assets/base.css`:

```css
@theme {
  --color-btn-primary: #14AE5C;   /* Primary button + footer background */
  --color-footer-bg: #14AE5C;     /* Footer background */
  --color-secondary: #C3EF35;     /* Dynamic Tab Content */
  --font-sans: 'Poppins', sans-serif;       /* Main font */
  --font-stats: 'Protest Riot', sans-serif; /* Stats font */
}

@layer {
  .heading {
    @apply font-semibold text-lg md:text-2xl lg:text-3xl;  /* reusable class for heading */
  }
}

```

---

## Fonts Used

- **Poppins** — Main Font (Google Fonts)
- **Protest Riot** — Stats Counter (Google Fonts)

Both are loaded via `<link>` tags in `index.html`.

---

## Features

- Responsive layout — mobile, tablet, desktop
- Slide-in sidebar mobile navigation drawer
- Tabbed content section with active state
- FAQ accordion with smooth open/close animation
- Reusable `Button.vue` with micro interactions
- Design tokens via Tailwind v4 `@theme` `@layer`

---

## License

This project was built as part of a frontend assignment.
