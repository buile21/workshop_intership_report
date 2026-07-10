---
title: "AWS First Cloud AI Journey Community Day"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Reflection Report: “AWS First Cloud AI Journey Community Day”

### Event Objectives

- **Exploring the limits of GenAI:** Delving into the technical nature of Large Language Models (LLMs), from handling non-determinism to building enterprise-grade Multi-Agent systems.
- **Mastering AWS infrastructure:** Updating cost optimization strategies, enhancing security from the Edge to the Origin server, and automating security audits.
- **Product building mindset:** Listening to hard-earned lessons from real-world projects and the "sprint" process in Hackathons to turn raw ideas into fully functional applications.

---

### Core Content Summary

#### 1. Enterprise-Grade Multi-Agent System: The Startup Credit Scoring Problem
- **Speaker:** Vy Lam - Senior Business Systems Analyst, VPBank
- **Real-world pain point:** Startups are often "ignored" by traditional credit models due to a lack of historical financial data and unstable cash flows.
- **Transformative solution:** Shifting from a Single Agent (which easily hits context limit barriers and lacks cross-checking) to a **Multi-Agent** architecture. This system simulates a "Virtual Credit Committee" with independent roles: *Financial Analyst, Market Analyst, Team Evaluator, Risk Assessor*, and *Compliance*.
- **Results:** Ensures transparency through parallel processing, reduces both time and costs by up to 95% per funding decision while firmly maintaining security barriers.

#### 2. Decoding the "Non-Determinism" of LLMs
- **Speaker:** Duc Dao - Solution Architect, Cloud Kinetics
- **The Temperature = 0 illusion:** Engineers often assume that setting **Temperature = 0** guarantees a fixed output from the AI. In reality, the variance can still reach up to 15%.
- **Technical perspective:** Because floating-point operations on GPUs running in parallel do not have full associativity, minuscule rounding errors in the *logit* can flip the result of the *argmax* function.
- **Survival strategy:** Embrace the probabilistic nature of LLMs. Instead of forcing the AI, use constrained outputs (*JSON mode*). The ideal setting is **Temperature = 0.1** to maintain stability without falling into infinite repetitive loops.

#### 3. 36 Life-or-Death Hours at Lotus Hacks 2026: Project UTMorpho
- **Speaker:** Team VIB
- **The Journey:** 36 sleepless hours to build UTMorpho – a Sketch2App tool using Claude Vision to convert sketch drawings into React/Tailwind code.
- **Crises encountered:** Hitting Claude's API Token limits, getting stuck in "Scope Creep" (greedily stuffing features), and the nightmare of AI generating junk code causing widespread bugs.
- **Key takeaways:** In Hackathons or real-world projects, the best ideas are born from dead ends. Team Sync is a matter of survival, and the unwritten rule is: Make the core value work first before thinking about fancy add-ons.

#### 4. From Edge To Origin: Optimizing with CloudFront
- **Speaker:** Nguyen Tuan Thinh - DevOps Engineer
- **The Problem:** The nightmare of bloated network infrastructure costs during traffic "spikes" or DDoS attacks.
- **The CloudFront Weapon:** Owning over 700+ global PoPs, CloudFront stops DDoS in its tracks from afar via AWS Shield and WAF.
- **Optimization tips:** - 100% free Data Transfer Out (*DTO*) from AWS Origins.
  - Use *Origin Access Control (OAC)* to "cloak" the origin server from the public internet.
  - Heavily leverage *Mutual TLS (mTLS)* and *Lambda@Edge* for direct edge computing.

#### 5. Context Is Everything: Making AI Actually "Work" For You
- **Speaker:** Tinh Truong - Platform Engineer, GoTymeX
- **Root cause:** Silly answers from AI are mostly not due to a bad model, but noisy Context. The "Internet Puller" syndrome—dumping a mess of random documents into the prompt—only wastes tokens and degrades accuracy.
- **AI Design Mindset:** A good system must have clear goals and strict constraints (regarding format, technology, and success criteria). The future of AI does not lie in isolated prompts, but in building a "Second AI Brain" (A context system with memory) for effective long-term personalization.

#### 6. Friendly AI Assistant with Amazon Q
- **Speaker:** Pham Ng Hai Anh - G-AsiaPacific Vietnam, AWS Community Builder
- **Use Case:** Using Amazon Q as a PM Assistant to handle boring paperwork: auto-generating Minutes of Meeting (MoM), sending follow-up emails, and scheduling.
- **Enterprise Highlights:** Its power lies in the ability to plug directly into 40+ enterprise data sources while strictly adhering to RBAC and Guardrails. Additionally, using GenAI to automate infrastructure security audits (*Auto Audit*) opens up an extremely promising direction for Cloud systems.

---

### Reflections & Practical Applications

The seminar wasn't just theoretical presentations; it actually provided me with a cognitive "toolkit" to apply directly to my current backend development projects:

1. **Standardizing AI system outputs:** I will no longer stubbornly force **Temperature to 0**. Instead, I'll strictly apply *JSON mode* combined with a *Retry* mechanism to ensure the raw returned data is always perfectly structured. This is extremely crucial when handling real-time data streams for the revenue forecasting system, preventing the downstream Lambda functions from crashing due to parsing errors.
2. **Security and data flow optimization:** Applying Mr. Thinh's lesson to configure *CloudFront* as an iron shield. Using *OAC* to hide S3 buckets and sensitive endpoints from the public internet will make the infrastructure architecture much more tightly sealed and professional.
3. **Context Management:** Instead of feeding data recklessly, I learned how to filter and pass only the truly decisive parameters and historical data into models (like Amazon Forecast or LLMs) to optimize computing costs and increase accuracy.
4. **"Product building" Mindset:** The lesson from Team VIB reminded me of focus. Whether building a small module or a large architecture, prioritizing the core flow to run smoothly from A-Z is mandatory before thinking about scaling up or sketching out secondary features.

> **Conclusion:** The event helped me step out of the pure "coding" perspective and shift toward the mindset of a systems engineer: securely connecting Cloud services together, optimizing costs, and always having a fallback plan for the "non-determinism" of modern AI technologies.

#### Some pictures from the event
![](../../images/4-EventParticipated/4.1-Event1/event.png)