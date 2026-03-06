**Technologies:** Node.js | n8n | Puppeteer | Workflow Automation | Fintech Operations

# Automated Debt Collection System

Workflow automation for  delinquent customers and triggering automated collection outreach.

## Problem

Fintech and revenue operations teams often rely on manual processes to identify delinquent customers and initiate collection outreach. These processes are time-consuming, difficult to scale, and may delay contact with overdue accounts.

Without automation, operations teams face challenges such as:

- prioritizing customers based on overdue status  
- triggering timely follow-ups  
- maintaining consistent communication channels  
- tracking collection actions across multiple customers  

## Solution

This project implements an **automated debt collection workflow** that identifies delinquent customers and triggers outreach actions automatically.

The system prioritizes overdue accounts and sends automated reminders through **WhatsApp and email**, reducing manual intervention in the collection process.

Customer data is managed through **Google Sheets**, enabling automated **customer segmentation, prioritization of accounts, and payment follow-ups**.

The workflow demonstrates how **automation and data-driven prioritization** can improve operational efficiency in **fintech and revenue operations environments**.

## Workflow Architecture

The automated workflow operates through the following steps:

1. Customer payment data is stored in **Google Sheets**  
2. **n8n** monitors overdue accounts  
3. A **Node.js script** processes the data and prioritizes delinquent customers  
4. **Puppeteer** automates WhatsApp Web interactions  
5. Automated reminders are sent via **WhatsApp and email**  
6. Follow-up activity is recorded for operational tracking  

## Tech Stack

- **n8n** — workflow automation  
- **Node.js** — automation logic and data processing  
- **Puppeteer** — browser automation for WhatsApp messaging  
- **Google Sheets** — customer data source and segmentation  

## Business Impact

This workflow demonstrates how automation can support **collection operations and revenue teams** by:

- reducing manual collection workload  
- enabling scalable customer follow-ups  
- improving response time for delinquent accounts  
- supporting data-driven prioritization of collection efforts  

Potential applications include:

- fintech operations  
- revenue operations  
- payment recovery teams  

## Example Use Case

1. A customer becomes overdue on a payment  
2. The system detects the delinquency in Google Sheets  
3. The workflow triggers an automated WhatsApp reminder  
4. If payment is not completed, an email follow-up is sent  
5. Collection activity is logged for monitoring and analysis  

## Repository

Project repository:

https://github.com/sofiacravo91-tech/Automated-Debt-Collection-System
