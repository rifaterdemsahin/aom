# 🧪 Hypotheses

> **Stage 1: Real Unknown** — Assumptions to validate.

---

## H1 — Metadata creation is the old bottleneck

If LLMs draft EntityTypes, PropertyTypes, and Rule Objects, AOM becomes cheap to start. **Validate:** time to add a type in the explainer vs a class hierarchy.

## H2 — Motion of the model was the missing 2002 piece

If types are files, rclone can copy them across Drive, Azure Files, and S3 without a custom metadata bus. **Validate:** document rclone as transport; do not bake rclone credentials into git.

## H3 — One conceptual Type Square, many physical stores

Files, SQL, graph, and vectors can be projections of the same runtime model. **Validate:** architecture.md maps each store to an AOM pattern.

## H4 — Delivery-pilot structure reduces agent drift

If specs, thinking log, and smoke tests gate Pages, refactors stay recoverable when the operator LLM changes. **Validate:** SPEC-014 + smoke_test.py.
