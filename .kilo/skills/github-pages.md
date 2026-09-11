# GitHub Pages skill

Load when deploying or debugging the static AOM site.

## Rules
- Static frontend stays on GitHub Pages (RULE-003).
- Workflow: `.github/workflows/static.yml` (smoke gate then deploy).
- Pages source must be **GitHub Actions**, not branch `/`.
- Live URL: https://rifaterdemsahin.github.io/aom/
- After deploy: `python3 5_Symbols/toolbox/smoke_test.py --base-url https://rifaterdemsahin.github.io/aom/`
