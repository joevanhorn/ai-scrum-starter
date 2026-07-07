# Getting Started

You have the files. Here's how to run your own project with them, start to
finish. Five steps. No theory — you got that in the session. Just do this.

## Before you start

- **Claude Code installed and working** — run `claude`, send "say hello", get a
  reply.
- **This folder on your machine.** Open Claude Code *inside this folder* — it
  loads `CLAUDE.md` automatically, which defines the roles you'll use.
- **A project in mind.** No project? Open `examples/backup_intakes.md` and
  borrow one.

---

## Step 1 — Write your vision  (~10 min)

Open `templates/VISION_TEMPLATE.md` and fill it in for your project: who has the
problem, what it costs them, what "better" looks like (an **outcome**, not a
feature), and a short prioritized backlog. `templates/VISION_EXAMPLE.md` shows a
finished one.

This is the thinking that makes everything after it work. Don't skip it.

## Step 2 — Plan with the Architect

Open a Claude web chat (or a new Claude Code session). Paste in `CLAUDE.md` and
your filled-in VISION. Then say:

> Act as the Architect. Here's my vision. Give me a first sprint plan with
> ready, testable stories, and flag anything that needs a spike.

Push back on anything vague. **Your target:** at least one story with acceptance
criteria, a definition of success, and a test plan. Your Scrum Master will check
for exactly that.

## Step 3 — Set up to build

- Make sure you're on a branch so you have rollback:
  `git checkout -b sprint-1`
- In Claude Code, press **Shift+Tab** to turn on **accept edits** — so sub-agents
  can work without stopping you for every change. (No "accept edits" on your
  connection? Default mode is fine; you'll just approve as you go.)

## Step 4 — Kick off the Scrum Master

Open `SCRUM_MASTER_KICKOFF.md`. Copy the prompt in the box, paste it into Claude
Code, then paste your Architect's plan where it says. The Scrum Master will:

- **check your plan is ready** — if not, it tells you what's missing. Fix it and
  re-paste. (That's the system working, not a failure.)
- **spin up a team of sub-agents** to build the ready work in parallel, reporting
  back as they go.

Ask **"where are we?"** any time for a status snapshot.

## Step 5 — Stay the Product Owner

Take a status snapshot back to your Architect and ask:

> Does what we're building still serve the outcome I wrote?

Realign, re-scope, or keep going — your call. That loop, repeated, is the whole
method.

---

## When something snags

- **Plan bounced?** Expected. Add the missing acceptance criteria / test plan and
  re-paste. (See `CLAUDE.md` → Definition of Ready.)
- **Model name errors?** Tell it: *"use whatever models you have available."*
- **Worker stalled?** Tell the Scrum Master: *"nudge the worker to continue."*
- **Agent tries to fix a failure itself?** Remind it: *"surface it and wait — the
  fix is my call."*

## The five steps, in one line

**Vision → Plan with Architect → Set up a branch → Kick off Scrum Master →
Check alignment.** Repeat.
