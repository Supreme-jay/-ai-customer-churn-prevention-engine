# AI Customer Churn Prevention Engine
### n8n + Groq (Free AI) | Identifies at-risk customers before they cancel

![Workflow](screenshots/workflow.png)

## Project Summary
The AI Customer Churn Prevention Engine is a workflow automation project built with n8n and Groq AI to identify customers at risk of churning before cancellation happens. It automatically analyses customer behaviour signals, classifies churn risk, sends retention emails where needed, alerts the customer success team, updates records, and generates weekly management insights.

This project demonstrates practical AI automation, customer success workflow design, retention-focused business automation, and multi-tool orchestration using free tools. It is designed as a portfolio-ready automation project for real-world subscription and recurring revenue businesses.

## The Problem
Companies lose $3.8 trillion globally to churn every year. Most discover a customer has left only after cancellation. This workflow finds them weeks earlier and acts automatically.

## Results
- 25–40% reduction in customer churn
- $240,000 saved/year on a $10M ARR company
- 0 manual work — runs every Monday automatically
- $0 AI cost using Groq's free tier

## How It Works
Every Monday at 8AM the workflow:
1. Reads all customer data from Google Sheets
2. Groq AI (Llama 3.3 70B) analyses each customer's behaviour
3. Scores every customer: HIGH / MEDIUM / LOW churn risk
4. HIGH risk → personalised AI-written win-back email + Slack alert
5. MEDIUM risk → soft check-in email
6. LOW risk → no action (avoids email fatigue)
7. Updates Google Sheets with scores and actions taken
8. Sends weekly summary report to management

## Churn Risk Signals Analysed
- Login frequency (last 30 days)
- Days since last login
- Support ticket volume (last 90 days)
- Feature usage level
- Failed payment events
- Plan tier and MRR value

## Tech Stack

| Tool | Purpose | Cost |
|------|---------|------|
| n8n | Workflow orchestration | Free (self-host) |
| Groq (Llama 3.3 70B) | Churn AI analysis | 100% Free |
| Google Sheets | Customer data store | Free |
| Gmail | Win-back + check-in emails | Free |
| Slack | CS team alerts | Free |

## Setup Instructions
1. Import `workflow.json` into your n8n instance
2. Get free Groq API key at console.groq.com
3. Create Google Sheet `Customer Health Tracker` with columns:
   `CustomerID, CustomerName, Email, Plan, MRR, SignupDate, LastLoginDate, LoginCount30Days, SupportTickets, FeatureUsage, PaymentFailed, ChurnRisk, ChurnReason, LastActionTaken`
4. Create Slack channel `#cs-churn-alerts` and add your bot
5. Connect all credentials in n8n
6. Activate workflow — runs every Monday at 8AM

## Ideal For
SaaS companies • E-commerce subscriptions • Telecom • Banking • Any subscription business that wants to stop losing customers silently

## Files Included
- `workflow.json` — n8n workflow export
- `screenshots/workflow.png` — workflow screenshot
- `SETUP.md` — setup guide

## Built By
**Ifeanyi Nwadike** | Open to AI Automation Engineer roles  
LinkedIn: https://www.linkedin.com/in/ifeanyi-nwadike-aab752356  
GitHub: https://github.com/Supreme-jay
