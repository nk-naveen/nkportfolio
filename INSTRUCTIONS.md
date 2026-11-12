# AI Instructions — Naveen Kumar Portfolio

This file is for any AI assistant working on this portfolio.
Read this fully before making any changes.

---

## What This Project Is

A single-page futuristic portfolio for **Naveen Kumar**, a DevOps Engineer.
Built as a single file: `index.html` — all CSS, HTML, and JavaScript in one place.
No frameworks. No build tools. No dependencies. Just open in a browser.

**Live theme:** Dark background + Cyan (#00e5ff) accent. Futuristic / tech aesthetic.
**Font:** Inter (body) + JetBrains Mono (labels, code-style text).

---

## File Structure

```
naveen-portfolio/
├── index.html        ← THE entire portfolio (edit this)
├── README.md         ← Deploy and update instructions for humans
└── INSTRUCTIONS.md   ← This file (instructions for AI)
```

---

## The Golden Rule

**All content changes go inside the `CONFIG` object only.**
Search for `★  PORTFOLIO CONFIG` in `index.html` to find it.
Never hardcode content in the HTML. Always use CONFIG.

The render functions (below CONFIG) read from CONFIG and build the DOM.
Do not touch the render functions unless adding a new section type.

---

## CONFIG Structure — What Each Key Does

```js
CONFIG = {
  name:     string              // Full name shown in hero
  title:    string              // Primary job title
  titles:   string[]            // Typewriter cycles through these
  stats: {
    experience:     number|null // null shows "—", number shows "N+"
    projects:       number|null
    certifications: number|null
  }
  contact: {
    email:    string
    linkedin: string            // Full URL
    github:   string            // Full URL
    location: string
  }
  skills: [                     // Array of skill categories
    { name: string, icon: emoji, tags: string[] }
  ]
  experience: [                 // Array of jobs, newest first
    { date, role, company, description, tags: string[] }
  ]
  projects: [                   // Array of projects
    { num, title, description, tags: string[], github, demo }
  ]
  certifications: [             // Array of certs
    { icon: emoji, name, issuer, status }
  ]
}
```

---

## How to Add Content

### Add a skill tag to an existing category
Find the category by `name`, add the tag string to its `tags` array.
```js
{ name: "Cloud Platforms", icon: "☁️", tags: ["AWS", "Azure", "GCP", "NEW_TOOL"] }
```

### Add a new skill category
Append a new object to the `skills` array:
```js
{ name: "Category Name", icon: "🔧", tags: ["Tool1", "Tool2"] }
```

### Add a certification
Append to `certifications` array:
```js
{ icon: "☁️", name: "Cert Full Name", issuer: "Issuing Body", status: "Mon Year" }
```
If not yet earned, set `status: "In Progress"` or `status: "Planned"`.

### Add a project
Append to `projects` array. Increment `num` sequentially:
```js
{
    num:         "04",
    title:       "Project Title",
    description: "What it does, why it matters, what impact it had.",
    tags:        ["Tech1", "Tech2"],
    github:      "https://github.com/naveenkumar/repo",
    demo:        null             // or a URL string
}
```

### Add a job to experience
Prepend to `experience` array (newest first):
```js
{
    date:        "Mon Year – Present",
    role:        "Job Title",
    company:     "Company Name",
    description: "Key responsibilities and achievements.",
    tags:        ["Tech1", "Tech2"]
}
```

### Update stats
Replace `null` with the actual number:
```js
stats: { experience: 5, projects: 20, certifications: 4 }
```

---

## Design Rules — Always Follow These

1. **Color palette is fixed.** Cyan `#00e5ff`, accent `#00ffcc`, background `#050810`.
   Do not introduce new colors. Use existing CSS variables only.

2. **Font is fixed.** Use `var(--mono)` for labels, code hints, tags.
   Use `var(--sans)` for body text. Do not import or add new fonts.

3. **Card style is fixed.** All cards use `clip-path: polygon(...)` for the cut-corner effect.
   New cards must follow this same pattern.

4. **CSS variables are in `:root`.** If you need a new reusable value, add it there.
   Never use raw hex/rgb values in new CSS — always reference a variable.

5. **Section labels use `//` prefix** in monospace font to look like code comments.
   e.g. `// git log --career` or `// ls -la ./projects`

6. **Sections follow this HTML pattern:**
```html
<div class="section-wrap" id="sectionId">
    <div class="sec-head reveal">
        <p class="sec-label">// label</p>
        <h2 class="sec-title">Word <span>Word</span></h2>
        <div class="sec-line"></div>
    </div>
    <!-- section content -->
</div>
```

7. **All new dynamic cards must have class `reveal`** so the scroll animation applies.

8. **Keep it single-file.** Do not split into separate CSS or JS files unless the user explicitly asks.

---

## What NOT to Change

- The particle canvas animation logic
- The typewriter function
- The scroll reveal (IntersectionObserver) logic
- The navbar scroll behavior
- The `:root` CSS variables (only add to them, never rename or remove)
- The `clip-path` values on cards — they define the aesthetic
- The `CONFIG` key names — render functions depend on them exactly

---

## Adding a Whole New Section

1. Add a new key to `CONFIG` with the data array.
2. Write a `renderXxx()` function that reads `CONFIG.xxx` and builds DOM elements.
3. Add the HTML placeholder `<div class="section-wrap" id="xxx">` with the standard header.
4. Call `renderXxx()` inside the `DOMContentLoaded` block at the bottom.
5. Add a nav link in the `<ul class="nav-links">` list.

---

## Tone & Copy Style

- Section labels: lowercase, `//` prefixed, like terminal commands
- Button text: ALL CAPS with underscores, e.g. `VIEW_MY_WORK`
- Placeholder hints: wrapped in `<div class="update-hint">` or `<div class="edit-hint">`
- Descriptions: professional, first-person, achievement-focused
- No emojis in body text (emojis only in icons/category headers)

---

## Owner

**Naveen Kumar** — DevOps Engineer
Portfolio file: `index.html`
Last updated: November 2026
