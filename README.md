# Convergence CRM — Preview SPA

Single-file CRM single-page app (vanilla JS + Supabase JS client), deployed to GitHub Pages.
Built for **OMN-58** (CRM Frontend SPA), same stack/pattern as the EOS Tracker.

## Live preview
https://bkocs7189.github.io/crm-preview/

**Board access code:** `crm-convergence-2026` (client-side SHA-256 gate, same pattern as EOS Tracker)

## Modules
- **Dashboard** — open-pipeline / won summary cards, pipeline-by-stage, recent activity feed
- **Contacts** — searchable list, detail drawer with company/deals/activity timeline, inline create/edit
- **Pipeline** — Kanban board with drag-and-drop stage moves (persists to Supabase)
- **Deals** — list + detail drawer, inline edit, stage/probability, close-date picker
- **Activities** — log call/email/meeting/note/task, link to contact and/or deal

## Stack
- Vanilla JS, no build step, single `index.html`
- `@supabase/supabase-js@2` via CDN
- Backend: Supabase project `Convergence` (`krthbgtykwamxqvapxnx`)
- Mobile-responsive (collapsible nav, full-width drawer)

## Backend note (coordination)
This preview reads/writes isolated, anon-accessible `crmui_*` tables so it stays decoupled
from the canonical CRM backend (OMN-59), which was actively migrating during the build.
Data contract (table → columns) is documented on OMN-58 for convergence with OMN-59.
Final access model + RLS hardening are owned by OMN-59 (backend) and OMN-62 (security review).
