# Naveen Kumar — DevOps Portfolio

Futuristic AI-themed single-page portfolio. Dark + cyan aesthetic with animated particle network.

## 🚀 Live in 2 Minutes

1. Push this folder to GitHub (see below)
2. Connect to [vercel.com](https://vercel.com) → Import repo → Deploy
3. Done — live at `yourname.vercel.app`

---

## ✏️ How to Update Content

**Everything is in one place.** Open `index.html` and find the `CONFIG` object near the bottom
(search for `★  PORTFOLIO CONFIG`). Edit the values there — the whole site updates automatically.

### Quick reference

| What to update          | Where in CONFIG        |
|-------------------------|------------------------|
| Name, title             | `name`, `title`        |
| Typewriter job titles   | `titles: [...]`        |
| Years / projects / certs count | `stats: {...}` |
| Email, LinkedIn, GitHub | `contact: {...}`       |
| Skills & tech stack     | `skills: [...]`        |
| Work history            | `experience: [...]`    |
| Projects                | `projects: [...]`      |
| Certifications          | `certifications: [...]`|

### Example — adding a project

```js
{
    num:         "04",
    title:       "Zero-Downtime K8s Migration",
    description: "Migrated 20+ microservices from ECS to EKS with zero downtime using blue/green deployments and ArgoCD.",
    tags:        ["Kubernetes", "ArgoCD", "AWS", "Terraform"],
    github:      "https://github.com/naveenkumar/k8s-migration",
    demo:        null
}
```

### Example — updating stats

```js
stats: {
    experience:     5,     // shows "5+"
    projects:       20,    // shows "20+"
    certifications: 4      // shows "4"
}
```

---

## 📤 Push to GitHub

```bash
cd portfolio

git init
git add .
git commit -m "initial portfolio"

# Create a repo on github.com first, then:
git remote add origin https://github.com/YOUR_USERNAME/portfolio.git
git push -u origin main
```

## 💻 Continue on Another Laptop

```bash
git clone https://github.com/YOUR_USERNAME/portfolio.git
# Open index.html in a browser — no install needed
```

## 🔄 Daily workflow

```bash
git pull               # get latest before starting
# ... make edits ...
git add .
git commit -m "update projects section"
git push               # Vercel auto-deploys on push
```

---

## 🔗 Add to LinkedIn

1. LinkedIn profile → **Edit intro** → **Website** → paste your Vercel URL
2. Also add to **Featured** section for maximum visibility

---

## 📁 File structure

```
portfolio/
└── index.html   ← entire portfolio in one file
└── README.md    ← this file
```

No dependencies. No build tools. No Node.js required. Just open `index.html` in a browser.
