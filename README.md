# Emmanuel Chibuikem — Portfolio V5

Premium React/Vite portfolio focused on cybersecurity and software engineering.

## Stack
React 19 · Vite 7 · Framer Motion · Lucide React · CSS

## Run
```bash
npm install
npm run dev
```

## Build
```bash
npm run build
npm run preview
```

## Structure
```text
src/
├── assets/headshot.png
├── components/
│   ├── CursorGlow.jsx
│   ├── Navbar.jsx
│   └── SectionLabel.jsx
├── data/
│   ├── projects.js
│   └── skills.js
├── sections/
│   ├── About.jsx
│   ├── Contact.jsx
│   ├── Hero.jsx
│   ├── Projects.jsx
│   └── Skills.jsx
├── App.jsx
├── index.css
└── main.jsx
```

## V4 → V5 fixes
The V4 capability console used invalid JSX: `<skillGroups[active].icon />`. V5 resolves the icon first with `const ActiveIcon = current.icon` and renders `<ActiveIcon />`. The monolithic App was also split into reusable sections and data modules.

## Deployment
Vercel: build command `npm run build`; output directory `dist`.

## Personal links
GitHub: https://github.com/Brunomarcel1901
LinkedIn: https://www.linkedin.com/in/emmanuel-ughaogu-457929346
Email: ughaoguemmanuel@gmail.com

## Content note
Project descriptions are intentionally conservative. Add only verified metrics, certifications and claims before publishing.
