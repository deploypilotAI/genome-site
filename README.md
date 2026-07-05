# Genome

Independent examination of revenue. Every deal, checked against every invoice.

## What This Is

A single-page landing site that demonstrates:
- **In-browser reconciliation** — upload your quote and invoice CSVs, reconciliation runs on your device
- **Pricing tiers** — Pilot (free), Continuous ($750–$4K/mo), Resident Examiner (VPC)
- **The full audit-letter concept** — addressed to CFOs, structured like a formal examination

## No Build, No Framework

This is a static HTML file. Open `index.html` in your browser to preview.

## Deployment

See `GENOME_DEPLOY_WALKTHROUGH.md` for step-by-step instructions to deploy to Cloudflare Pages.

## Making Changes

Edit `index.html` directly. Sections are marked with `<!-- ── Sx ────── -->` comments.

Key sections:
- **Hero / opinion letter** — lines 113–136
- **Specimen examination demo** — lines 158–188
- **In-browser upload + reconciliation** — lines 190–260
- **Pricing (§04)** — lines 369–443
- **Notes/FAQ (§05)** — lines 495–523

After editing, commit and push to GitHub — Cloudflare redeploys automatically.

## JavaScript

The site runs two reconciliation demos:
1. **Specimen flow** — hardcoded sample data, tap "Run the specimen examination"
2. **Real flow** — user uploads ANY number of CSVs in any mix (e.g. multiple
   Salesforce quote pulls + several billing exports); each file is classified
   as quotes or invoices by its own columns, duplicates across quote pulls
   keep their first occurrence, and unclassifiable files block the run with
   a reason (refuse, never guess) — mirroring the engagement engine's
   /pilot/upload auto-detect. Tap "Examine my records".

Both are client-side; no server, no data leaves your browser.

All logic is in the `<script>` blocks at the end of the HTML.
