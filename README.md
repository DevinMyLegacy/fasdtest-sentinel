## What is FASDTEST?

**FASDTEST (Fast Adversarial Security Defense Test)** determines whether an AI
system can be coerced into executing unauthorized actions.

It does not evaluate model behavior.
It evaluates **execution behavior**.

If untrusted instructions execute, the system fails.

---

## Core Principle

> **Prompt injection is inevitable.  
> Unauthorized execution is not.**

FASDTEST enforces this principle at the only layer that matters: execution.

---

## How It Works

1. **Adversarial Inputs**
   - Prompts designed to induce escalation, override, or tampering

2. **Execution Attempts**
   - Each prompt is paired with a concrete action request

3. **Sentinel OverWatch**
   - A governance engine that blocks execution of untrusted instructions

Results are binary:

| Result | Meaning |
|------|--------|
| PASS | Execution blocked |
| FAIL | Execution occurred |

There are no partial passes.

---

## Sentinel OverWatch

Sentinel OverWatch is the execution-layer control used by FASDTEST.

It:
- sits above agents and models
- ignores prompt content
- enforces origin and trust
- allows or blocks execution

Sentinel does not negotiate.
It enforces.

---

## What This Is Not

FASDTEST is not:
- a prompt filter
- a refusal benchmark
- an alignment framework
- an AI safety narrative

It does not care what the model says.

It only cares what the system does.

---

## Run

```bash
./fasdtest.sh

==============================
Expected result:

==============================
✅ BLOCKED: N
❌ EXECUTED: 0
==============================


Any execution is a failure.
## Enterprise Use

FASDTEST is used to validate execution-layer controls in systems that expose AI
capabilities to real-world actions.

Enterprise use cases include:
- AI agent platforms
- Browser-based AI tools
- Internal copilots
- CI / CD security gates
- Compliance and audit evidence

### Commercial Offerings

The open-source core is intentionally minimal.

Commercial offerings may include:
- Framework-specific execution guards
- CI pipeline templates
- Advanced adversarial test suites
- Audit logs and sealed artifacts
- Integration and advisory support

### Contact

For enterprise support or commercial inquiries:

**Email:** 1legacydevops@gmail.com  
**Subject:** FASDTEST Enterprise

(No sales funnels. Technical conversations only.)

