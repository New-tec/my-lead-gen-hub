# Product Requirements Document
## LeadForge — B2B Lead Generation Hub

**Version:** 1.1  
**Date:** July 21, 2026  
**Status:** Draft  
**Live Product:** https://lead-generation-hub--couragefred3.replit.app  

---

## 1. Executive Summary

LeadForge is a B2B lead generation platform that lets sales teams find, verify, enrich, and reach prospects on autopilot. Users type a keyword — an industry, role, or company type — and LeadForge runs a 4-step async pipeline: it discovers businesses via web intelligence, scrapes contact data, verifies every email address, and enriches each profile with LinkedIn, phone, and firmographic data. Verified leads are then pushed directly into Brevo email campaigns or Twilio WhatsApp sequences with a single click — no CSV exports, no copy-paste.

The product ships with a built-in demo mode using mock data so users can experience the full workflow before connecting their own API keys.

---

## 2. Problem Statement

B2B sales teams waste hours every week stitching together multiple tools to find, qualify, and contact prospects. Key pain points:

- **Manual prospecting is slow** — reps spend 3–4 hours/day on LinkedIn and Google to build contact lists
- **Data quality is poor** — unverified emails cause high bounce rates (industry average 15–25%), damaging sender reputation
- **Fragmented toolchain** — discovery, verification, enrichment, and outreach all live in separate tools with no shared pipeline
- **Delayed outreach** — manual handoffs between tools mean warm leads go cold before first contact
- **No single dashboard** — pipeline health, verification rates, and campaign performance are scattered across platforms

---

## 3. Goals & Success Metrics

| Goal | Metric | Target |
|------|--------|--------|
| Reduce prospecting time | Hours/week saved per rep | ≥ 12 hours (per landing page claim) |
| Improve email accuracy | Verified email success rate | ≥ 94% |
| Leads generated on platform | Cumulative leads through pipeline | 2.4M+ (current milestone) |
| Customer adoption | Companies actively using LeadForge | 1,200+ (current milestone) |
| Activation | % of signups who run at least one pipeline | > 60% within first session |
| Revenue | Monthly Recurring Revenue | $10K MRR within 6 months of launch |

---

## 4. Target Users & Personas

### Persona 1 — Alex, the B2B Sales Rep
- Works at a 10–200 person SaaS or professional services company
- Spends 3–4 hours/day manually prospecting on LinkedIn and email
- Frustrated by copying contact details between tools
- Needs: fast keyword-based discovery, verified contacts, one-click campaign launch

### Persona 2 — Jordan, the SME Owner / Sales Lead
- Runs a small business or leads a team of 2–10 sales reps
- Needs pipeline visibility and outreach performance data without hiring an ops team
- Makes the buying decision; cares about ROI and ease of setup
- Needs: analytics dashboard, API key vault, clear demo-to-live upgrade path

### Persona 3 — Morgan, the Growth / Marketing Manager
- Runs outbound campaigns and owns email deliverability
- Wants a single platform for discovery-to-campaign without CSV handoffs
- Needs: Brevo push integration, bounce rate monitoring, campaign performance tracking

---

## 5. Application Structure

LeadForge is a single-page web application with four primary views accessible via a left-hand sidebar:

| Route | Page | Purpose |
|-------|------|---------|
| `/app` | Dashboard | Pipeline stats, recent activity, health metrics |
| `/app/search` | Discovery Engine | Keyword input → launch async pipeline |
| `/app/leads` | Lead Pipeline | Verified contacts table with filter, bulk action, campaign assignment |
| `/app/settings` | API Key Vault | Connect Firecrawl, Hunter.io, Fullenrich, Brevo, Twilio keys |

---

## 6. Features & Requirements

### 6.1 Discovery Engine (Search)

| # | Requirement | Priority |
|---|-------------|----------|
| DE-1 | Keyword search bar accepting free-text input (industry, role, location, company type) | P0 |
| DE-2 | "Launch" triggers an async 4-step pipeline in the background | P0 |
| DE-3 | Real-time pipeline progress indicator while job runs | P0 |
| DE-4 | Firecrawl integration — web intelligence to discover matching businesses | P0 |
| DE-5 | Demo mode using mock data when no API keys are configured | P0 |
| DE-6 | Pipeline history — view past searches and their results | P1 |
| DE-7 | Saved search templates (reusable keyword queries) | P2 |

### 6.2 The 4-Step Async Pipeline

| Step | Action | Service | Priority |
|------|--------|---------|----------|
| 1 — Discover | Web crawl for matching businesses based on keyword | Firecrawl | P0 |
| 2 — Scrape | Extract contact name, email, company, title, website from results | Firecrawl | P0 |
| 3 — Verify | Validate every email address before adding to pipeline | Hunter.io | P0 |
| 4 — Enrich | Append LinkedIn URL, phone, role, company size, industry | Fullenrich | P0 |

### 6.3 Lead Pipeline (Leads View)

| # | Requirement | Priority |
|---|-------------|----------|
| LP-1 | Tabular lead list showing: Contact, Company, Verification Status, Campaign | P0 |
| LP-2 | Filter leads by verification status (Verified / Unverified / Bounced) | P0 |
| LP-3 | Filter leads by campaign | P0 |
| LP-4 | Bulk select leads for outreach action | P0 |
| LP-5 | One-click push selected leads to a Brevo email campaign | P0 |
| LP-6 | One-click send WhatsApp messages to leads with phone numbers via Twilio | P0 |
| LP-7 | Lead detail view — full contact info, enrichment data, activity log | P1 |
| LP-8 | Manual lead entry and CSV bulk import | P1 |
| LP-9 | Tag and label leads | P1 |
| LP-10 | Export leads to CSV | P1 |

### 6.4 Email Outreach (Brevo Integration)

| # | Requirement | Priority |
|---|-------------|----------|
| EM-1 | Push verified leads directly into an existing Brevo campaign | P0 |
| EM-2 | Create a new Brevo campaign from within LeadForge | P1 |
| EM-3 | Track open rate, click rate, and reply rate per campaign | P1 |
| EM-4 | Bounce rate monitoring and automatic lead status update | P0 |
| EM-5 | Unsubscribe / opt-out handling (CAN-SPAM / GDPR compliant) | P0 |
| EM-6 | Personalisation tokens (first name, company, role) | P1 |

### 6.5 WhatsApp Outreach (Twilio Integration)

| # | Requirement | Priority |
|---|-------------|----------|
| WA-1 | Send personalised WhatsApp messages to leads that have a phone number | P0 |
| WA-2 | Message template editor with personalisation tokens | P0 |
| WA-3 | Delivery status tracking (sent / delivered / read / failed) | P1 |
| WA-4 | Opt-out handling for WhatsApp messages | P0 |

### 6.6 Analytics Dashboard

| # | Requirement | Priority |
|---|-------------|----------|
| AN-1 | Total leads in pipeline, by verification status | P0 |
| AN-2 | Pipeline success rate (discovered → verified → enriched) | P0 |
| AN-3 | Email campaign performance (open, click, bounce, reply rates) | P0 |
| AN-4 | WhatsApp outreach performance (sent, delivered, read) | P1 |
| AN-5 | Time saved estimate (vs manual research baseline) | P1 |
| AN-6 | Historical pipeline runs and their outcomes | P1 |
| AN-7 | Export dashboard report to CSV / PDF | P2 |

### 6.7 Settings — API Key Vault

| # | Requirement | Priority |
|---|-------------|----------|
| SK-1 | Secure vault to store and manage user-provided API keys | P0 |
| SK-2 | Keys: Firecrawl, Hunter.io, Fullenrich, Brevo, Twilio | P0 |
| SK-3 | Per-key connection test (validate key is active before saving) | P1 |
| SK-4 | Clear indicator: Demo mode (no keys) vs Live mode (keys connected) | P0 |
| SK-5 | Keys encrypted at rest; never exposed in UI after save | P0 |

### 6.8 Authentication & Accounts

| # | Requirement | Priority |
|---|-------------|----------|
| AU-1 | Email + password registration and login | P0 |
| AU-2 | Google OAuth sign-in | P1 |
| AU-3 | Password reset via email | P0 |
| AU-4 | Account settings (name, email, password change) | P1 |
| AU-5 | Team / organisation support with multiple seats | P2 |

### 6.9 Mobile Experience

| # | Requirement | Priority |
|---|-------------|----------|
| MOB-1 | Fully responsive web app (works on iOS and Android browsers) | P0 |
| MOB-2 | Mobile-optimised sidebar navigation | P0 |
| MOB-3 | Touch-friendly lead table with horizontal scroll | P0 |

---

## 7. Integrations

| Integration | Role | How it's used | Priority |
|-------------|------|---------------|----------|
| **Firecrawl** | Web discovery & scraping | Crawls the web for businesses matching the keyword; extracts contact data | P0 |
| **Hunter.io** | Email verification | Validates every scraped email before it enters the pipeline | P0 |
| **Fullenrich** | Contact enrichment | Appends LinkedIn URL, phone, role, company size, and industry | P0 |
| **Brevo** | Email outreach | Receives verified lead lists; delivers email campaigns | P0 |
| **Twilio** | WhatsApp outreach | Sends personalised WhatsApp messages to leads with phone numbers | P0 |
| **Paystack** | Payment & subscriptions | Handles plan billing and subscription management | P0 |

---

## 8. User Flows

### Flow 1 — Keyword to Pipeline (Core Flow)
1. User navigates to **Search → Discovery Engine**
2. Types a keyword (e.g. "VP Engineering Fintech San Francisco")
3. Clicks **Launch**
4. Async pipeline runs in background: Discover → Scrape → Verify → Enrich
5. Results appear in the **Leads** view as verified, enriched contacts
6. User filters by verification status and selects target leads
7. Clicks "Push to Brevo" or "Send WhatsApp" to launch outreach

### Flow 2 — Demo to Live Upgrade
1. New user signs up — app runs in demo mode with mock data
2. User explores the full pipeline experience using sample leads
3. User navigates to **Settings** and enters their API keys
4. System validates each key and switches to live mode
5. First real pipeline run uses actual Firecrawl + Hunter.io + Fullenrich data

### Flow 3 — Email Campaign Launch
1. User selects verified leads in the pipeline table
2. Clicks "Push to Brevo campaign"
3. Selects an existing Brevo campaign or creates a new one
4. Leads are added to the campaign contact list
5. Email is sent via Brevo; open/click/bounce data flows back into LeadForge

### Flow 4 — WhatsApp Outreach
1. User filters leads to those with a phone number
2. Selects leads and clicks "Send WhatsApp"
3. Selects or writes a message template with personalisation tokens
4. Messages are sent via Twilio; delivery status is tracked in the pipeline

---

## 9. Technical Requirements

| Area | Requirement |
|------|-------------|
| **Platform** | Web application — responsive, mobile-first |
| **Frontend** | React + Vite |
| **Backend** | Node.js / Express, PostgreSQL, Drizzle ORM |
| **Async pipeline** | Background job queue for multi-step scrape/verify/enrich operations |
| **Payments** | Paystack Subscriptions API |
| **Email delivery** | Brevo API |
| **WhatsApp** | Twilio WhatsApp Business API |
| **Web discovery** | Firecrawl API |
| **Email verification** | Hunter.io API |
| **Data enrichment** | Fullenrich API |
| **Security** | API keys encrypted at rest; HTTPS; rate limiting; secrets vault |
| **Data privacy** | GDPR and CAN-SPAM compliant opt-out and data deletion |
| **Uptime** | 99.5% monthly |
| **Performance** | Dashboard load < 2s on 4G mobile |

---

## 10. Monetisation

| Plan | Price | Leads/mo | Features |
|------|-------|----------|----------|
| **Starter** | $49/mo | 500 | Discovery, verification, Brevo push |
| **Growth** | $149/mo | 2,500 | + Fullenrich enrichment, WhatsApp, analytics |
| **Pro** | $399/mo | Unlimited | + Saved searches, export, priority support |
| **Enterprise** | Custom | Unlimited | + Custom integrations, SLA, dedicated CSM |

- **Demo mode** available to all signups with no credit card required — uses mock data
- Payment processed via **Paystack Subscriptions**
- Annual billing available at 20% discount

---

## 11. Out of Scope (v1.0)

- Native iOS / Android apps (responsive mobile web only)
- HubSpot / Salesforce CRM sync (v2 roadmap)
- LinkedIn direct scraping (Firecrawl web intelligence covers discovery)
- AI-generated email copy (v2 roadmap)
- Multi-seat team workspaces (v2 roadmap)
- Predictive lead scoring with ML (v2 roadmap)

---

## 12. Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| Firecrawl blocks or rate-limits crawls | Medium | High | Implement retry with backoff; surface clear error in UI |
| Hunter.io false negatives (valid emails marked invalid) | Low | Medium | Allow manual override of verification status |
| Twilio WhatsApp policy violations | Medium | High | Enforce opt-in confirmation and opt-out handling |
| Brevo API rate limits | Medium | Medium | Queue push jobs; process in batches |
| GDPR non-compliance | Low | Very High | Opt-out flow, data deletion endpoint, privacy policy on all outreach |
| Poor demo-to-paid conversion | Medium | High | In-app prompt when user exhausts mock leads; highlight live mode benefits |

---

## 13. Milestones

| Milestone | Deliverables | Target |
|-----------|-------------|--------|
| **M1 — Foundation** | Auth, DB schema, API scaffold, CI/CD | Week 2 |
| **M2 — Discovery Engine** | Keyword search UI, Firecrawl integration, async pipeline | Week 4 |
| **M3 — Verify & Enrich** | Hunter.io email verification, Fullenrich enrichment, demo mode | Week 6 |
| **M4 — Lead Pipeline** | Leads table, filters, lead detail view, CSV export | Week 8 |
| **M5 — Email Outreach** | Brevo push integration, campaign selection, tracking | Week 10 |
| **M6 — WhatsApp Outreach** | Twilio integration, message templates, delivery tracking | Week 12 |
| **M7 — Analytics** | Dashboard metrics, pipeline history, campaign performance | Week 13 |
| **M8 — Settings Vault** | API key management, connection testing, demo/live toggle | Week 14 |
| **M9 — Monetisation** | Paystack subscriptions, plan enforcement, billing portal | Week 16 |
| **M10 — Launch** | QA, mobile polish, onboarding flow, public launch | Week 18 |

---

## 14. Open Questions

1. Should the async pipeline run server-side (background worker) or client-side (polling)?
2. Is there a desired lead volume cap per pipeline run, or is it purely plan-based?
3. Should WhatsApp outreach require pre-approved message templates (Twilio requirement)?
4. Is there a free trial period (e.g. 14 days) before Paystack billing kicks in?
5. Should the Settings vault support multiple API key profiles (e.g. different Brevo accounts per campaign)?
