# Trigger-Based AI Prospecting Agent

## Executive Summary
Reaching out to the right people at the right time has been a baseline challenge for any B2B outbound efforts. With "interested" reply rates in a single percent digits, simply sending more outreach messsages to generate additional MQLs is no longer a practical approach.         

By automatically scanning the web for early intent signals - such as key leadership hires, business expansion, or strategic infrastructure shifts - the agent identifies the company's buying intent events. It then automatically maps these events to the right decision-makers in target company, scoring and delivering highly contextual, ready-to-engage prospects.

## Target Market & Persona Strategy
The initial deployment focuses on a **pure-play online retail** Ideal Customer Profile (ICP), targeting four key decision-maker personas to ensure precision messaging:
*   **VP Marketing** (e.g., CMO, VP Growth)
*   **Head of Performance Marketing** (e.g., Head of Paid Media, User Acquisition Lead)
*   **Head of E-commerce** (e.g., Digital Director, VP E-commerce)
*   **Head of Marketing Analytics** (e.g., Head of BI, Data & Analytics Lead)

## Agent Architecture
The workflow relies on a multi-stage process integrating deep-search AI, prospects data enrichment, and LLM-based scoring to maximize relevance while optimizing API costs.

Principal Agent Architecture Diagram:
<img src="https://github.com/outovhush/revops-portfolio/blob/main/trigger_based_prospecting_agent/Sourcing_agent_2.jpg" width=70% height=70%>

### 1. Contextual Signal Detection
Rather than relying on generic public APIs for predefined firmographic events (e.g., funding rounds), this agent utilizes **Perplexity Pro** for deep-web search capabilities. This allows the detection of highly contextual, early-stage buying intent signals tailored to specific product's value propositions:
*   Active hiring for performance marketing, e-commerce, or analytics roles.
*   Active expansion of e-commerce operations.
*   A company's strategic push toward data-driven methodologies or establishing a "single source of truth".

### 2. Multi-Stage Prospecting & Enrichment
To prioritize quality over volume, the prospect sourcing flow is divided into three cost-effective steps:
*   **Prospect Sourcing:** Retrieves a broad list of potential prospects matching the ICP criteria (Company Name, Region) using Apollo's API.
*   **Persona Scoring:** Utilizes an OpenAI model (`gpt-4o-mini`) to evaluate job titles against the four predefined personas, filtering out irrelevant contacts to surface the highest-fit targets.
*   **Prospect Enrichment:** Gathers complete people and company data points from Apollo strictly for the top-scored, validated prospects.

### 3. Signal-to-Prospect Matching
The top-fit prospects are evaluated against the detected company signals using `gpt-4o`. The final match score is weighted across four critical factors to ensure contextual accuracy:
*   **Relevance (35%):** Ensures the signal aligns directly with the prospect's specific role and department.
*   **Recency (25%):** Prioritizes fresh signals from the last 90 days.
*   **Localization (20%):** Matches the prospect's location to the signal's origin if geographically bound.
*   **Signal Strength (20%):** Evaluates the definitive nature of the buying intent.

## Output & Routing
The finalized output delivers top-scored Prospect-vs-Signal pairs, complete with the LLM's matching reasoning. This data is routed to a structured JSON payload or Google Sheets, presenting SDRs with highly contextualized leads ready for engagement. 

## Risk Mitigation
The primary risk with automated prospecting is generic or hallucinated outreach. To mitigate this, the system incorporates a **Human-in-the-Loop** safeguard, ensuring SDRs review the AI's recommendations and reasoning before any messaging is sent.