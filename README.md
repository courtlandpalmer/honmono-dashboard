# Honmono Project Dashboard

Shared project management dashboard for the Honmono omakase project (320 Center Street, Healdsburg). Built for Charlie Palmer Collective / Appellation Hotels.

## How it works

- **Frontend:** this repo's `index.html`, served by GitHub Pages. Anyone with the URL can view and edit.
- **Data:** Supabase project `honmono-dashboard` (Appellation org). Tables: `milestones`, `documents`, `contacts`, `open_questions`, `meeting_notes`. Documents live in the public `project-docs` storage bucket.
- **Tasks:** live in ClickUp (Honmono space, four lists). The dashboard reads and writes them through the `clickup` Supabase Edge Function, which holds the ClickUp API token server side. Nobody needs to open ClickUp.

## Operations

- Design or layout changes: edit `index.html`, commit to `main`; the site updates in about a minute.
- Data corrections: Supabase Dashboard, Table Editor.
- Task changes: use the dashboard, or ClickUp directly if preferred; both stay in sync because ClickUp is the system of record.
- The Supabase anon key embedded in `index.html` is publishable by design. The ClickUp token is not in this repo and must never be added to it.

## Admin

- GitHub Pages: Settings, Pages, deploy from `main`, root.
- Supabase project ref: `jpiqmeiwuygzzfoejrvr`.
- Edge function: `clickup` (Supabase Dashboard, Edge Functions) for the task bridge.
