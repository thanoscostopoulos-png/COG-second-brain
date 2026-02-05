# Morning Pages Reflections

## Directory Structure

```
morning-pages-reflections/
├── README.md (this file)
├── daily-reflections/
│   ├── frontend/          # User-facing daily reflections (2-min reads)
│   │   ├── 2026-01-28.md
│   │   ├── 2026-01-29.md
│   │   └── ...
│   └── backend/           # Analytical layer with full observations
│       ├── 2026-01-28.md
│       ├── 2026-01-29.md
│       └── ...
├── weekly-reflections/
│   ├── frontend/          # User-facing weekly reflections
│   └── backend/           # Analytical weekly reflections
└── monthly-reflections/
    ├── frontend/          # User-facing monthly reflections
    └── backend/           # Analytical monthly reflections
```

## File Naming Convention

- **Daily**: `YYYY-MM-DD.md` (e.g., `2026-02-05.md`)
- **Weekly**: `YYYY-week-NN.md` (e.g., `2026-week-05.md`)
- **Monthly**: `YYYY-MM.md` (e.g., `2026-02.md`)

## Two-Layer System

### Backend Reflections
- Expansive, unfiltered analysis
- All observations, hypotheses, pattern explorations
- Explains reasoning for what gets filtered to frontend
- No length constraints (as long as content is solid and grounded)
- More analytical, working through patterns with compassion

### Frontend Reflections
- Filtered, thoughtful presentation
- Short, readable within 2 minutes
- Direct, cutting through bias, with compassion
- Passes through filters defined in reflection-framework.md

## Versioning & Experiments

As the `reflection-framework.md` evolves, reflections will be regenerated to test new instructions. To track experiments:

### Version Tracking
Add to frontmatter:
```yaml
framework-version: v1.0
experiment: initial-baseline
regenerated: false
```

### When Regenerating
1. Keep old versions in `archive/` subdirectory
2. Update `framework-version` in new reflections
3. Note changes in `experiment` field
4. Mark `regenerated: true` and add `previous-version` reference

Example:
```
archive/
├── v1-initial/
│   ├── frontend/
│   └── backend/
└── v2-tone-adjustment/
    ├── frontend/
    └── backend/
```

## Current Status

**Framework Version**: v0.1 (in development)
**Latest Reflections**: 2026-01-28 through 2026-02-05
**Experiment**: Baseline reflections using initial framework

---

*This structure supports iterative refinement of the reflection framework while maintaining organized archives of experiments.*
