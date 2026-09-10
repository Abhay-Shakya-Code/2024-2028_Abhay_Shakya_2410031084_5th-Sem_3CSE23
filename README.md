# 2024-2028_Abhay_Shakya_2410031084_5th-Sem_3CSE23
# NetSage AI

### Local AI-Assisted Cisco Network Troubleshooting Assistant

**B.Tech Computer Science & Engineering (Core)**
**3rd Year • 5th Semester • Section 3CSE23**

---

## Student Information

| **Field**                      | **Details**                                  |
| ------------------------------ | -------------------------------------------- |
| **Student Name**               | ABHAY SHAKYA                                 |
| **Roll Number**                | 2410031084                                   |
| **Program**                    | B.Tech Computer Science & Engineering (Core) |
| **Year**                       | 3rd Year                                     |
| **Semester**                   | 5th Semester                                 |
| **Section**                    | 3CSE23                                       |
| **Academic Batch**             | 2024–2028                                    |
| **Project Domain**             | Artificial Intelligence                      |
| **Organization / Institution** | IILM University                              |
| **Training / Program**         | Introduction to Modern AI                    |
| **Program Association**        | Cisco Networking Academy                     |

---

## About the Project

**NetSage AI** is a local AI-assisted Cisco network troubleshooting application designed to support the diagnosis of common networking problems in a structured and explainable manner.

The application accepts a networking problem in natural language and uses **Ollama with Llama 3.2** to generate a structured troubleshooting recommendation.

A diagnosis may include:

* Likely Root Cause
* OSI Layer
* Networking Concept
* Severity
* Evidence to Check
* Cisco SHOW Command
* Safe Proposed Fix
* Confidence
* Human Review Requirement

NetSage AI combines the flexibility of an AI language model with deterministic validation and a mandatory human-review workflow.

---

## Key Idea

NetSage AI is designed as a **decision-support system**, not an autonomous network-management system.

The overall workflow is:

```text
User Problem
     │
     ▼
Streamlit Interface
     │
     ▼
Ollama Local API
     │
     ▼
Llama 3.2
     │
     ▼
Structured Diagnosis
     │
     ▼
Deterministic Safety Validation
     │
     ▼
Human Verification
     │
     ├── Accept
     ├── Needs Revision
     └── Reject
     │
     ▼
Review Log
     │
     ▼
Dashboard / Reports
```

---

## Core Features

### AI-Assisted Diagnosis

NetSage uses **Llama 3.2 through Ollama** to analyze the described networking issue and generate a structured troubleshooting diagnosis.

### Evidence-Based Troubleshooting

The system identifies the evidence that should be checked and recommends relevant Cisco `SHOW` commands before a fix is accepted.

### Deterministic Safety Validation

AI-generated recommendations are passed through software-based validation rules to check whether the diagnosis and proposed action satisfy predefined safety and troubleshooting constraints.

### Human Review Gate

NetSage requires a human reviewer to verify the diagnosis before it can be accepted.

The reviewer can:

* **Accept** the diagnosis
* **Edit / Request Revision**
* **Reject** the diagnosis

### Post-Fix Verification

After a proposed fix is reviewed, the system supports verification of the expected network state and records the result.

### Logging and Reporting

Review decisions, corrections, validation results, and verification outcomes can be recorded for later analysis through logs, dashboards, and reports.

---

## System Architecture

```text
┌──────────────────────────────┐
│        User / Engineer       │
└──────────────┬───────────────┘
               │ Network Problem
               ▼
┌──────────────────────────────┐
│      Streamlit Interface     │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│      Ollama Local API        │
│        Llama 3.2             │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│   Structured AI Diagnosis    │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│ Deterministic Rule Checker   │
│  & Safety Validation Layer   │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│       Human Review Gate      │
└──────────────┬───────────────┘
        ┌──────┼──────┐
        ▼      ▼      ▼
     Accept  Revise  Reject
        │      │      │
        └──────┼──────┘
               ▼
┌──────────────────────────────┐
│   Review Logs & Verification │
└──────────────┬───────────────┘
               ▼
┌──────────────────────────────┐
│       Dashboard / Reports    │
└──────────────────────────────┘
```

---

## Technologies & Tools

| **Technology / Tool**           | **Purpose**                                      |
| ------------------------------- | ------------------------------------------------ |
| **Python**                      | Core application and logic                       |
| **Streamlit**                   | Web-based user interface                         |
| **Ollama**                      | Local LLM serving                                |
| **Llama 3.2**                   | AI-based diagnosis generation                    |
| **Cisco Packet Tracer**         | Network topology and troubleshooting environment |
| **Rule Checker**                | Deterministic validation of AI recommendations   |
| **JSON / Structured Schemas**   | Standardized diagnosis representation            |
| **CSV / Logs**                  | Results, review and analysis data                |
| **Dashboard / Reporting Layer** | Visualization and project evaluation             |

---

## Troubleshooting Workflow

1. The user enters a networking problem.
2. NetSage sends the problem to the local AI model.
3. The AI generates a structured diagnosis.
4. Deterministic rules validate the generated recommendation.
5. The system identifies supporting evidence and troubleshooting commands.
6. A human reviewer evaluates the recommendation.
7. The diagnosis can be accepted, revised, or rejected.
8. The final decision is recorded in the review log.
9. The proposed resolution can then be verified.
10. Results are reflected in reports and dashboards.

---

## Example Diagnosis Output

A typical NetSage recommendation can contain:

```text
Problem:
PC can obtain an IP address but cannot reach the server.

Likely Root Cause:
Possible VLAN, routing, ACL, or gateway-related issue.

OSI Layer:
Layer 2 / Layer 3

Evidence to Check:
- VLAN membership
- Default gateway
- Routing table
- ACL configuration
- Interface status

Recommended SHOW Command:
show vlan brief
show ip route
show access-lists

Proposed Fix:
Review the identified configuration issue before applying any change.

Confidence:
AI-generated confidence score

Human Review:
Required
```

---

## Safety & Responsible AI

NetSage AI is intentionally designed with **human oversight**.

The system does not treat an AI-generated recommendation as automatically correct. Instead, the recommendation is checked through deterministic validation and presented to a human reviewer before acceptance.

This design helps reduce the risk of:

* Incorrect AI-generated diagnoses
* Unsafe configuration recommendations
* Unsupported troubleshooting actions
* Blind reliance on language-model output

The project therefore follows a **human-in-the-loop decision-support approach**.

---

## Project Structure

```text
NetSage-AI/
│
├── app/
│   ├── Streamlit interface
│   └── dashboard components
│
├── core/
│   ├── AI diagnosis
│   ├── rule checker
│   ├── validation
│   ├── human review
│   └── verification
│
├── prompts/
│   └── AI troubleshooting prompts
│
├── test/
│   └── test cases and evaluation files
│
├── data/
│   └── cases, logs and result files
│
├── packet_tracer/
│   └── network topology files
│
├── reports/
│   └── generated reports and analysis
│
└── README.md
```

---

## Project Objectives

* Develop an AI-assisted troubleshooting workflow for Cisco networking problems.
* Use a local LLM to generate structured network diagnoses.
* Connect AI output with deterministic validation rules.
* Provide evidence-based troubleshooting commands.
* Introduce a mandatory human-review mechanism.
* Maintain review and verification records.
* Demonstrate responsible use of AI in network troubleshooting.

---

## Scope

NetSage AI focuses on **decision support for common Cisco network troubleshooting scenarios**.

The current implementation is intended for:

* Learning and academic demonstration
* Packet Tracer-based network troubleshooting
* AI-assisted diagnosis
* Evidence-driven troubleshooting
* Human-reviewed recommendations
* Experimental evaluation of AI-assisted networking workflows

It is not intended to directly modify production network devices without appropriate human authorization and verification.

---

## Future Scope

Possible future improvements include:

* Retrieval-Augmented Generation (RAG) using a larger networking knowledge base
* Support for additional Cisco devices and platforms
* Integration with more real-time network telemetry
* Improved diagnosis benchmarking
* More extensive automated verification
* Multi-model diagnosis comparison
* Advanced network topology awareness
* Deployment as a secure enterprise troubleshooting assistant

---

## Conclusion

**NetSage AI** demonstrates how artificial intelligence can be integrated with conventional networking diagnostics to create a safer and more explainable troubleshooting workflow.

Instead of relying only on an AI-generated answer, the system combines **AI reasoning, deterministic validation, human review, and verification** to support network troubleshooting decisions.

The project highlights a practical application of AI in networking while keeping human expertise at the center of the final decision.

---

## Keywords

`Artificial Intelligence` `Cisco Networking` `Network Troubleshooting` `Llama 3.2` `Ollama` `Packet Tracer` `Human-in-the-Loop` `Decision Support`
