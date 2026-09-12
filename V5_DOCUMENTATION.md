# V5 Proper Documentation

## 1. Purpose
V5 turns the working V4 portfolio into a maintainable, component-based React application. It keeps the premium dark cyber/engineering aesthetic while reducing JSX fragility and separating content from presentation.

## 2. Architecture
`main.jsx` mounts `App.jsx`. `App` owns global scroll progress and composes `CursorGlow`, `Navbar`, and the page sections. Reusable UI lives in `components/`; editable content lives in `data/`.

```text
main.jsx → App.jsx → Navbar + Hero + About + Skills + Projects + Contact
                         ↑                         ↑
                    components/                 data/
```

## 3. Components
- `Navbar.jsx`: responsive desktop/mobile navigation and menu state.
- `CursorGlow.jsx`: pointer-following ambient glow, disabled for coarse pointers/reduced motion.
- `SectionLabel.jsx`: consistent technical section labels.

## 4. Sections
- `Hero.jsx`: identity, portrait, CTA and social links.
- `About.jsx`: positioning statement and stats.
- `Skills.jsx`: interactive capability console.
- `Projects.jsx`: expandable project case-study previews.
- `Contact.jsx`: direct email and social channels.

## 5. Critical V4 bug
V4 failed at Babel parsing because JSX cannot use an expression such as:
```jsx
<skillGroups[active].icon />
```
V5 uses:
```jsx
const current = skillGroups[active];
const ActiveIcon = current.icon;
```
and then:
```jsx
<ActiveIcon />
```
This is valid dynamic component rendering in React.

## 6. Skills data
Edit `src/data/skills.js`. Each group contains `index`, `title`, `kicker`, `detail`, `icon`, and `skills`. The active group is controlled with React state.

## 7. Projects data
Edit `src/data/projects.js`. Each project contains `number`, `category`, `title`, `summary`, `stack`, and `status`. Replace the abstract terminal visual with real screenshots later under `src/assets/projects/`.

## 8. Accessibility
The navigation is labelled, the mobile menu exposes expanded state, capability buttons expose tab selection, project buttons expose expanded state, and reduced-motion preferences are respected.

## 9. Responsive behavior
At ≤900px the hero stacks, navigation switches to the mobile menu, capability navigation becomes a two-column grid, and the project detail loses the desktop indentation. At ≤620px the interface becomes single-column and typography/padding scale down.

## 10. SEO
`index.html` contains viewport, theme color, description, author, title and Open Graph basics. Before launch, add a production domain, canonical URL and a real OG image.

## 11. Verification checklist
- `npm install` succeeds.
- `npm run build` succeeds with zero errors.
- Headshot loads.
- Navigation anchors work.
- Capability tabs change content.
- Project accordion opens/closes.
- Email/GitHub/LinkedIn links work.
- Mobile menu opens/closes.
- No horizontal overflow.
- Browser console is clean.
- Replace mock project visuals with real screenshots before final publication.

## 12. Deployment
Push to GitHub and import the repository into Vercel. Use `npm run build` and `dist`. No custom backend is required for the current static frontend.

## 13. V6 roadmap
Real project screenshots, individual case-study routes, verified certifications, experience timeline, GitHub repository integration, contact form/spam protection, Lighthouse optimization, favicon/brand system and a final accessibility audit.
