# Overclocker — Challenge-Based Hiring Platform

> **Team Overclocked:** Shorya Jain & Bhavya Singh  
> **Event:** HackShift, IIIT Delhi  
> **Theme:** Entrepreneurship & Employment

---

## 🚀 Overview

**Overclocker** is a challenge-based hiring platform designed to replace resume buzzwords with demonstrated strengths. Instead of screening PDF resumes, startups post open vacancies as realistic, time-capped **micro-challenges** (≤ 4 hours). Job seekers submit deliverables alongside written technical rationale and AI disclosures. Mentors review submissions against visible rubrics, and startups hire candidates whose multidimensional profiles best match their specific priorities.

### The 3 Core Innovations

1. **Vacancy = Challenge:** The task is the application. No resume fluff.
2. **Mandatory Cash Prize Escrow (Scam Control):** Every posted challenge must fund an upfront cash prize pool (minimum ₹2,000) held in platform escrow before going live. This prevents startups from exploiting free work or ghosting applicants.
3. **Multidimensional Skill Profile, Not a Single Score:** Every reviewed challenge builds a granular skill radar across dimensions (Design Quality, Problem-Solving, Communication, Attention to Detail, Response to Feedback). Two candidates with equal totals can have vastly different strengths, and companies rank candidates with explainable dimensional weights.

---

## 🛠️ Architecture & Tech Stack

- **Frontend:** React 18, TypeScript, Tailwind CSS, React Router v6, Lucide Icons, Canvas Confetti.
- **Charts:** Custom interactive SVG Multidimensional Radar Chart with 5-level concentric polygons, vertex tooltips, and responsive coordinate geometry.
- **State & Backend Engine:**
  - Reactive Storage Engine (`src/services/store.ts`) mirroring Supabase tables, row-level access rules, draft autosaves, and idempotent result publishing in local storage.
  - Complete PostgreSQL / Supabase migration schema (`supabase/migrations/20261018000000_init.sql`) with tables, foreign keys, views (`skill_profile_view`), and RLS policies.
- **Centralized Rules Configuration:** `src/config/rules.ts` houses all assumptions, fee structures, escrow thresholds, token multipliers, and formula logic in one place.

---

## 👥 Personas & Pre-Seeded Demo Data

Overclocker comes with labeled demo datasets for seamless testing:

| Role | Persona Name | Email | Key Responsibility / Feature |
|---|---|---|---|
| **Admin** | Deepa Roy | `admin@overclocker.dev` | Approves challenges with verified escrow, audits logs, verifies companies, executes Section 9.3 payout safeguards |
| **Company 1** | Arjun Mehta (Acme Studio) | `arjun@acmestudio.in` | Verified company posting hardware/UI challenges; uses dimensional fit ranking to shortlist/hire |
| **Company 2** | Kavita Sen (NeoVibe Brands) | `kavita@neovibe.co` | D2C sustainable streetwear brand posting merchandise challenges |
| **Mentor 1** | Priya Sharma | `priya.sharma@designguild.org` | Principal Visual Designer; scores rubrics, inspects authenticity signals panel |
| **Mentor 2** | Alex Chen | `alex.chen@globalcraft.io` | Creative Director; apparel and merchandise reviewer |
| **Mentor 3** | Sameer Joshi | `sameer.joshi@uxcollective.in` | UX Systems Lead; evaluates wireframes and technical rationale |
| **Job Seeker 1** | Rahul Verma | `rahul.verma@student.iiitd.ac.in` | IIITD Student; high Communication & Problem-Solving score (85/100) |
| **Job Seeker 2** | Ananya Iyer | `ananya.iyer@creatives.in` | Brand Specialist; identical total score (84/100) but high Design Quality & Attention to Detail |
| **Job Seeker 3-6**| Devendra, Tanvi, Kunal, Meera | `*@*.in` | Additional applicants demonstrating multi-applicant rankings |

---

## 🧭 HackShift End-to-End Demo Script (7 Steps)

You can run the full flow manually or click the **"HackShift Demo Script"** floating widget at the bottom-left of the screen:

1. **Company Door:** Sign in as Arjun Mehta (Acme Studio), post the *"Poster Design for a Product Launch"* challenge with ₹5,000 prize pool, deposit into escrow, and verify admin approval.
2. **Job Seeker Door:** Switch to Rahul Verma, register for the challenge, draft your visual submission and explain-your-work answers (observe the draft timeline snapshots updating automatically).
3. **Mentor Review:** Switch to Priya Sharma, open the review queue, inspect the **Authenticity Signals Panel** (draft timeline, Jaccard similarity, explain word counts, AI disclosure), and score the 4 dimensions.
4. **Revision Round:** Switch back to Rahul Verma, view the mentor feedback, open Round 2 Revision, and submit an updated entry (response to feedback delta is automatically computed).
5. **Publish Results:** Company publishes results; ₹5,000 prize is paid from escrow to finalists, and participation + revision bonus tokens are credited to wallets.
6. **Explainable Fit Ranking:** Company opens Fit Ranking on the SaaS challenge, filters `Communication ≥ 4.0`, and shortlists Rahul Verma over candidates with equal total score.
7. **Candidate Radar:** Rahul Verma views his verified Multidimensional Skill Radar, confidence badges, and personalized Improvement Hints based on mentor critiques.

---

## 🏃 Running the Application

### 1. Install dependencies:
```bash
npm install
```

### 2. Start local development server:
```bash
npm run dev
```

### 3. Build for production:
```bash
npm run build
```

---

## ⚖️ Fair-Use, Anti-Scam & Trust Guarantees

- **Mandatory Cash Escrow:** No challenge can go live without upfront escrow funding (min ₹2,000).
- **Effort Cap:** Strict maximum 4 hours of applicant effort.
- **IP Protection:** Clear choice between `winner_only_rights` and `no_rights_unless_hired`.
- **Authenticity Signals:** Informative signals for human reviewers; never an automated disqualification verdict.
- **Admin Safeguard Override:** If a company does not publish results within deadline + 7 days, platform admins release escrowed prizes directly to candidates based on mentor scores.

---
*Built with passion for HackShift 2026, IIIT Delhi.*
