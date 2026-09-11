# 🏛️ Architecture Decision Records (ADRs)

> **Stage 4: Formula** — Documenting major architectural decisions, their context, and consequences.

---

## 📋 ADR Index

- **ADR 001:** Choice of Secrets Manager (Azure Key Vault `dp-kv-deliverypilot`)
- **ADR 002:** Reuse existing vault — do not create aom-kv
- **ADR 003:** Static frontend on GitHub Pages; no backend this pass

---

## 📌 ADR 001: Choice of Secrets Manager (Azure Key Vault)

### **Status:** Accepted
**Date:** 2026-09-11  
**Decided By:** Environment Agent / user rule

### **Context & Problem Statement**
*What is the context of this decision? What problem are we solving? (e.g. "We need a secure way to manage database credentials and API keys across environments without committing them to git.")*

### **Decision Drivers**
1. Zero secrets committed to version control.
2. Low cost for development operations.
3. Ease of integration with GitHub Actions and deployment platforms.

### **Considered Options**
- **Option 1:** Local `.env` files (Committed, high-risk).
- **Option 2:** Vault by HashiCorp (High configuration complexity, higher cost).
- **Option 3:** Azure Key Vault (FIPS compliance, pay-per-operation pricing).

### **Decision Outcome**
**Chosen Option:** **Option 3 (Azure Key Vault)**.
- **Why:** Fits enterprise-grade requirements, costs ~$0.03 per 10K requests (Standard tier), and interfaces natively with cloud pipelines.

### **Consequences**
- **Pros:** High security, audit logging, simple credential rotation.
- **Cons:** Requires active Azure credentials during CLI initialization and deployment pipelines.

---

## 📌 ADR 002: Reuse `dp-kv-deliverypilot`

### **Status:** Accepted
**Date:** 2026-09-11  
**Decided By:** User (refactor prompt)

### **Context & Problem Statement**
Consumer projects must not spawn a Key Vault per repo.

### **Decision Outcome**
Use `/vaults/dp-kv-deliverypilot/secrets` for Fly.io, Cloudflare Workers, Azure Storage, and APIs. Document names in `.env.example` only.

---

## 📌 ADR 003: GitHub Pages for the AOM explainer

### **Status:** Accepted
**Date:** 2026-09-11  
**Decided By:** Formula Agent (RULE-003)

### **Context & Problem Statement**
The site is HTML/CSS/JS with no server-side interpreter yet.

### **Decision Outcome**
Stay on GitHub Pages via `.github/workflows/static.yml`. Do not deploy Fly.io or Workers until an interpreter API exists. Metadata files may later live in Azure blobs (RULE-004).
