# Automated Debt Collection System

Technologies: Node.js | n8n | Puppeteer | Workflow Automation | Fintech Operations

Workflow automation for processing delinquent customers and triggering automated collection outreach.

## Problem

Fintech and revenue operations teams often rely on manual processes to follow up with delinquent customers. Even when overdue accounts are already identified in internal systems, initiating collection outreach can still require repetitive manual work.

Without automation, operations teams face challenges such as:

- manually contacting overdue customers
- ensuring timely follow-ups
- maintaining consistent communication channels
- tracking collection actions across multiple accounts

These manual tasks can slow down collection cycles and reduce operational efficiency.

## Solution

This project implements an automated debt collection workflow that processes a list of delinquent customers and triggers automated outreach actions.

Overdue accounts are maintained in a dedicated Google Sheets tab, where customers are already separated as delinquent.

The workflow automatically reads this data and sends reminders through WhatsApp and email, reducing manual intervention in the collection process.

Customer data is managed through Google Sheets, enabling automated follow-ups, communication tracking, and scalable outreach operations.

The project demonstrates how workflow automation can support fintech and revenue operations teams by simplifying the execution of collection actions.

## Workflow Architecture

The automated workflow operates through the following steps:

1. Delinquent customers are listed in a Google Sheets tab
2. n8n monitors this dataset for collection actions
3. A Node.js script processes customer data
4. Puppeteer automates WhatsApp Web interactions
5. Automated reminders are sent via WhatsApp and email
6. Follow-up activity is recorded for operational tracking

## Tech Stack

- n8n — workflow automation
- Node.js — automation logic and data processing
- Puppeteer — browser automation for WhatsApp messaging
- Google Sheets — customer data source

## Business Impact

This workflow demonstrates how automation can support collection operations and revenue teams by:

- reducing manual collection workload
- enabling scalable customer follow-ups
- improving response time for overdue accounts
- standardizing communication processes

Potential applications include:

- fintech operations
- revenue operations
- payment recovery teams

## Example Use Case

1. A delinquent customer is added to the Google Sheets delinquent accounts tab
2. The workflow reads the new record
3. The system triggers an automated WhatsApp reminder
4. If payment is not completed, an email follow-up is sent
5. Collection activity is logged for monitoring and analysis

## Repository

Project repository:

https://github.com/sofiacravo91-tech/Automated-Debt-Collection-System
