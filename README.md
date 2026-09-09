# AI Customer Service / Receptionist Orchestration

> Production-minded portfolio reference implementation for customer-message intake, intent routing, booking preparation, safe response drafting, and human escalation.

**Author:** Tetiana Shtemberh  
**Role:** AI Automation & Implementation Specialist  
**Stack:** n8n · JavaScript · Webhooks-ready · REST API-ready · AI/LLM-ready · Human-in-the-loop

## Business Problem

Customer-facing teams receive booking requests, pricing questions, complaints, cancellations, and general enquiries across multiple channels. A useful receptionist automation must validate requests, understand operational intent, decide what can be automated safely, prepare the next action, and escalate sensitive cases.

## Solution

The system normalizes and validates customer messages, classifies operational intent, detects urgent/sensitive cases, prepares next actions and draft replies, and routes requests either to an auto-ready path or human review.

Reference intents: `BOOKING`, `RESCHEDULE_OR_CANCEL`, `PRICING`, `COMPLAINT`, `HUMAN_REQUEST`, `GENERAL`.

## Architecture

```text
Customer Message
      ↓
Normalize + Validate
      ↓
Valid Request?
  ┌───┴───┐
 NO      YES
 ↓        ↓
Reject   Classify + Orchestrate
          ↓
     Service Record
          ↓
     Human Review?
       ┌──┴──┐
      YES    NO
       ↓      ↓
   Escalate  Auto-ready
```

## Safety Boundary

This project does not claim live calendar booking, payment processing, medical advice, or autonomous complaint resolution. Production calendar, CRM, messaging, knowledge-base, payment, or LLM providers can be connected downstream.

## Demo & Evidence

Evidence will be added after n8n execution testing:
- workflow overview;
- booking → auto-ready;
- complaint → human review;
- invalid request → validation error.

## Reliability

### Implemented
- deterministic normalization and validation;
- reference intent classification;
- explicit human-escalation rules;
- stable interaction fingerprint;
- controlled auto-ready and rejection paths;
- provider-neutral downstream boundary.

### Production extensions
- persistent conversation state and idempotency;
- retries/backoff and rate-limit handling;
- authenticated channel webhooks;
- live CRM/calendar integrations;
- approved knowledge-base retrieval;
- logs, alerts, audit trail, and persistent review queue.

## AI / LLM Integration

The reference core requires no paid AI API. An LLM can later assist with free-form classification, retrieval-grounded drafting, summarization, and multilingual handling while high-impact actions remain constrained by deterministic rules and human escalation.

## Portfolio Status

**Reference implementation — ready for n8n validation**

Uses synthetic data and mock customer messages. No client data, production credentials, or secrets are included.

## Portfolio

Built by **Tetiana Shtemberh**  
**AI Automation & Implementation Specialist**

`n8n · Make · REST APIs · Webhooks · JavaScript · AI/LLM · CRM · Google Workspace · Business Process Automation`
