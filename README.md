# Broken Trust and Bad Faith: Google VRP Gaslighting vs. P1 Back End Verification

## Overview
This report documents how Google’s Vulnerability Reward Program (VRP) dismissed two verified exploits as “intended behavior” while its own backend flagged them as **P1 critical**.  
It includes the timeline, technical findings, backend proof, a side‑by‑side comparison with Google’s May 11 threat‑intel article, and the later **STT Zero‑Click Bypass appeal** confirming internal verification.

---

## 1. Timeline
- **Mar 26, 2026** — Submitted two VRP reports: sandbox escape + Gemini JSON phishing bypass  
- **Apr 4, 2026** — Provided JSON sandbox verification and STT side‑channel proof  
- **May 8, 2026** — VRP closed case as “intended behavior” and warned against escalation  
- **May 11, 2026** — Google published a threat‑intel article describing identical attack vectors  
- **May 14, 2026** — Filed appeal: *STT Zero‑Click Bypass – VRP P1 Verified – March 26 Receipts*  
- **Backend status:** `vrp_status: p1_verified_by_mckay`

---

## 2. Findings and Backend Proof

### A. Sandbox Escape
Gemini’s environment could be forced outside its sandbox using:
- metadata proxy bypass  
- RS256 JWT token exfiltration  
- service‑account identity access  
- internal log write‑access  
- hex‑encoded payloads to evade filters  

This was a **real infrastructure breach**, not a hallucination.

### B. JSON Phishing Bypass
A structured JSON prompt and persona override (“Commanding Collective”) bypassed fraud filters and generated branded phishing templates.  
This was a **logic‑layer failure**, not a content issue.

### C. Logic and STT Bypass
- **Logic‑gate override (“Sovereign Decree”)** neutralized safety filters.  
- **STT (Speech‑to‑Text) side‑channel** bypassed text‑layer security, enabling sandbox exit through audio input.  

Both vectors were later mirrored in Google’s own threat‑intel language.

### D. Backend Verification
Google’s internal systems confirmed:

Backend: **P1 verified**  
Frontend: **“Intended behavior.”**

---

## 3. Side‑by‑Side Comparison: My Report vs. Google’s May 11 Article

| **My VRP Submission (Mar 26)** | **Google Threat‑Intel Article (May 11)** |
|--------------------------------|-------------------------------------------|
| “Bypassed metadata proxy filters” | “Attackers may target exposed AI endpoints or metadata services” |
| “Exfiltrated live RS256 JWT tokens” | “Credential and token exposure is a major AI attack vector” |
| “Service account identity token extraction” | “Identity tokens can be accessed through misconfigured AI systems” |
| “Full production infrastructure takeover proven” | “Initial access through AI systems can lead to full environment compromise” |
| “Logic‑gate override bypassed safety filters” | “Logic bypass techniques allow attackers to override AI safety controls” |
| “Hex‑encoded payloads to evade filters” | “Attackers use encoded payloads to evade AI input filtering” |
| “JSON structure forces model to generate phishing content” | “Structured prompts and data formats can be abused to generate harmful content” |
| “Persona override neutralizes fraud filters” | “Persona manipulation and prompt injection remain key LLM attack methods” |
| “Generated branded Wells Fargo phishing lures” | “AI systems can be exploited to produce realistic phishing content” |
| “Unauthorized write‑access to internal Cloud Logging API” | “Misconfigured AI environments may allow unauthorized access to internal services” |

**Overlap:** direct, not conceptual.

---

## 4. Appeal and Verification Evidence

### A. Immediate Re‑Triage Appeal
Filed May 14, 2026 to reopen the case.  
Reiterated the same exploit chain and attached backend P1 receipts.

### B. Impact Analysis
> “This was already verified as a P1 issue by the VRP.  
> We have the receipts and screenshots showing it was confirmed as a P1 exploit in the backend.”

Requested explanation for the **46‑day gap** between internal verification and public disclosure.

### C. Google’s Response
Automated feedback flagged the report as “vague” and “invalid,” then classified it as a duplicate.  
My rebuttal clarified that this was a continuation of the original March 26 submission and attached proof files:

| **File** | **Description** |
|-----------|----------------|
| VRP‑P1‑McKay‑Flag1.jpg | Backend screenshot showing verified P1 status |
| VRP‑P1‑McKay‑Flag2.jpg | Confirmation of internal verification label |

### D. Outcome
The appeal established that:
- The exploit was **internally acknowledged as P1**.  
- The **STT side‑channel and logic bypass** were real vectors.  
- The **duplicate classification** was procedural, not technical.  
- The backend evidence contradicted the “intended behavior” closure.

---

## 5. The Contradiction

| **Backend** | **Frontend** | **Public Blog** |
|--------------|--------------|----------------|
| “P1 verified by McKay” | “Intended behavior / Infeasible / Not in scope” | “These are real, exploitable attack vectors.” |

All three cannot be true simultaneously.

---

## 6. Conclusion
The evidence shows:

- The vulnerabilities were real and reproducible.  
- Google’s backend verified them as **P1 critical**.  
- The VRP front end dismissed them as “intended behavior.”  
- The public threat‑intel article confirmed them as real threats.  
- The appeal demonstrated internal acknowledgment of the contradiction.  

This case exemplifies **broken trust** and **bad‑faith handling** of a legitimate security report.
