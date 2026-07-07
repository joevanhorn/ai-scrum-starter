# Discovery call — Meridian Health — raw notes

*(These are the messy notes from a discovery call. Your project: turn them into a
structured solution sketch. Don't clean them up first — that's the work.)*

---

Meridian Health — disco call, ~50 min
On their side: Dana R. (CISO), Marcus T. (Dir. IT Ops), Priya S. (Compliance/Privacy Officer), + someone from clinical ops joined late (Karen? clinical apps owner)
Our side: me + SE

**Who they are**
- ~4,500 employees, 3 hospitals + a bunch of outpatient clinics
- just acquired a clinic group (~600 ppl) — "still untangling their AD" — Marcus sounded tired
- ~120 apps. Epic is the big one. also a pile of clinical systems + back-office SaaS (Workday for HR, ServiceNow, O365, some homegrown stuff)
- currently on-prem Active Directory, some ADFS for a few apps

**Why we're talking (the trigger)**
- Dana: failed an access review audit last quarter. couldn't produce "who has access to what" for the auditors in time. this is THE thing keeping her up. compliance deadline for remediation ~6 months out
- also — phishing incident 2 months ago. a clinician clicked, creds stolen, someone got into email + one clinical app before it was caught. "we got lucky it wasn't worse"
- Priya cares about HIPAA / audit evidence. wants to be able to SHOW controls, not just have them

**Current state / pain (kind of all over the place)**
- provisioning is manual. IT ticket -> someone creates accounts by hand across apps. Marcus said onboarding a nurse takes "3-5 days sometimes a week" to get all access. clinical ops HATES this — nurse shortage, every day a new hire can't work = real $
- offboarding worse. "we're honestly not sure we catch everything." contractors + travel nurses churn constantly. Dana: pretty sure there are active accounts for people who left. (this is also the audit problem)
- passwords everywhere. help desk drowning in resets. no SSO except the few ADFS apps
- MFA — they have it on VPN and email but not consistently on clinical apps. the compromised app in the phishing incident? no MFA on it
- Epic access is a whole thing — managed separately, lots of role complexity, don't fully understand it yet, need to dig in

**Things they said they want (mixed in, not prioritized by them)**
- "single place to see and manage access"
- faster onboarding — clinical ops pushed hard on this
- pass the audit / prove access reviews happen
- stop the phishing bleeding — Dana wants phishing-resistant auth, mentioned they'd heard about passwordless
- someone (Marcus?) asked about automating the joiner/leaver stuff off Workday
- Priya: audit logs, evidence, retention

**Open questions / didn't get answers**
- what's the actual timeline / budget? Dana dodged budget. audit remediation is the forcing function though (~6mo)
- how does Epic provisioning actually work today? need a follow-up specifically on Epic
- the acquired clinic group — separate AD forest? how are they going to consolidate? (Marcus wants to fold them in but no plan yet)
- who's the exec sponsor / who signs? felt like Dana but she didn't say
- do they have a preference on cloud vs keeping some on-prem? didn't ask, should have

**Vibes / notes to self**
- Dana is the champion. audit + phishing are her hot buttons. lead with those
- Marcus = day-to-day pain (provisioning toil), he'll be an internal advocate if we make his life easier
- Priya = has to be satisfied on compliance or this stalls, but not the decision maker
- clinical ops (Karen?) is the emotional/urgency angle — onboarding speed = patient care. underrated lever
- they're drowning and reactive. the audit deadline is real leverage. don't overwhelm them — they need a path, not 40 features
- didn't talk pricing at all. next step is a follow-up on Epic + a scoping session

**Next steps (agreed)**
- we send a recap + proposed approach
- follow-up call on Epic provisioning specifically
- Dana to loop in her exec sponsor for a scoping conversation
