# Jatin Kumar – Personal Portfolio

A premium, multi-page portfolio built with **only HTML5, CSS3 and vanilla JavaScript**. No frameworks, no build step, no installs.

## Folder structure

```
jatin-portfolio/
├── index.html         Home
├── about.html         About Me
├── skills.html        Skills & Technologies
├── experience.html    Work Experience
├── projects.html      Projects
├── education.html     Education & Certifications
├── contact.html       Contact
├── css/
│   ├── style.css      Design system (colors, cards, buttons, animations)
│   └── responsive.css Mobile / tablet layout + mobile menu
├── js/
│   └── script.js      All interactivity (typing, reveal, particles, form…)
├── assets/
│   ├── profile.png    ← YOU add this later (see below)
│   └── images/        Abstract project illustrations (SVG)
└── README.md
```

## Run it locally

**Easiest:** double-click `index.html`. It opens in your browser and everything works.

**Recommended (acts like a real website):**
1. Install Python from python.org if you don't have it.
2. Open a terminal inside the `jatin-portfolio` folder.
3. Run `python -m http.server 8000`
4. Open <http://localhost:8000> in your browser. Press `Ctrl+C` in the terminal to stop.

(Or, in VS Code, install the "Live Server" extension, right-click `index.html` → *Open with Live Server*.)

## Add your photograph later

1. Choose a clear, square-ish photo (at least 600×600 px).
2. Save it as **`profile.png`** inside the `assets/` folder (exact name, lowercase).
3. Refresh the page. The animated **JK** initials are replaced by your photo automatically, on the Home and About pages.
4. Delete the file any time and the JK initials return.

If it doesn't appear, check the name is exactly `profile.png` (not `profile.png.png` or `Profile.PNG` — GitHub Pages is case-sensitive), then hard-refresh with `Ctrl+Shift+R`.

## Things to review and edit

I only used facts you gave me. A few items are generic and **you should check them**:

- **Projects page** – the descriptions and technology tags (e.g. "Python", "AI") for KRITI AI Assistant, Cybersecurity Toolkit and Networking & Security Labs are reasonable placeholders. Edit them in `projects.html` so they match what you actually built. Each GitHub button points to your profile; once a project has its own repository, replace that button's `href` with the repo URL.
- **Skills page** – the short descriptions are generic (no levels or percentages). Adjust the wording if you like.
- **Certifications** – add real, verifiable ones in `education.html` (a commented template is included).
- **Education** – add your college name and dates in `education.html` only when you want them shown.

## Connect the contact form (important)

A website made of only HTML/CSS/JS **cannot send email by itself**. Right now the form validates the fields and then tells the visitor honestly that no message was sent. To really receive messages, connect a form service. The easiest free option:

**Option A – Formspree (no code)**
1. Create a free account at formspree.io and create a new form. You'll get a URL like `https://formspree.io/f/xxxxxxx`.
2. In `contact.html`, find `<form id="contact-form" ... data-endpoint="">` and paste the URL between the quotes:
   `data-endpoint="https://formspree.io/f/xxxxxxx"`
3. Save, upload, and send a test message. Formspree emails it to you (confirm your email with them first).

**Other options:** Web3Forms, Getform, Netlify Forms (if hosting on Netlify), or EmailJS. Any service that accepts a `POST` of form data and returns a JSON/200 response works with the same `data-endpoint` setting. If you ever build your own backend, point `data-endpoint` at it and validate the input again on the server.

## Deploy free on GitHub Pages

1. Sign in at github.com (your username is `cyber370`).
2. Click **New repository**. Name it `jatin-portfolio` (or `cyber370.github.io` to get the shortest URL). Set it to **Public** and create it.
3. On the repository page click **uploading an existing file**, drag in **the contents** of the `jatin-portfolio` folder (all HTML files plus the `css`, `js`, `assets` folders — `index.html` must be at the top level), and click **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, choose branch **main** and folder **/ (root)**, then **Save**.
5. Wait 1–3 minutes. Your site appears at `https://cyber370.github.io/jatin-portfolio/` (or `https://cyber370.github.io/` if you used that repo name).
6. To update later: open a file in the repo, click the pencil icon, edit, and commit — or upload the new `assets/profile.png`.

## Troubleshooting

| Problem | Fix |
|---|---|
| Page looks unstyled | Keep the folder layout exactly as above. `css/style.css` must sit in a `css` folder next to the HTML files. |
| Page is blank for a moment | Normal fade-in. If it stays blank, `js/script.js` may be missing or have a typo — it shows itself automatically after ~1.5 s as a safety net. |
| Photo doesn't show | File must be `assets/profile.png`, exact name and case. Hard-refresh (`Ctrl+Shift+R`). |
| GitHub Pages shows 404 | Make sure `index.html` is in the repo root, Pages is enabled on `main`, and wait a few minutes. |
| Changes don't appear online | Hard-refresh; GitHub Pages can take a minute or two to update. |
| Form says "message was NOT sent" | That is expected until you add a `data-endpoint` (see above). |
| Animations feel slow on an old device | Remove `<canvas id="matrix">` from `index.html` or the `initParticles()` call at the bottom of `js/script.js`. Visitors who enable "reduce motion" in their OS automatically get minimal animation. |

## Customising the look

All colors live at the top of `css/style.css` under `:root` (`--neon`, `--black`, `--charcoal`, …). Change `--neon` to restyle the whole site.
