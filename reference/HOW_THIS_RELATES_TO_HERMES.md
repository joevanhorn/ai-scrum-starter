# How this relates to Hermes

You may hear coworkers talking about **Hermes** — Nous Research's open-source
agent harness (27K+ GitHub stars as of early 2026). If someone asks how this
workshop relates to it, here's the short version.

## They're built on the same premise

Hermes exists because of one finding: hold the model constant, change the
*harness* — the instructions, constraints, memory, and orchestration around
the model — and you change the result. That is the exact thesis of this
workshop. "Most AI failures are harness problems, not model problems" is no
longer a hunch; it's a movement with a 27K-star repo behind it. When we say
we're teaching you to *be* the harness, Hermes is the infrastructure version
of the same idea.

## The difference: infrastructure vs. methodology

- **Hermes automates the harness.** It's a self-hosted runtime you install on
  a server. It builds the memory, hooks, workflows, and orchestration *for*
  you, so you don't hand-craft them.
- **This method teaches you to be the harness.** It's the thinking and the
  artifacts — VISION, CLAUDE.md, Definition of Ready, the role discipline —
  that make *any* harness produce the right thing. It works in Claude Code,
  in Hermes, in whatever ships next.

They're not competitors. They're different layers. You can run this method
inside Hermes. You can't get the method *from* Hermes.

## Where our design independently matches theirs

Worth knowing, because it's good external validation that these choices aren't
idiosyncratic:

- **Sub-agents return a structured summary to the parent.** That's our
  Engineer-to-Scrum-Master handoff format, built into their runtime.
- **Dangerous actions default to deny in delegated contexts.** That's our
  fail-safe permission posture.
- **Safety runs independently of the model's cooperation.** That's why we gate
  on a Definition of Ready and make the Scrum Master surface-not-solve — we
  don't trust the agent to behave just because the prompt asked nicely.

## Where we point past where Hermes is today

Hermes's own architects name **durable orchestration** as their next step: the
hard part is keeping a parent agent alive and steerable instead of letting it
finish and take its child agents down with it. Our Scrum Master *is* that
long-lived, steerable orchestrator — modeled as a role you play, not a piece
of infrastructure you wait for. We teach the pattern the field is reaching for.

One honest caveat: that's a *conceptual* alignment. Our Scrum Master is a
disciplined prompt-and-role pattern, not a hardened control plane that
out-engineers Hermes. The claim is "we teach the thing the field is converging
on," not "we built what they haven't."

## If someone asks you in one sentence

> "Hermes is great infrastructure for *running* long-lived agents, and it's
> built on the same premise we teach — that the harness, not the model, is
> where the leverage is. This method is the layer underneath: the thinking
> that makes any harness build the right thing."

*Note: Hermes ships fast. If you're citing specifics, a quick check of the
current release is worth it — details here reflect early-to-mid 2026.*
