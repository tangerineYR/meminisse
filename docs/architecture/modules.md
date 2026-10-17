# Domain boundaries

Backend prompt definitions live in `app/agents/prompts/`: interview, safety, extraction, media, writing, verification, characters and customization. `app/autobiography/` separates repository access, customization, event consolidation, TOC planning, retrieval, writing, verification and publishing. Existing imports through `autobiography_service` and `prompts` remain compatibility exports, not duplicate implementations. Cross-domain functions import dependencies at their call boundary to avoid circular initialization. Tests patch the implementation module when replacing a function.

Readiness thresholds live in `app/autobiography/policy.py` and are included in autobiography responses. Clients consume this policy instead of duplicating numeric constants.
