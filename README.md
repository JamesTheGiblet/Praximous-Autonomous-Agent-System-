# 🌀 Praximous Autonomous Agent System (PAAS)

MODULARITY IS MYTHOS // GLYPH IS IDENTITY // DESIGN IS RITUAL

⚠️ **Creator's Note**  
Praximous is an independent system, designed and developed entirely as a personal project. It is not affiliated with or derived from my professional employment. All ideas, code, and documentation presented here are original works under my personal authorship.

This codex presents **Praximous**, a secure, modular, and on-premise multi-agent framework designed to offload routine cognitive labor from your Copilot and human staff. It enables containerized agents to autonomously handle tasks, learn from feedback, and escalate only when needed.

Version 2.1.0 introduces practical fixes for deployment at scale: a centralized skill pantheon, manual Copilot fallback, strict local resource control, and rule-based learning refinement.

---

## 2. Ritual Architecture

### 2.1 High-Level Glyph
- A distributed, containerized multi-agent system.
- Agents retrieve task "glyphs" from a central Skill Pantheon.
- All data processing remains local and secure.
- Copilot fallback requires a human-in-the-loop approval ritual.

### 2.2 Altar Environment
- **Deployment Mode**: On-premise Linux servers (Ubuntu / RHEL).
- **Network Model**: VLAN isolation only.
- **Containerization**: Podman (rootless) or optional Kubernetes.
- **Resource Control**: systemd + Podman (MemoryMax, CPUQuota).

---

## 3. Modular Tenets

### 3.1 Agent Core
Each agent is composed of:
- `Praxis-Agent-Core`: FastAPI microservice.
- `SyntaxLearner`: Enforces formatting via spaCy.
- `TaskExecutor`: Executes named skills (cliexec, markdowngen, etc.).
- `MemoryEngine`: TinyDB-based memory store.
- `SelfImprover`: Logs Copilot feedback, refines behavior (Phase 1: rule-based).

### 3.2 Skill Pantheon
A central codex for all agent skills:
- **Storage**: Git-style object store or shared filesystem.
- **Metadata DB**: PostgreSQL / Redis.
- **Skills include**: `skill_id`, `category`, `permissions`, `filepath`, `version`.

**Agent Flow**:
- Checks local skill cache.
- Queries Skill Pantheon if missing.
- Verifies and executes in sandbox.

### 3.3 Copilot Oversight
- A minimal fallback layer behind the Mentor Bridge.
- Requires manual approval from authorized staff.
- Annotated results are returned to the SelfImprover for agent learning.

### 3.4 Monitoring Augury
- **Resource monitoring**: Netdata or Prometheus + Grafana.
- **Lore-keeping**: Execution stats, failure rates, agent maturity levels.

---

## 4. Vigils & Trials

| Mechanism       | Purpose                                      |
|------------------|----------------------------------------------|
| RBAC            | Agent-level and pantheon-level scoping        |
| Audit Trail     | Immutable logs for each agent invocation      |
| Data Sandbox    | Read-only execution folders per agent         |
| Manual Escalation | 2FA + role verification for fallback        |

---

## 5. Operational Rituals

### 5.1 Agent Task Invocation

flowchart TD
    A[Builder submits task] --> B[Agent receives task]
    B --> C{Skill available locally?}
    C -->|Yes| D[Run skill in sandbox]
    D --> E[Log success to Monitor]
    E --> F[SelfImprover updates MemoryEngine]
    C -->|No| G[Query Skill Pantheon]
    G --> H[Download + verify skill codex]
    H --> D
    H -->|Skill invalid| I[Escalate to Copilot Request]
    I --> J[Manual Approval Required]
    J --> K[Copilot processes task]
    K --> L[Result returned and annotated]
    L --> M[SelfImprover updates logic]

5.2 Skill Registration Ritual

A builder uploads a .py skill to the Pantheon.

Automated linting + sandbox test run is performed.

If passed → metadata is indexed and versioned.

Agents may request based on permissions.



---

6. Path of Evolution

Each phase is detailed in modular .md scrolls:

Phase	Scope	Outcome

Phase 1	Core Agent System + Skill Pantheon	POC for execution and logging
Phase 2	Alpha Deployment in real rituals	Copilot fallback + feedback loop
Phase 3	Enhancement Layer	Skill search + agent tiering
Phase 4	Federation Deployment	Multi-team agent mesh
Phase 5	Ecosystem Ritualization	Contributor onboarding + licensing



---

7. Future Aspirations

Embedding-based skill discovery

Skill-sharing across isolated environments

Agent tiering (Executor, Critic, Researcher)

Role-specific UI and deployment profiles

A premium roadmap for external licensing



---

8. Licensing & Authorship

This framework is designed for cross-sector use. All code, architecture, and supporting docs are authored and owned by the creator unless explicitly licensed or transferred.

Licensing Notice:
All intellectual property in this repository is the sole creation of James The Giblet and is not affiliated with any employer or third-party institution.

A Suggested Deployment Glyph:

README.md: Free for public use

Roadmaps, deployment guides: Paid tiers or consulting

Full ownership remains with James The Giblet, unless sold or open-sourced



---

🌐 Explore the Vault. Build your own Pantheon.
💬 Collaborations, rituals, and questions are welcome.

---
