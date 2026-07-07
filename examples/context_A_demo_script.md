# Project Context — Option A: Prospect Demo Script (Workforce Identity)

*Fictional context for the Option A backup. Your attendees don't build demo
tooling from scratch — they assemble a tailored demo from reusable use-cases.
This gives you the two things that make the project self-contained: a **use-case
catalog** to assemble from, and a **sample prospect** to tailor for. Paste it
alongside your VISION.*

---

## How this project works

You're a Specialist. A prospect profile lands on your desk. You pick the
use-cases that fit their priorities and assemble them into a tailored demo
script — the right stories, in the right order, with talking points that land
for *this* buyer. Your Scrum Master dispatches a sub-agent per selected
use-case to draft its section for this prospect, then assembles them into one
narrative.

The skill being demonstrated isn't writing prose — it's **selection and
sequencing**: which use-cases matter to this prospect, and in what order they
build a story.

---

## The sample prospect: Meridian Health

*(A fictional prospect. Swap in your own if you'd rather.)*

Mid-size healthcare provider, ~4,500 employees across three hospitals and a set
of clinics. Just acquired a clinic group, so headcount is churning. Runs on-prem
Active Directory with manual account provisioning across ~120 apps — an EHR
(Epic), clinical systems, and back-office SaaS.

**What's hurting them, in their words:**
- *"Get clinicians productive on day one."* A nurse waiting a week for app
  access is lost care hours — and they're already short-staffed.
- *"Pass our next audit."* They failed a recent access-review audit — couldn't
  show who had access to what.
- *"Stop the phishing bleeding."* A phishing incident compromised a clinician's
  credentials.
- *"Close the gap when contractors leave."* High traveling-nurse and contractor
  turnover leaves orphaned access behind.

**Buying committee:** CISO (phishing, audit), IT Director (provisioning toil),
Compliance Officer (HIPAA, audit evidence), Clinical Ops (onboarding speed).

---

## The use-case catalog (assemble from these)

Six Workforce Identity building blocks. Pick the ones that fit the prospect;
you won't use all six for every demo.

### 1. Single Sign-On (SSO)
- **Shows:** one login opens a dashboard of all their apps — no re-authenticating per app.
- **Addresses:** password fatigue, app sprawl, help-desk reset costs, slow access.
- **Flow:** log into Okta → app dashboard → click Epic, launches with no second login → same for a SaaS app.
- **Talking points:** day-one productivity, fewer password resets, the foundation everything else builds on.
- **Who cares:** IT Director, Clinical Ops, end users.

### 2. Adaptive / Risk-Based MFA
- **Shows:** context-aware step-up — trusted device/location is smooth; new device, new location, or a risky signal triggers a challenge.
- **Addresses:** phishing and credential theft, without blanket friction.
- **Flow:** log in from a known device → straight in. Simulate a new-location login → MFA prompt → explain the policy behind it.
- **Talking points:** phishing resistance without friction everywhere; stricter policy on sensitive apps (the EHR).
- **Who cares:** CISO, security team.

### 3. Lifecycle Management (Automated Provisioning)
- **Shows:** join / move / leave automation — add a user to a group and accounts auto-create in downstream apps; deactivate and access is revoked everywhere at once.
- **Addresses:** slow onboarding, orphaned access at offboarding, contractor churn, IT toil.
- **Flow:** add a new nurse to the "Clinicians" group → accounts provision into Epic + SaaS apps. Then deactivate a departing contractor → access removed across every app in seconds.
- **Talking points:** day-one productivity (clinician shortage), instant deprovisioning (the contractor gap), IT toil eliminated.
- **Who cares:** IT Director, Clinical Ops, CISO.

### 4. Identity Governance (Access Requests + Certifications)
- **Shows:** self-service access requests with approval workflows, plus periodic access-review campaigns that prove who has access to what.
- **Addresses:** failed audit, over-provisioned access, manual reviews, HIPAA evidence.
- **Flow:** user requests access to a clinical app → owner approves → granted. Then run a certification campaign → reviewer sees all access → revokes stale grants → audit report generated.
- **Talking points:** pass the audit that failed, least privilege, automated compliance evidence.
- **Who cares:** Compliance Officer, CISO, auditors.

### 5. Passwordless / Phishing-Resistant Auth (Okta FastPass)
- **Shows:** login with biometric or passkey — no password — and why it resists phishing.
- **Addresses:** passwords as the top attack vector; the phishing incident directly.
- **Flow:** user logs in with FastPass (Touch ID / passkey), no password typed → explain why it's phishing-resistant (device-bound, no shared secret).
- **Talking points:** remove the phishing attack surface, better UX than password + MFA, a direct answer to their incident.
- **Who cares:** CISO, security, end users.

### 6. Device Trust / Device Assurance
- **Shows:** only compliant, managed devices get access; non-compliant devices are blocked or limited.
- **Addresses:** BYOD and unmanaged devices reaching PHI.
- **Flow:** access from a managed compliant device → allowed. From an unmanaged device → blocked, or limited to low-risk apps.
- **Talking points:** protect PHI, zero-trust posture, device and identity enforced together.
- **Who cares:** CISO, security, compliance.

---

## What "Ready" looks like here

This project produces a document, not code — so a story is Ready when:

- **Acceptance criteria:** the section covers the use-case's core "show" tailored
  to a specific Meridian priority; includes the demo flow (what to show, in
  order); includes 2–3 talking points in the prospect's language; names which
  buying-committee persona it targets.
- **Definition of success:** a Specialist who's never seen this prospect could
  deliver the section and it would land for Meridian's priorities.
- **Test plan:** automated testing doesn't apply to a demo narrative, so the test
  is a **review rubric** — does the section hit every acceptance criterion above?
  (This is the "manual, and here's why" path the Definition of Ready allows.)

---

## The sprint this unlocks

Ready, self-contained, and parallel:

- **One story per selected use-case** — "Draft the tailored demo-script section
  for [use-case] for Meridian Health." These run in parallel, one sub-agent each.
- **One assembly story** — "Weave the sections into a single demo script: an
  opening hook, a logical flow across use-cases, and a close tied to Meridian's
  priorities." Runs once the sections land.
- **Output:** `DEMO_SCRIPT.md` — a real artifact the attendee watches their team
  build.

*Suggested selection for Meridian: Lifecycle, Governance, Passwordless, Adaptive
MFA, and SSO as the opener. Device Trust is a reasonable drop for a first demo —
deciding what to leave out is part of the exercise.*
