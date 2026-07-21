# Product Requirements Document
## Lead Generation Hub

**Version:** 1.0  
**Date:** July 21, 2026  
**Status:** Draft  

---

## 1. Executive Summary

Lead Generation Hub is a B2B sales intelligence and lead management platform that helps sales teams discover, capture, score, verify, and follow up on prospects from multiple sources — including web scraping, LinkedIn, website forms, and cold outreach campaigns. It consolidates fragmented lead generation workflows into a single, mobile-friendly hub with deep integrations into industry-standard CRM and outreach tools.

---

## 2. Problem Statement

Sales teams at SMBs and B2B companies waste significant time and money juggling multiple disconnected tools to find, qualify, and act on leads. Key pain points include:

- **Scattered data sources** — leads come from LinkedIn, forms, cold email, and scraped databases with no unified view
- **Manual verification** — reps spend hours validating email addresses and contact info
- **No intelligent scoring** — every lead looks equally valuable, leading to poor prioritisation
- **Slow follow-up** — manual outreach delays mean warm leads go cold
- **Poor visibility** — no single dashboard showing pipeline health, conversion rates, or source ROI

---

## 3. Goals & Success Metrics

| Goal | Metric | Target |
|------|--------|--------|
| Centralise lead capture | % of leads flowing through the hub | > 80% within 30 days of onboarding |
| Reduce time-to-contact | Average hours from lead capture to first outreach | < 2 hours |
| Improve lead quality | % of leads that reach "qualified" status | > 40% |
| Increase rep productivity | Leads processed per rep per week | 2× baseline |
| Revenue | Monthly Recurring Revenue (MRR) | $10K within 6 months of launch |

---

## 4. Target Users & Personas

### Persona 1 — Alex, the B2B Sales Rep
- Works at a 20–200 person SaaS or services company
- Spends 3–4 hours/day prospecting on LinkedIn and email
- Frustrated by copy-pasting contact details across tools
- Needs: fast lead discovery, one-click enrichment, and email sequences

### Persona 2 — Jordan, the Sales Manager / SME Owner
- Owns a small business or leads a sales team of 2–10 reps
- Needs visibility into pipeline health and rep activity
- Makes buying decisions; cares about ROI and simplicity
- Needs: analytics dashboard, team management, integrations with existing tools

### Persona 3 — Morgan, the Marketing/Growth Lead
- Runs inbound campaigns and owns the website contact form
- Wants leads from forms to auto-route into the sales pipeline
- Needs: form builder, source attribution, campaign performance data

---

## 5. Features & Requirements

### 5.1 Lead Capture

| # | Requirement | Priority |
|---|-------------|----------|
| LC-1 | Embeddable web capture forms (customisable fields, branding) | P0 |
| LC-2 | LinkedIn scraping — extract contact name, title, company, email, URL | P0 |
| LC-3 | Web scraper — crawl target websites or directories for contact data | P0 |
| LC-4 | Manual lead entry / CSV bulk import | P0 |
| LC-5 | Cold outreach reply capture (email parsing) | P1 |
| LC-6 | API endpoint for third-party lead ingestion | P1 |

### 5.2 Lead Enrichment & Verification

| # | Requirement | Priority |
|---|-------------|----------|
| EV-1 | Email address verification via Hunter.io integration | P0 |
| EV-2 | Contact enrichment (job title, company size, industry) via Apollo.io | P0 |
| EV-3 | Duplicate detection and merging | P0 |
| EV-4 | Phone number validation | P1 |
| EV-5 | Company firmographic data (revenue range, headcount, tech stack) | P1 |

### 5.3 Lead Scoring

| # | Requirement | Priority |
|---|-------------|----------|
| LS-1 | Configurable scoring rules (job title, company size, industry, source, engagement) | P0 |
| LS-2 | Automated score calculation on lead creation and update | P0 |
| LS-3 | Score thresholds for automatic status transitions (cold → warm → hot) | P0 |
| LS-4 | AI-assisted scoring based on historical conversion patterns | P2 |

### 5.4 CRM & Pipeline Management

| # | Requirement | Priority |
|---|-------------|----------|
| CRM-1 | Built-in lead pipeline (Kanban and list views) with drag-and-drop stage management | P0 |
| CRM-2 | Lead detail page — contact info, activity timeline, notes, tasks | P0 |
| CRM-3 | Two-way HubSpot sync (contacts, deals, activities) | P0 |
| CRM-4 | Apollo.io contact and sequence sync | P1 |
| CRM-5 | Tag and segment leads with custom labels | P1 |
| CRM-6 | Task and reminder management per lead | P1 |

### 5.5 Email Automation & Outreach

| # | Requirement | Priority |
|---|-------------|----------|
| EM-1 | Multi-step email sequence builder (drip campaigns) | P0 |
| EM-2 | Personalisation tokens (first name, company, role) | P0 |
| EM-3 | Send-time optimisation | P1 |
| EM-4 | Open, click, and reply tracking | P0 |
| EM-5 | Brevo (formerly Sendinblue) integration for email delivery | P0 |
| EM-6 | Unsubscribe / opt-out handling (CAN-SPAM / GDPR compliant) | P0 |
| EM-7 | A/B testing for subject lines and email body | P2 |

### 5.6 Analytics Dashboard

| # | Requirement | Priority |
|---|-------------|----------|
| AN-1 | Pipeline overview — total leads, by stage, by source | P0 |
| AN-2 | Conversion funnel (capture → qualified → contacted → closed) | P0 |
| AN-3 | Source performance — which channels generate the most / best leads | P0 |
| AN-4 | Email campaign metrics (open rate, click rate, reply rate, bounce rate) | P0 |
| AN-5 | Lead score distribution over time | P1 |
| AN-6 | Rep activity leaderboard (leads contacted, emails sent, deals closed) | P1 |
| AN-7 | Export reports to CSV / PDF | P1 |

### 5.7 Integrations

| Integration | Purpose | Priority |
|-------------|---------|----------|
| HubSpot | Bi-directional CRM sync | P0 |
| Apollo.io | Contact enrichment + outreach sequences | P0 |
| Hunter.io | Email finding and verification | P0 |
| Brevo | Transactional and campaign email delivery | P0 |
| Paystack | Payment processing for subscriptions | P0 |
| LinkedIn (via scraper) | Lead discovery | P0 |
| Zapier / Webhook | Custom automation triggers | P2 |

### 5.8 Authentication & Team Management

| # | Requirement | Priority |
|---|-------------|----------|
| TM-1 | User registration and login (email + password, Google SSO) | P0 |
| TM-2 | Organisation / workspace with multiple seats | P0 |
| TM-3 | Role-based access control (Admin, Manager, Rep) | P1 |
| TM-4 | API key management per workspace | P1 |

### 5.9 Mobile Experience

| # | Requirement | Priority |
|---|-------------|----------|
| MOB-1 | Fully responsive web app (works on iOS and Android browsers) | P0 |
| MOB-2 | Mobile-optimised lead detail and pipeline views | P0 |
| MOB-3 | Push notifications for hot lead alerts and task reminders | P2 |

---

## 6. User Flows

### Flow 1 — Web Scrape & Capture
1. Rep enters a target domain or LinkedIn search URL
2. Scraper extracts contact list (name, email, title, company)
3. System auto-verifies emails via Hunter.io
4. Verified leads are enriched via Apollo.io
5. Leads are scored and added to the pipeline

### Flow 2 — Inbound Form Lead
1. Visitor fills in a form on the rep's website (embedded hub form)
2. Lead is created instantly in the hub
3. Score is calculated based on company and role data
4. Automated email sequence is triggered
5. Rep is notified if score exceeds "warm" threshold

### Flow 3 — Outreach Campaign
1. Rep creates a segment of leads (e.g. score > 60, industry = SaaS)
2. Rep builds a 3-step email sequence with personalisation tokens
3. Sequence launches and tracks opens, clicks, replies
4. Replies are parsed and lead status updated automatically
5. Hot leads surface in the rep's priority queue

### Flow 4 — CRM Sync
1. Rep qualifies a lead in the hub
2. Contact and deal are pushed to HubSpot automatically
3. HubSpot deal stage changes sync back to the hub pipeline
4. Activity log stays consistent across both systems

---

## 7. Technical Requirements

| Area | Requirement |
|------|-------------|
| **Platform** | Web application (responsive, mobile-first) |
| **Backend** | Node.js / Express API, PostgreSQL database |
| **Frontend** | React + Vite |
| **Scraping** | Headless browser (Playwright or Puppeteer) with proxy rotation |
| **Email delivery** | Brevo SMTP / API |
| **Payments** | Paystack Subscriptions API |
| **Auth** | JWT sessions; Google OAuth optional |
| **Data privacy** | GDPR and CAN-SPAM compliant opt-out and data deletion |
| **Uptime** | 99.5% monthly |
| **Performance** | Dashboard load < 2s on 4G mobile |
| **Security** | HTTPS, rate limiting, input sanitisation, secrets vault |

---

## 8. Monetisation

| Plan | Price | Limits | Features |
|------|-------|--------|----------|
| **Starter** | $49/mo | 1 seat, 500 leads/mo | Capture, scoring, basic email |
| **Growth** | $149/mo | 3 seats, 2,500 leads/mo | + Integrations, sequences, analytics |
| **Pro** | $399/mo | 10 seats, unlimited leads | + AI scoring, A/B testing, priority support |
| **Enterprise** | Custom | Unlimited | + Custom integrations, SLA, dedicated CSM |

Payment processed via **Paystack Subscriptions**. Annual billing available at 20% discount.

---

## 9. Out of Scope (v1.0)

- Native iOS / Android apps (mobile web only)
- Salesforce integration (v2 roadmap)
- AI-generated email copy (v2 roadmap)
- Social media (Twitter/X, Facebook) scraping
- Predictive deal forecasting

---

## 10. Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| LinkedIn scraping gets blocked | High | High | Use rotating proxies, throttle requests, offer manual import fallback |
| Email deliverability issues | Medium | High | Use Brevo with domain authentication (SPF/DKIM), monitor bounce rates |
| GDPR non-compliance fines | Low | Very High | Unsubscribe flow, data deletion API, privacy policy on all forms |
| HubSpot API rate limits | Medium | Medium | Queue sync jobs, implement exponential backoff |
| Low conversion from free trial | Medium | High | Onboarding wizard, sample leads, in-app tooltips |

---

## 11. Milestones

| Milestone | Deliverables | Target |
|-----------|-------------|--------|
| **M1 — Foundation** | Auth, DB schema, API scaffold, CI/CD | Week 2 |
| **M2 — Core Capture** | Form builder, CSV import, manual entry, lead list | Week 4 |
| **M3 — Enrichment** | Hunter.io + Apollo.io integration, email verification, scoring | Week 6 |
| **M4 — Outreach** | Email sequence builder, Brevo integration, tracking | Week 8 |
| **M5 — CRM & Sync** | Pipeline view, HubSpot sync, task management | Week 10 |
| **M6 — Analytics** | Dashboard, funnel, source performance reports | Week 12 |
| **M7 — Scraping** | LinkedIn + web scraper with proxy support | Week 14 |
| **M8 — Monetisation** | PayPal subscriptions, plan enforcement, billing portal | Week 16 |
| **M9 — Beta Launch** | QA, mobile polish, onboarding flow, public beta | Week 18 |

---

## 12. Open Questions

1. Will the LinkedIn scraper use a headless browser or a third-party data provider (e.g. PhantomBuster) to reduce legal risk?
2. Should the email sequence builder support plain-text only, or also HTML templates?
3. Is there a desired trial period (e.g. 14-day free trial) before PayPal billing kicks in?
4. Are there specific regions / languages to support at launch (English only for v1)?
5. Should team seats include shared lead pools or separate pipelines per rep?
