# 🎯 Problem Statement

> **Stage 1: Real Unknown** — Clearly define the pain point, gap, or opportunity before starting.

---

## 🔍 Core Problem / Pain Point

Joe Yoder’s Adaptive Object Model stores classes, attributes, relationships, and rules as **runtime metadata**. Historically that extra abstraction was expensive: custom interpreters, trapped databases, and one physical schema.

- **Current State:** AOM is well described (2001–2002) but rarely operated as a living system because metadata was hard to create, move, and project.
- **Ideal State:** Types are data; a small interpreter runs them; LLMs draft metadata; rclone moves files; graph / SQL / vectors / files are projections of one Type Square.
- **The Gap:** This repo must explain that shift and host it as a delivery-pilot project (7 stages, GitHub Pages, Key Vault `dp-kv-deliverypilot`).

## 👥 Target Audience & Stakeholders

- **Primary User:** Architects and agents working with runtime models, Second Brain stores, and multi-model data.
- **Secondary Stakeholders:** Readers of [adaptiveobjectmodel.com](https://adaptiveobjectmodel.com/), operators using rclone and Azure.

## 💡 Proposed Value Proposition

A public GitHub Pages explainer plus a 7-stage agent framework so AOM work is specced, tested, and deployable without freezing the domain in classes.

## 🚀 Constraints & Scope Boundaries

- Static frontend only on GitHub Pages (RULE-003). No Fly.io/Workers app in this pass.
- Do not create a new Key Vault — use `dp-kv-deliverypilot`.
- Default blobs: Azure project storage (RULE-004), not git LFS.
