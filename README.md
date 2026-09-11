# 🧩 Adaptive Object Model (AOM)

> https://rifaterdemsahin.github.io/aom/

Joe Yoder’s Adaptive Object Model: **types as runtime metadata**, a small interpreter as code. This repo hosts the explainer on GitHub Pages and runs the delivery-pilot 7-stage agent framework.

## Live links

- 🌐 Live site: [https://rifaterdemsahin.github.io/aom/](https://rifaterdemsahin.github.io/aom/)
- 🧩 Explainer (original long page): [https://rifaterdemsahin.github.io/aom/5_Symbols/aom_explainer.html](https://rifaterdemsahin.github.io/aom/5_Symbols/aom_explainer.html)
- 📘 Live README.md: [https://rifaterdemsahin.github.io/aom/README.md](https://rifaterdemsahin.github.io/aom/README.md)
- 🐙 GitHub: [rifaterdemsahin/aom](https://github.com/rifaterdemsahin/aom)
- 📄 README on GitHub: [blob/main/README.md](https://github.com/rifaterdemsahin/aom/blob/main/README.md)

## Idea

The object model the user cares about is data. The coded object model is an interpreter (Yoder & Johnson, 2002). Type Square: `EntityType` / `Entity` / `PropertyType` / `Property`.

What changed: LLMs draft metadata; rclone moves files; graph, SQL, vectors, and files can all be projections of one Type Square. Friction of extra-abstract runtime models dropped.

## Delivery pilot

Forked structure from [delivery-pilot-template](https://github.com/rifaterdemsahin/delivery-pilot-template). Static frontend on GitHub Pages (RULE-003). Secrets in existing Key Vault **`dp-kv-deliverypilot`** (`/vaults/dp-kv-deliverypilot/secrets`) — do not create a new vault. Default blobs: Azure project storage (RULE-004).

| Stage | Folder | This project |
|-------|--------|----------------|
| 1 | `1_Real_Unknown` | Problem, OKRs, AOM hypotheses |
| 2 | `2_Environment` | Pages + Key Vault + architecture |
| 3 | `3_Simulation` | Carousel of Type Square images |
| 4 | `4_Formula` | SPEC-014, ADRs, thinking log |
| 5 | `5_Symbols` | Site, renderer, toolbox, images |
| 7 | `7_Testing_Known` | Smoke tests |
| 6 | `6_Semblance` | Errors, fixes, smoke report |

Read `agents.md` and `5_Symbols/rules/agent_operating_rules.md` (RULE-001–005).

## Sources

- [adaptiveobjectmodel.com](https://adaptiveobjectmodel.com/)
- [Architecture of AOMs (WICSA 2002)](https://adaptiveobjectmodel.com/WICSA3/ArchitectureOfAOMsWICSA3.htm)
- [rclone](https://rclone.org/)

## Links

- **GitHub Pages:** [https://rifaterdemsahin.github.io/aom/](https://rifaterdemsahin.github.io/aom/)
- **LinkedIn:** [rifaterdemsahin](https://www.linkedin.com/in/rifaterdemsahin/)
- **YouTube:** [@RifatErdemSahin](https://www.youtube.com/@RifatErdemSahin)
