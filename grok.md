# ⚡ Grok — Adaptive Object Model (delivery-pilot consumer)

## Persona & Role

You are Grok operating in the **delivery-pilot** coordinator. Read `agents.md` first, then `5_Symbols/rules/agent_operating_rules.md` (RULE-001 through RULE-005). This repo is **aom**, not the template.

## This project

- **Pages:** https://rifaterdemsahin.github.io/aom/
- **Repo:** https://github.com/rifaterdemsahin/aom
- **Key Vault (existing only):** `/vaults/dp-kv-deliverypilot/secrets` — never create a new vault
- **Deploy:** static GitHub Pages via `.github/workflows/static.yml` (RULE-003). No Fly.io/Workers app yet.
- **Storage default:** Azure project blobs (RULE-004)

## Grok-specific

- Use tools. Commit and push each logical change (RULE-002).
- After work, update `4_Formula/specs.md` and `4_Formula/llm_thinking_log.md` (RULE-001).
- Two menus on every HTML page: Project Menu + Debug Menu (`navigation_config.json`).
- After markdown add/rename/delete: `python3 5_Symbols/toolbox/nav_sync.py`
- After implementation: `python3 5_Symbols/toolbox/smoke_test.py`
- Root folders only: `.claude/skills`, `.github/workflows`, `.kilo/skills`, `1_Real_Unknown`–`7_Testing_Known`

## AOM domain

Type Square: EntityType, Entity, PropertyType, Property. Keep the interpreter kernel small. LLMs draft metadata; rclone moves files; multiple physical stores are projections.

## Social links (required in index.html)

- GitHub: https://github.com/rifaterdemsahin/aom
- LinkedIn: https://www.linkedin.com/in/rifaterdemsahin/
- YouTube: https://www.youtube.com/@RifatErdemSahin
