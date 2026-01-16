# QUENNE-AI-CODER (Research Prototype)

**QUENNE AI CODER** is a research prototype exploring **governed AI-assisted engineering workflows**—with an emphasis on:
- **system architecture reasoning**
- **secure-by-design development patterns**
- **auditability & traceable decision-making**
- **long-horizon safety constraints (evolution governance)**

> Status: **Research / Experimental**  
> This repository is intended for **prototyping and documentation**. It is **not** production-ready and should not be used for safety-critical or regulated deployments without independent review.

---

## What this project is

QUENNE-AI-CODER is a modular framework for experimenting with an “AI co-pilot” that can:
- translate structured intents into engineering plans
- generate scaffolds, tests, and documentation
- propose threat models and mitigations
- produce reproducible artifacts (design logs, reasoning traces, audit records)

The goal is not “autonomous software engineering.” The goal is **governed assistance**: helpful automation that remains **inspectable, reversible, and aligned** with human oversight.

---

## What this project is not

To set clear expectations, QUENNE-AI-CODER is **not**:
- a claim of “consciousness” or validated sentience
- a claim of quantum advantage without measured benchmarks
- a guarantee of “zero vulnerabilities”
- a compliance-certified product out of the box

If you are looking for verified performance claims, see **Benchmarks** (when available) and the **Research Notes** section.

---

## Key concepts

### 1) Governed Engineering Loop
A workflow pattern designed to keep assistance aligned:

1. **Intent → Constraints** (what you want, what you refuse)
2. **Plan → Risk Review** (threat model + failure modes)
3. **Generate → Test** (code + tests + static checks)
4. **Audit → Approve** (human review gates)
5. **Release → Monitor** (telemetry + rollback posture)

### 2) Traceability by default
Every “generation” can be logged as:
- inputs (intent, constraints)
- outputs (artifacts)
- checks (tests, linters, policies)
- decisions (human approvals)

### 3) Security posture (research baseline)
This repo encourages:
- least privilege configuration
- secrets hygiene
- secure-by-default templates
- post-quantum readiness exploration (optional modules)

---

## Repository layout (proposed)
quenne-ai-coder/
├── src/
│   ├── orchestrator/         # orchestration, pipelines, policies
│   ├── governance/           # constraints, review gates, audit trail
│   ├── security/             # threat modeling, checks, templates
│   ├── adapters/             # tool / model adapters (optional)
│   └── api/                  # REST/WebSocket API (optional)
├── configs/                  # example configs
├── docs/                     # documentation & research notes
├── examples/                 # example intents & outputs
├── tests/                    # unit/integration tests
└── deployments/              # docker/k8s (optional / later)

> If your current code layout differs, we can align this README to your actual structure.

---

## Quick start (local prototype)

### Requirements
- Python **3.10+**
- Recommended: virtual environment (`venv`)

### Install
```bash
git clone https://github.com/<your-org>/<your-repo>.git
cd quenne-ai-coder

python -m venv venv
source venv/bin/activate

pip install -U pip
pip install -r requirements.txt
pip install -e .

Run (example)

quenne --help
# or
python -m src.orchestrator.cli --help

Note: commands depend on your actual entry points. If you share your repo structure/CLI name, I’ll make this exact.

⸻

Example workflow

1) Provide an intent + constraints
intent: "Design a secure service for high-integrity audit logging"
constraints:
  safety_level: "high"
  requirements:
    - "tamper-evident logs"
    - "least privilege"
    - "reversible changes"
  prohibited:
    - "hard-coded secrets"
    - "unsafe eval/exec patterns"

2) Outputs (typical)
   •   architecture outline (Markdown)
   •   threat model (Markdown)
   •   skeleton code + tests
   •   audit trail (JSONL)

⸻

Safety & governance

This project follows a “no silent autonomy” policy:
   •   Human approval gates for consequential changes
   •   Clear rollback paths for generated outputs
   •   Audit logging as a first-class artifact

See:
   •   docs/GOVERNANCE.md
   •   docs/THREAT_MODEL.md
   •   SECURITY.md

⸻

Roadmap (research direction)
   •   v0.x: reproducible pipeline + audit trail + secure templates
   •   v1.x: policy engine + constraint evaluation + sandboxed execution
   •   v2.x: multi-agent planning + long-horizon risk checks + deployment patterns
   •   v3.x: evolution governance patterns (trajectory monitoring, checkpoints)

Roadmap items are research goals and may change.

⸻

Contributing

Contributions are welcome—especially:
   •   secure coding templates
   •   tests & evaluation harnesses
   •   documentation improvements
   •   governance policy modules

See CONTRIBUTING.md.

⸻

License

MIT License (see LICENSE).

If you intend to mix open-source and proprietary components, we should clearly separate those in repo structure and licensing to avoid confusion.

⸻

Citation

If you use this repository in research, please cite:
@software{quenne_ai_coder,
  author = {Santiago, Nicolas and QUENNE Research Institute},
  title  = {QUENNE-AI-CODER: Governed AI-Assisted Engineering (Research Prototype)},
  year   = {2026},
  publisher = {GitHub},
  url    = {https://github.com/<your-org>/<your-repo>}
}


⸻

About

QUENNE Research Institute
Saitama, Japan

Focus areas:
   •   governed intelligence systems
   •   resilient infrastructure architectures
   •   safety, auditability, and long-horizon alignment

# QUENNE-AI-CODER — Architecture

## Status
Research Architecture · Non-Production · Public

---

## 1. Purpose

QUENNE-AI-CODER is a **governed AI-assisted engineering research prototype**.
Its purpose is to explore how AI systems can assist complex engineering tasks **without bypassing human authority, safety constraints, or accountability**.

The architecture prioritizes:
- transparency over autonomy
- auditability over speed
- governance over optimization

---

## 2. Architectural Principles

1. **Human Sovereignty**
   - No irreversible action without human approval.

2. **Traceability**
   - Every generated artifact is traceable to its inputs.

3. **Reversibility**
   - All outputs must be revertible or discardable.

4. **Constraint-First Design**
   - Explicit constraints are evaluated before generation.

5. **Separation of Concerns**
   - Planning, generation, validation, and approval are isolated stages.

---
## 3. High-Level Architecture

Intent
↓
Constraint & Policy Engine
↓
Planning & Decomposition
↓
Generation Modules
↓
Validation & Testing
↓
Audit & Review Gate
↓
Approved Artifacts

No component is permitted to skip a stage.

---

## 4. Core Modules

### Orchestrator
Coordinates the end-to-end workflow and enforces ordering.

### Governance Engine
- Evaluates constraints
- Enforces approval gates
- Maintains decision logs

### Generation Modules
- Code scaffolding
- Documentation
- Test generation
(All sandboxed)

### Validation Layer
- Static analysis
- Test execution
- Policy compliance checks

### Audit Layer
- Immutable logs
- Human approval records

---

## 5. Non-Goals

This architecture does **not** aim to:
- replace human engineers
- claim autonomy or consciousness
- guarantee correctness or security
- outperform expert teams

---

## 6. Research Scope

This repository represents:
- architectural exploration
- experimental tooling
- governance patterns

It does not represent a finished or certified system.

---

## 7. Open Questions

- How should long-horizon risk be evaluated?
- What governance signals scale with system complexity?
- Where should automation stop by default?

These questions are intentionally left open.

GOVERNANCE.md

# QUENNE-AI-CODER — Governance Framework

## Status
Foundational · Required · Public

---

## 1. Governance Philosophy

This project follows a single governing principle:

> **Assistance may scale. Authority must remain human.**

Governance is treated as an architectural feature, not a policy add-on.

---

## 2. Mandatory Human Oversight

Human approval is required for:
- externally visible changes
- security-sensitive artifacts
- deployment-related output
- irreversible transformations

---

## 3. Governance Gates

| Stage | Gate |
|-----|-----|
| Planning | Constraint review |
| Generation | Sandbox isolation |
| Validation | Automated checks |
| Release | Human approval |

Skipping gates is prohibited.

---

## 4. Decision Logging

Each run produces:
- input intent
- declared constraints
- generated artifacts
- validation results
- approval decision

Logs are append-only.

---

## 5. Authority Boundaries

The system:
- may propose
- may generate drafts
- may suggest mitigations

The system may **not**:
- self-approve
- self-deploy
- self-modify governance rules

---

## 6. Drift Prevention

Repeated patterns are monitored for:
- reduced human involvement
- narrowing decision diversity
- silent escalation of autonomy

If detected, the system must halt and require review.

---

## 7. Governance Is Not Optional

Any derivative work claiming alignment with QUENNE principles must preserve these rules.

THREAT_MODEL.md
# QUENNE-AI-CODER — Threat Model

## Status
Research · Non-Exhaustive · Public

---

## 1. Threat Modeling Scope

This document addresses risks related to:
- misuse
- over-trust
- automation bias
- insecure outputs
- governance bypass

---

## 2. Threat Categories

### T1 — Automation Bias
Risk: Humans over-trust generated outputs.

Mitigation:
- Mandatory review
- Explicit uncertainty labeling

---

### T2 — Unsafe Code Generation
Risk: Insecure defaults or patterns.

Mitigation:
- Secure templates
- Static analysis
- Prohibited-pattern checks

---

### T3 — Scope Creep
Risk: Prototype treated as production.

Mitigation:
- Clear disclaimers
- No production defaults
- Manual deployment barriers

---

### T4 — Governance Erosion
Risk: Approval gates bypassed over time.

Mitigation:
- Immutable logs
- Gate enforcement in orchestrator

---

## 3. Out-of-Scope Threats

This project does not currently address:
- nation-state attacks
- hardware-level exploits
- certified compliance requirements

---

## 4. Living Document

This threat model evolves with research findings.

SECURITY.md

# Security Policy

## Reporting Security Issues

If you discover a security issue:

- **Do not open a public issue**
- Email: security@quenne.jp (placeholder)

Provide:
- description
- reproduction steps
- potential impact

---

## Scope

This repository:
- is a research prototype
- has no security guarantees
- is not production-hardened

---

## Safe Use Guidelines

- Do not deploy to public networks
- Do not use with sensitive data
- Review all generated code manually

---

## Responsible Disclosure

We aim to acknowledge reports within 7 days.

DISCLAIMER.md

# Disclaimer

This repository is provided **for research and experimentation purposes only**.

- No guarantees of correctness, security, or fitness
- No claims of autonomy or consciousness
- No certification or regulatory approval

Use at your own risk.

The authors assume no liability for misuse or misinterpretation.

---

## Interpretation Notice

Any references to:
- intelligence
- cognition
- governance
- alignment

are **architectural metaphors**, not claims of sentience or capability.

CONTRIBUTING.md

# Contributing to QUENNE-AI-CODER

Thank you for your interest.

---

## Contribution Principles

We welcome contributions that:
- improve clarity
- increase safety
- strengthen governance
- enhance documentation

---

## Contribution Rules

- No unverifiable performance claims
- No autonomy-expanding changes without discussion
- No removal of governance gates

---

## Process

1. Fork the repo
2. Create a feature branch
3. Add tests or documentation
4. Open a Pull Request with rationale

---

## Code Style

- Python: Black, isort
- Tests: pytest
- Docs: Markdown, clear language

---

## Review Criteria

PRs are evaluated for:
- technical correctness
- governance impact
- clarity and restraint



