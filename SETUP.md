# Setup Guide

## 1. Import the Workflow
Import `workflow.json` into your n8n instance.

## 2. Groq Setup
Get a free Groq API key from console.groq.com.

Recommended model:
- `llama-3.3-70b-versatile`

Used for:
- churn risk analysis
- risk reasoning
- personalised win-back and check-in email generation

## 3. Google Sheets Setup
Create a Google Sheet named **Customer Health Tracker**.

Use these columns:
- CustomerID
- CustomerName
- Email
- Plan
- MRR
- SignupDate
- LastLoginDate
- LoginCount30Days
- SupportTickets
- FeatureUsage
- PaymentFailed
- ChurnRisk
- ChurnReason
- LastActionTaken

## 4. Gmail Setup
Connect Gmail in n8n using OAuth2.

Used for:
- win-back emails
- medium-risk check-in emails
- weekly summary emails if included in your workflow

## 5. Slack Setup
Connect Slack in n8n.

Used for:
- high-risk customer alerts
- customer success team notifications

Recommended channel:
- `cs-churn-alerts`

## 6. Schedule
The workflow is designed to run every Monday at 8AM.

## 7. Expected Flow
- workflow reads customer data from Google Sheets
- Groq analyses churn risk per customer
- high-risk customers receive win-back email + Slack alert
- medium-risk customers receive soft check-in email
- low-risk customers receive no action
- Google Sheet is updated with churn risk and action taken
- weekly summary can be sent to management

## 8. Notes
This project is portfolio-ready and may require reconnecting credentials after importing into another n8n environment.
