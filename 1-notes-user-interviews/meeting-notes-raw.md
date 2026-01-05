MONDAY 10/7 - BUSY DAY

=== Meeting 1: Product sync w/ Jessica & Mate (9am) ===

attendees: Jessica (head of product), Mate (design), me
context: weekly product sync

- talked about Q4 priorities
- Jessica wants to push dark mode up in priority
  - "most requested feature by far"
  - engineering team asking for it (Joseph specifically)
  - might help with retention?

Mate showed initial mockups for dark mode
- looks good! really clean
- uses our existing color system
- question: what about user-uploaded images? contrast issues?
- Mate will investigate

ONBOARDING discussion:
Jessica: "we need to hit 60% activation by end of Q1"
- current: 45% (not great)
- time to first task completion: 45 min (too slow)
- competitor linear: ~15 min

ideas discussed:
- template library (pre-built projects users can start with)
- better first-run experience
- video tutorials? (Mate says maybe not, users skip videos)
- interactive tour (Mate likes this)

ACTION ITEMS:
- me: research what competitors do for onboarding (asana, linear, clickup)
- Mate: wireframes for interactive tour concept
- Jessica: talk to customer success about common activation blockers

also talked about mobile app progress
- on track for Q1 launch (good news!)
- Thomas (mobile PM) demoing beta next week

---

=== Meeting 2: Stakeholder check-in w/ Joseph (CTO) (11:30am) ===

Joseph (cto) wants to discuss notifications system

CONTEXT:
notifications are messy right now
- too many emails (users complaining)
- not enough context in notifications
- mobile notifications not working great
- users miss important updates

Joseph's perspective:
"engineering team is drowning in notifications"
- average engineer gets 40-50 notifications/day
- most are noise
- important stuff gets buried

discussed:
1. smart batching (group similar notifications)
   - Joseph: "like github does it - one email for multiple events"
   - me: makes sense, but need to define what gets batched

2. notification preferences need overhaul
   - current: binary (on/off per notification type)
   - need: granular (by project, by person, by urgency)

3. digest mode
   - batch non-urgent notifications
   - send once daily (or twice daily?)
   - Joseph: "i want morning digest, not constant interruptions"

4. timezone-aware notifications
   - don't notify at 2am!
   - respect working hours
   - Joseph mentioned they built this at his last company

TECHNICAL CONSIDERATIONS:
- notification service currently synchronous (slows down API)
- need to move to async queue (redis? kafka?)
- Joseph estimates 2 sprint effort
- need database schema changes (preferences table redesign)

CONCERNS from Joseph:
- team is at capacity (mobile app work)
- this would push dark mode back
- suggests Q2 instead of Q1?

my take: notifications are important but dark mode is more visible
Jessica might disagree - need to discuss priorities

ACTION:
- me: draft PRD for notification improvements
- me: talk to customer success - how many tickets are notification-related?
- me: competitive analysis (how do other tools handle this?)
- Joseph: technical spec if we decide to move forward

random note: Joseph mentioned engineer happiness survey results
- tools satisfaction: 7.2/10 (down from 7.8 last quarter)
- dark mode came up multiple times in comments
- performance issues mentioned (3 people)

---

=== Meeting 3: Planning session - Template Library (2pm) ===

brainstorming session for template library project
attendees: me, Mate (design), Thomas (mobile pm), jamie (eng lead)

BACKGROUND:
users take forever to get started
new user flow:
1. sign up
2. stare at empty workspace
3. ... now what?
4. manually create first project
5. manually create first tasks
6. finally start using product (45 min later!)

GOAL: get users to value faster

TEMPLATE LIBRARY CONCEPT:
pre-built project templates users can use
- "product launch"
- "sprint planning"
- "hiring pipeline"
- "content calendar"
- "bug tracking"
- etc.

discussion:

Mate: "we should show templates immediately after signup"
- modal: "choose a template to get started"
- can skip (create blank project)
- templates have real tasks, not just structure

me: "how many templates do we need?"
- Mate: "start with 5-7, expand later"
- too many = paradox of choice
- too few = not enough variety

Thomas: "mobile app should have templates too"
- consistent experience
- mobile users probably need templates more (smaller screen, harder to setup)

jamie (eng): "template data structure?"
- json files? database records?
- need versioning (templates evolve)
- need to support custom fields (templates might use them)

CONCERNS:
jamie: "templates are tricky"
- users customize templates
- template updates don't affect existing projects
- or DO they? (might be a feature!)

me: "privacy/security?"
- enterprise customers might want PRIVATE templates
- team-specific templates (not just global)
- Jessica mentioned this before

COMPETITIVE RESEARCH NOTES:
- Asana has template library (huge! 100+ templates)
  - organized by category
  - some are "certified" by Asana
  - users can create/share templates
- notion has templates (inline, good UX)
- clickup has templates (overwhelming, too many options)
- linear: NO templates (interesting! they just have blank projects)

OPEN QUESTIONS:
1. template discovery - how do users find templates?
2. template customization - edit before creating project?
3. community templates - let users share?
4. template analytics - which templates are popular?

jamie's technical estimate: 3-4 sprints
- template storage system
- template rendering logic
- UI for browsing templates
- UI for creating from template
- versioning system (if we want updates)

Thomas: "can this wait until after mobile app ships?"
- team capacity issue again
- mobile app = Q1 priority
- this might be Q2

DECISION: need to prioritize with Jessica
- is template library Q1 or Q2?
- ties into activation OKR (important!)
- but team capacity is constrained

ACTION ITEMS:
- me: write one-pager on template library (scope, goals, timeline)
- me: gather data on activation drop-off (where do users abandon?)
- Mate: quick mockups of template selection UI
- jamie: more detailed technical estimate
- Thomas: check if mobile app needs template support at launch (or later?)

---

RANDOM NOTES / PARKING LOT:

- Jessica wants to discuss API v2 roadmap next week
- customer success escalated enterprise customer asking about custom SSO
  (we have SAML but they want some other protocol? need to investigate)
- Joseph mentioned performance regression in search (looking into it)
- marketing wants to do a dark mode launch campaign (getting ahead of ourselves?)
- someone on slack mentioned competitor "motion" (haven't heard of them - need to check out)

personal reminder: need to review Thomas's mobile PRD by wednesday

UPCOMING THIS WEEK:
- tuesday: customer interview (enterprise admin from salesforce)
- wednesday: design review (dark mode final mockups)
- thursday: sprint planning
- friday: all-hands

data to pull:
- activation funnel breakdown (where are drop-offs?)
- notification ticket volume (last 3 months)
- feature request frequency (dark mode vs templates vs notifications)
- survey results (nps, user satisfaction)

---

PRIORITIES EMERGING:
1. mobile app (committed, Q1)
2. dark mode (highly requested, team morale, relatively quick)
3. activation/onboarding (OKR-critical, but what exactly?)
   - templates? interactive tour? both?
4. notifications (pain point, but complex, might be Q2)
5. enterprise features (sso variants, advanced permissions - ongoing)

need to get clarity from Jessica on what's actually Q1 vs Q2

---

FOLLOW-UPS NEEDED:
✓ competitive research on onboarding (me)
- PRD for notifications (me)
- one-pager on template library (me)
- talk to customer success re: notifications & activation (me)
- review mobile PRD (me)
- wireframes for interactive tour (Mate)
- dark mode final mockups (Mate)
- technical spec for notifications (Joseph)
- technical estimate for templates (jamie)

busy week ahead!
