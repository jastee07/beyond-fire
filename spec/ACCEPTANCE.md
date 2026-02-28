# Acceptance Criteria — Beyond FIRE Calculators (frontend-only)

## Product decisions (locked)
- [ ] App is frontend-only (no server required for calculations, no DB, no auth)
- [ ] Deployed under a subdomain target: `calculators.jakesteele.com` (document deployment notes)
- [ ] All return assumptions are **real returns** (after inflation) by default; UI copy/tooltips reflect this
- [ ] Rental ROI calculator includes **IRR** (with guardrails when IRR is undefined)

## Deliverables (spec + build-ready plan)
- [ ] `docs/PRD.md` exists and reflects v1 scope (4 calculators + cross-cutting features)
- [ ] `docs/Calculators.md` defines for each calculator:
  - [ ] exact input fields + defaults
  - [ ] validation rules / ranges
  - [ ] exact outputs (definitions + formulas)
  - [ ] beginner-facing tooltips / copy notes
- [ ] `docs/URL-Schema.md` defines:
  - [ ] URL query param schema per calculator (names, types)
  - [ ] encoding/decoding rules (incl. versioning strategy)
  - [ ] example share links
- [ ] `docs/Math-Engine.md` defines:
  - [ ] a pure-function architecture (calculate(inputs) -> outputs)
  - [ ] FIRE timeline math approach + sensitivity approach
  - [ ] Rent vs buy net-worth simulation approach
  - [ ] House hack cashflow + occupancy breakeven approach
  - [ ] Rental IRR cashflow construction + numerical method (Newton/bisection) + failure modes
- [ ] `docs/Build-Plan.md` defines:
  - [ ] repo structure proposal (Next.js, calc/, components/, pages/routes)
  - [ ] milestones & sequencing for a weekend build
  - [ ] testing approach (unit tests for calc functions)

## Open questions resolved in-doc (choose and justify)
- [ ] IRR exit modeling decision is made and documented:
  - [ ] Use appreciation-based exit price (simple) **or**
  - [ ] Use exit cap rate valuation (real estate accurate)
  - [ ] (Optional) allow both via an Advanced toggle (spec it if chosen)
- [ ] “Learn” pages decision is made for v1 (include/exclude) and reflected in PRD

## Quality bar
- [ ] Spec is written so a dev can implement without further clarification
- [ ] No backend assumptions (everything computable client-side)
- [ ] Beginner-friendly defaults + explanation text included (no jargon-only fields)
