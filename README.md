# Job Application Tracker — n8n + AI (Personal Learning Repo)

> **This project is a personal learning experiment where I use n8n and AI agents to automate tracking my job applications.** The main goal is to reduce the manual effort of updating a job application tracker — so I can focus entirely on applying, while the system keeps the table up to date.   
>
> It’s highly customized to my own process, Excel schema, and email setup. It isn’t meant to be a generic template, but rather a record of how I explored combining automation and AI in a real, practical workflow.
---

## What’s inside

- `job-application-tracker.n8n.json` — the n8n workflow export you can import.


### Workflow at a glance
![Example Image](Job_application_tracker_workflow.png)
### Excel table the flow updates
![Example Image](Excel_applications.png)
---

## How it works (very briefly)

This solution has two main flows that work together to keep my tracker current:

Tracking progress and rejections
-Periodically scans emails (including Junk) for updates from companies and recruiters.
-AI parses the messages into structured outcomes, like Status = Rejected or Interview Scheduled.
-The system then updates the matching row in Excel so I always see the latest stage of each application.

Capturing job confirmations
-Periodically checks the inbox for confirmation emails (e.g. “We received your application”).
-AI extracts the company and job title, then matches it to an existing row or creates a new one if it’s a fresh application.
-This removes the need for me to manually input every application into the tracker.

---

## Importing the workflow (n8n)
> You have to set up your own credentials & API keys for it to work!

1. Open n8n → **Workflows** → **Import from File**.
2. Choose `workflow/job-application-tracker.n8n.json`.
3. Update these to match your own setup:
   - Outlook connections and folder IDs (Inbox/Junk).
   - Excel Workbook / Worksheet / Table IDs.
   - OpenAI (or compatible) credentials and model names.
4. Test with a **single email** first and watch the Execution view.

> Note: If you don’t use the same Excel schema, update the *Set* nodes and the *Update/Append* mappings accordingly.

---
