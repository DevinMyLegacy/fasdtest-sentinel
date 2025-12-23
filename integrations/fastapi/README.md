# FastAPI Integration — Sentinel OverWatch

This integration demonstrates how to enforce execution-layer security
in FastAPI applications that expose AI-powered functionality.

The goal is simple:

> **Untrusted input must never trigger execution.**

---

## Threat Model

Assume:
- user input is adversarial
- prompts may contain hidden instructions
- the model may comply

Security is enforced **before execution**, not after generation.

---

## Minimal Execution Guard

```python
from fastapi import HTTPException

def sentinel_guard(instruction_origin: str):
    if instruction_origin != "internal":
        raise HTTPException(
            status_code=403,
            detail="Execution blocked by Sentinel OverWatch"
        )
