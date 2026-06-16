---
name: dyna-events-dashboard
description: Build and customize Salesforce Lightning-style global event marketing dashboards for annual budget management, regional event performance, Leads/MQL/SQL funnel tracking, ROI/Revenue reporting, admin data updates, event-level task progress, risk alerts, reminder rules, and meeting collaboration. Use when a user asks for an event marketing command center, annual events budget dashboard, regional ROI dashboard, multi-level activity tracking page, or reusable HTML template for global events operations.
---

# DYNA Events Dashboard

## Overview

Use this skill to create a self-contained HTML dashboard for global event marketing operations. The bundled template in `assets/dyna-events-dashboard-template.html` implements a four-level Salesforce-style workflow:

1. Executive overview for annual budget, spend, Leads, MQLs, SQLs, ROI, and Revenue.
2. Regional performance view for event count, progress, budget usage, funnel quality, and ROI.
3. Regional event list with event ID, status, owner, cost, funnel metrics, revenue, score, and update actions.
4. Event workspace with task owners, schedule health, risk alerts, local reminder settings, and meeting collaboration.

## Quick Start

Copy `assets/dyna-events-dashboard-template.html` into the user's requested output location and rename it for the client or project. Keep it as a standalone HTML file unless the user explicitly asks for a framework implementation.

Use the template when the user wants:

- an annual event budget dashboard
- a global or regional event marketing management panel
- Leads, MQL, SQL, ROI, and Revenue tracking
- a Salesforce-style operational interface
- login-gated local data updates
- task/risk management for each event
- a shareable static prototype or working local dashboard

## Customization Workflow

1. Preserve the four-level information architecture unless the user asks to simplify it.
2. Update the `regions` array in the script section for region names, budgets, owners, event IDs, status, cost, Leads, MQLs, SQLs, Revenue, and score.
3. Keep placeholder event name/date/location fields as `TBC` when the user wants to fill them later.
4. Keep the default local admin credentials only for prototypes: `admin` / `dyna2026`.
5. Explain that local login and reminder automation are browser-local prototype features, not production authentication or external notifications.
6. If the user asks for production use, recommend adding a backend, real authentication, database persistence, calendar/email integration, and role-based permissions.

## Design Rules

- Keep the UI in English unless the user explicitly requests another language.
- Use a Salesforce Lightning-inspired system style: white panels, light gray app background, compact tables, blue primary buttons, subtle borders, restrained shadows, and dense operational layouts.
- Avoid marketing landing-page composition. This is an internal operations tool.
- Keep cards for repeated records, task cards, modals, and dashboard panels only.
- Keep controls practical: selects for filters, buttons for actions, tables for event records, and forms for updates.
- Preserve responsive behavior for desktop and mobile widths.

## Event Workspace Expectations

For each event, include:

- event summary: ID, name, date, location, owner, cost, funnel metrics, Revenue, ROI
- task progress: task name, owner, due date, status, schedule health, blocker note
- risk alerts: generated from event status, score, MQL rate, SQL rate, and ROI
- reminder automation: local cadence, owner, and note fields
- meeting collaboration: invitees, agenda, copyable meeting brief, and email draft launch

Task owner meeting actions should focus the meeting agenda on the selected blocker and produce a concise brief for stakeholders.

## Validation

After editing the template, validate the file before handing it off:

```bash
node -e "const fs=require('fs'); const html=fs.readFileSync('OUTPUT.html','utf8'); const script=html.match(/<script>([\s\S]*)<\/script>/)[1]; new Function(script); console.log('script syntax ok');"
```

If Node is not available, at minimum inspect the HTML for duplicate IDs and obvious untranslated text. If a browser preview is available, click through all four levels and test:

- region click opens regional event details
- event row or `Open Workspace` opens the event workspace
- `Update` opens the admin update flow
- reminder settings save locally
- meeting brief copy or email draft works

## Bundled Resource

- `assets/dyna-events-dashboard-template.html`: standalone working template with sample data, local storage persistence, admin update forms, risk/task workspace, and Salesforce-style UI.
