# AI Ops Playbook

## QA and Testing

### 1. Automated Website and App QA Checklist Generator

**Problem:** Manual QA checklists take 45 minutes and
miss edge cases.

**Solution:** Paste a live URL or staging link and AI
generates a comprehensive checklist organized by category.

**Tools:** Claude + Screenshotone API or ChatGPT Vision

**Time saved:** 5 minutes vs 45 minutes manual

**Impact:** Junior developers catch 40% more issues
before client handoff.

**Example output:**

```
Input: https://app-staging.example.com

Output: 50-point QA checklist organized by:
- Functionality (login, forms, navigation)
- Responsive design (mobile, tablet, desktop)
- Accessibility (WCAG compliance)
- Performance (load time, image optimization)
- SEO (meta tags, structured data)
```

---

### 2. Figma Design QA Before Dev Handoff

**Problem:** Incomplete handoffs lead to 20+ developer
clarification questions per project.

**Solution:** Share a Figma link and AI audits missing
states, spacing inconsistencies, and accessibility gaps
before the file reaches development.

**Tools:** Claude Projects with Figma API or manual
screenshot upload

**Time saved:** 10 minutes AI review vs 60 minutes
designer self-review

**Impact:** 70% fewer developer questions. Prevents
2-3 revision rounds per project.

**Example output:**

```
Audit categories:
- Missing interaction states
- Inconsistent spacing (8px vs 10px grid violations)
- Color contrast ratio failures
- Missing responsive breakpoints
- Unlabeled auto-layout frames
```

---

### 3. Database Schema Review Against Feature Brief

**Problem:** Schema reviews take 45-60 minutes and
security issues slip through to production.

**Solution:** Upload your database schema and feature
brief together. AI flags missing tables, RLS policy
gaps, and naming inconsistencies before development
starts.

**Tools:** Claude (best for structured analysis)

**Time saved:** 10 minutes PM pre-review plus 5 minutes
founder validation vs 60 minutes manual review

**Impact:** 12x faster founder review. Catches security
gaps before production.

**Example output:**

```
Critical: users table missing email_verified field
Warning: documents table has no created_by audit field
Passed: All foreign keys properly indexed
Warning: Supabase RLS policies missing on shares table

Feature coverage:
User auth        - Complete
Document upload  - Partial (missing file_size field)
Sharing          - Missing (no shares table exists)
```

---

## Project Management and Coordination

### 4. Slack Thread to PM Tool Ticket Auto-Creator

**Problem:** Blockers get lost in Slack threads and
tickets are created inconsistently when they exist
at all.

**Solution:** Developer posts a blocker in Slack. AI
extracts the issue and severity and automatically
creates a ticket with labels, priority, and assignee.

**Tools:** Zapier plus Claude API or Slack Workflow
Builder plus ChatGPT

**Time saved:** 2 minutes automated vs 8 minutes
manual per issue

**Impact:** Zero blockers lost. 30% faster issue
resolution.

**Example output:**

```
Slack message:
"Firebase auth keeps throwing invalid token on iOS
build but works fine on Android. Blocking v2.1 release."

Auto-generated ticket:
Title: iOS Firebase Auth Token Validation Failure
Priority: High (blocking release)
Labels: bug, firebase, iOS, authentication
Assigned: developer
Linked: Release v2.1
Description: extracted from message with full context
```

---

### 5. Client Feedback Consolidator

**Problem:** Feedback arrives across email, Slack, and
Loom and items get missed between platforms.

**Solution:** Upload all feedback sources to AI. It
consolidates everything into one prioritized list with
sources and severity.

**Tools:** Claude Projects with all inputs uploaded

**Time saved:** 5 minutes consolidation vs 25 minutes
hunting across platforms

**Impact:** Nothing slips through. Client feels heard
because everything is captured and actioned.

**Example output:**

```
Critical (from Loom video at 2:34):
- Homepage CTA button not clickable on mobile

Medium (from Slack DM, Jan 15):
- Login page needs more visual energy

Low (from email thread, Jan 14):
- Consider adding dark mode in a future release
```

---

### 6. Sprint Retrospective Pattern Analyzer

**Problem:** The same issues repeat across sprints and
nobody can see the pattern because retros live in
separate documents.

**Solution:** Upload the last 6 retrospectives. AI
identifies recurring blockers and sentiment trends
across the full dataset.

**Tools:** ChatGPT with file upload

**Time saved:** 15 minutes analysis vs 90 minutes
manual review

**Impact:** Systemic issues become visible to leadership.
Teams stop repeating the same mistakes.

**Example output:**

```
Recurring patterns across 6 sprints:

"Client changes requirements mid-sprint" (5 of 6 sprints)
Suggestion: Change request form with impact assessment

"Waiting for client assets" (4 of 6 sprints)
Suggestion: Asset checklist at kickoff with deadlines

Team sentiment on work-life balance: trending down
Action needed: Review workload distribution
```

---

## Client Communication

### 7. Technical Jargon to Client-Friendly Translator

**Problem:** Developer updates are too technical and
account managers spend 12 minutes rewriting each one.

**Solution:** Paste the developer Slack update. AI
translates it to client-friendly language. Account
manager reviews and sends.

**Tools:** Claude (best at tone shifting)

**Time saved:** 3 minutes vs 12 minutes per update

**Impact:** 60% fewer "what does this mean?" replies
from clients.

**Example output:**

```
Developer update:
"Supabase RLS policies configured for user data
isolation. Firebase Auth OAuth redirect URL needs
client Google Cloud project access. ETA 2 days
pending client credentials."

Client version:
Completed: User data security setup. Each user's
data is now private to them only.

Blocked: We need access to your Google Cloud account
to finish the Google login feature. Can you provide
this by Thursday? Otherwise launch may shift 2 days.
```

---

### 8. Client Meeting to Multi-Channel Distribution

**Problem:** Action items from meetings scatter across
people's notes and things get missed.

**Solution:** AI generates tickets, design comments,
code issues, and a client summary email from one
meeting transcript.

**Tools:** Otter.ai plus Claude API plus Zapier

**Time saved:** 8 minutes automated vs 35 minutes
manual distribution

**Impact:** Zero "I didn't know about that" situations
after meetings.

**Example output:**

```
From one meeting transcript:

PM tool: 3 tickets created (design, dev, QA)
Figma: 2 comments added to specific frames
GitHub: 1 issue created with technical spec
Client: Summary email sent within 10 minutes
Slack: Team notified in relevant channels
```

---

### 9. Scope Creep Detector

**Problem:** Small client requests accumulate into
unpaid work and project margins erode slowly.

**Solution:** Paste the client email. AI compares it
to the original SOW and flags anything out of scope
with an estimated cost.

**Tools:** Claude Projects with SOW uploaded as context

**Time saved:** 2 minutes analysis vs 15 minutes
founder review

**Impact:** Protects margins on roughly 25% of projects
where scope creep would otherwise go undetected.

**Example output:**

```
Client request:
"Can we add a feature where users export data to Excel?"

Analysis:
Scope creep detected.
Original SOW: PDF export only (page 3, deliverable 2.4)
New request: Excel export with formatting and sheets
Estimated hours: 8-12
Estimated cost: $800-$1,200
Recommendation: Send change order proposal
```

---

## Code and Technical Review

### 10. Pre-Merge Code Security Audit

**Problem:** Security vulnerabilities slip into
production because full reviews take too long.

**Solution:** Pull request submitted. AI scans for SQL
injection, XSS vulnerabilities, exposed keys, and weak
authentication before merge.

**Tools:** Claude or GitHub Copilot

**Time saved:** 5 minutes AI scan vs 30 minutes senior
developer review

**Impact:** Junior developers ship with senior-level
security awareness. Zero incidents from missed
vulnerabilities.

**Example output:**

```
Critical: API key exposed in client-side code (line 47)
High: SQL query uses string concatenation (line 203)
Medium: Password reset token does not expire
Passed: Input validation on all forms
Passed: HTTPS enforced across all routes
```

---

### 11. API Integration Pre-Flight Checklist

**Problem:** Teams start integrations unprepared and
discover blockers mid-project when delays are costly.

**Solution:** Paste the API documentation. AI generates
a complete implementation checklist including wait times
and blockers to surface before development starts.

**Tools:** ChatGPT with documentation pasted or linked

**Time saved:** 5 minutes vs 60 minutes reading
documentation manually

**Impact:** Prevents 80% of mid-project blockers caused
by requirements nobody knew about upfront.

**Example output:**

```
Resend Email API pre-flight:
- Domain verification required (DNS records, 24-48hr wait)
- Sender email address configuration
- API key generation (production vs test environments)
- Rate limits: 100 emails per hour on free tier
- Error handling: 4xx vs 5xx response patterns
- Webhook setup for delivery tracking
- Blocker: Need client domain access before starting
- Estimated setup: 2-3 days including domain verification
```

---

### 12. Deployment Readiness Validator

**Problem:** Launch day reveals things nobody checked.
Environment variables, analytics, error tracking.

**Solution:** Before launch, paste your configuration
and logs. AI checks environment variables, database
migrations, DNS, SSL, analytics, and error tracking.

**Tools:** Claude with configuration files pasted

**Time saved:** 10 minutes vs 45 minutes manual review

**Impact:** Every launch is complete. Zero post-launch
"we forgot to install analytics" situations.

**Example output:**

```
Environment variables: set (12 of 12)
Database migrations: run
DNS: configured and propagated
SSL certificate: active (expires Dec 2026)
Missing: Google Analytics not installed
Missing: Sentry error tracking not configured
App Store screenshots: 4 of 5 required

Ready to deploy: No. 2 critical items outstanding.
```

---

## Agency Operations

### 13. Profitability Anomaly Detector

**Problem:** Projects that are losing money get caught
too late for intervention to matter.

**Solution:** Export time entries as CSV. AI flags
projects burning budget faster than completion
percentage justifies.

**Tools:** ChatGPT with CSV upload

**Time saved:** 10 minutes vs 2 hours manual
spreadsheet analysis

**Impact:** Catch at-risk projects 3 weeks earlier.
Saves $3,000-$8,000 per project through earlier
scope conversations.

**Example output:**

```
Alert: Project SafeCabinet
Budget: 80 hours | Used: 64 hours | Completion: 45%
Projected overrun: 60 hours ($6,000 loss)
Action: Scope discussion needed this week

Warning: Designer logged 52 hours this week
Average: 40 hours | Overallocation risk: High
Action: Review workload distribution

Healthy: Project Twintual
Budget: 120 hours | Used: 55 hours | Completion: 50%
On track for 10% profit margin
```

---

### 14. Proposal Win/Loss Pattern Analyzer

**Problem:** Nobody knows why proposals win or lose
so pricing and language decisions are based on gut.

**Solution:** Upload your last 20 proposals. AI finds
pricing ranges, language patterns, and timeline
preferences correlated with wins vs losses.

**Tools:** Claude (200K context handles 20+ documents)

**Time saved:** 20 minutes vs not possible manually
across that volume

**Impact:** Win rate increases 15-20% when proposals
are adjusted based on actual pattern data.

**Example output:**

```
Won proposals (when these are present):
- Price between $8K-$15K
- Client testimonials included (75% win rate)
- Specific tech stack match mentioned (80% win rate)
- Timeline of 6-8 weeks

Lost proposals (when these are present):
- Price over $20K (sticker shock pattern)
- Generic language without specifics
- Timeline under 4 weeks (perceived as rushed)

Recommendations: Add testimonials to template.
Target $10K-$12K. Avoid timeline under 4 weeks.
```

---

### 15. Employee Onboarding Knowledge Bot

**Problem:** New hires ask repeated questions and
senior team members lose 8 hours per onboarding
answering the same things.

**Solution:** Upload all documentation once. New hire
asks questions and AI answers with source links so
they know where to find information independently.

**Tools:** Claude Projects or custom ChatGPT

**Time saved:** 2-hour one-time setup vs 8 hours per
new hire in senior team time

**Impact:** New hires productive from day one. 90%
fewer onboarding interruptions in Slack.

**Example output:**

```
Q: How do I submit my timesheet?
A: Use Productive.io, Time Tracking tab, submit by
   Friday 5pm. [Source: Employee Handbook, page 12]

Q: What is our code review process?
A: Create PR, request review from tech lead, must
   pass security scan, merge after approval.
   [Source: Developer Guidelines, section 3.2]

Q: Where are brand assets stored?
A: Google Drive, Clients folder, client name folder,
   Brand Assets subfolder.
   [Source: Project Management SOP, page 7]
```

---

*Part of the [ops-playbooks](https://github.com/srush3003/ops-playbooks) repo by Srush*  
*Full portfolio: <a href="https://srushtip.notion.site/portfolio" target="_blank">srushtip.notion.site/portfolio</a>*  
*LinkedIn: <a href="https://linkedin.com/in/srushti-pagrut" target="_blank">linkedin.com/in/srushti-pagrut</a>*
