# Repository Instructions

Start with `PROJECT.md` and `.doctrine/project.json` before changing this
repository. They define the project goal, lifecycle, boundaries, public
surfaces, delivery model, and adoption gaps.

Use `SylphxAI/doctrine` for enterprise standards. Keep the website
content-oriented: backend product APIs, auth, billing, customer data, and
runtime product behavior belong in their owning repositories, not this static
company website.

For control-plane-only changes, validate with:

```bash
python3 /Users/kyle/.doctrine/scripts/project-control-plane-audit.py --local . --fail-on-drift --json
git diff --check
```

For website changes, also run the relevant Bun, Vite, Biome, static preview,
and hosting readback checks.
