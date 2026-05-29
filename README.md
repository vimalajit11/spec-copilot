# SpecCopilot

A working AI tool that turns a one-line feature idea into a structured PRD — problem, user stories, acceptance criteria, success metrics, and a RICE score. Built as a working demo for the Razorpay Full-Stack AI PM role.

It's a single static file (`index.html`). No build step, no backend.

## Two modes

- **Demo mode (default):** with no API key set, clicking *Generate* returns a real, pre-written PRD instantly. Anyone opening the link sees polished, functional output — good for a recruiter clicking cold.
- **Live mode:** click the **Demo mode** pill (top-right), paste your own Anthropic API key, and it generates live via the Claude API (`claude-sonnet-4-6`). Your key is stored **only in your browser** (`localStorage`) — it is never written into the file, committed, or sent anywhere except `api.anthropic.com`.

## Export

Every generated PRD (demo or live) can be exported:
- **Copy Markdown** — one click to clipboard, ready to paste into Notion, Confluence, Jira, or Slack.
- **Download .md** — saves a clean Markdown file named after the PRD title.

## Why bring-your-own-key (and not a hardcoded key)

A public static site can't hold a secret. If you paste an API key into `index.html` and push it to a public repo, anyone can read it from the page source and run up charges on your account. The bring-your-own-key + demo-mode design avoids that entirely: cold visitors get the demo result, and you generate live with your own key on your own machine.

For a live demo in an interview or a screen recording, just open the page, click the pill, paste your key, and go. Set a low monthly spend cap on that key at console.anthropic.com for peace of mind.

## Deploy to GitHub Pages (your stack)

1. Create a public repo, e.g. `spec-copilot`.
2. Add this `index.html` at the repo root and push.
3. Repo → **Settings → Pages → Source: "Deploy from a branch" → `main` / `root`** → Save.
4. Live in ~1 minute at `https://<your-username>.github.io/spec-copilot/`.

Vercel or Netlify work identically — drag the folder in, done.

## What to do with the link

- Drop it in the Razorpay application ("a working demo I built: …").
- Include it in your VTU-alum / hiring-manager outreach.
- In an interview, screen-share it live with your key entered, then talk through how you'd extend it (multi-step agent, Jira push, eval harness on the output quality).
