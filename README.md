# Multi-Agent-Mental-Health-Therapeutic-System
The system is an agentic mental health framework built with LangGraph. It uses a Q-Learning agent to optimize patient screening and dynamically transitions between Motivational Interviewing (MI) and CBT interventions based on real-time risk scores. Demonstrates adaptive multi-agent orchestration and stateful AI memory.
# CaiTI: Conversational AI for Therapeutic Intervention

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![LangGraph](https://img.shields.io/badge/LangGraph-State%20Management-orange)
![AI Agents](https://img.shields.io/badge/Architecture-Multi--Agent-green)
![Reinforcement Learning](https://img.shields.io/badge/Algorithm-Q--Learning-red)

**CaiTI** (Context-aware AI Therapeutic Intervention) is an advanced multi-agent system designed to simulate personalized mental health support. Unlike linear chatbots, CaiTI utilizes **Reinforcement Learning (RL)** and **Graph-based orchestration** to dynamically adapt its screening strategy based on real-time patient risk assessment.

This project demonstrates the application of **Agentic AI** in sensitive domains, featuring state persistence, context-aware memory, and the seamless transition between diagnostic screening and active therapeutic frameworks (CBT & Motivational Interviewing).

---

## 🧠 Core Features & Architecture

The system is built on **LangGraph**, orchestrating a directed cyclic graph of specialized agents. It moves beyond simple prompt engineering by implementing a custom **Q-Learning Agent** that "learns" which health dimensions to prioritize during a conversation.

### 1. Adaptive Screening (The RL "Selector")
* **Dynamic Pathing:** Instead of a fixed questionnaire, the `Selector` agent uses a Q-Table to decide which of the **37 mental health dimensions** (e.g., *Mood, Sleep, Social Support*) to investigate next.
* **Exploration vs. Exploitation:** The agent balances exploring new topics versus drilling down into known high-risk areas based on the patient's profile.
* **Reward Mechanism:** The model receives positive reinforcement when it successfully identifies high-risk areas (Score 2), optimizing the screening process over time.

### 2. Multi-Modal Intervention
The workflow supports two distinct therapeutic modalities based on immediate needs:
* **Motivational Interviewing (MI):** Triggered *reactively* during screening. If a user expresses a high-risk sentiment, the system pauses data collection to provide immediate, non-judgmental validation.
* **Cognitive Behavioral Therapy (CBT):** Triggered *proactively* after screening. The system identifies the single highest-risk dimension and initiates a structured 3-stage CBT loop:
    1.  **Identify:** Isolate the negative thought.
    2.  **Challenge:** Examine evidence for/against the thought.
    3.  **Reframe:** Guide the user to construct a balanced perspective.

### 3. Context-Aware Personas
To ensure robustness, the system loads detailed JSON patient profiles (e.g., "Alice - Generalized Anxiety", "Bob - Depression"). The agents respect specific boundaries (e.g., "Do not discuss past trauma") and tailor questions to the patient's specific context.


