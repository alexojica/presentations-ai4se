# Thesis Progress Deck

Offline HTML presentation for the thesis progress review.

## Open Locally

From the repository root:

```bash
python3 -m http.server 8008 --directory docs/presentations/greenlight-review
```

Then open:

```text
http://127.0.0.1:8008/
```

Speaker notes:

```text
press s
```

PDF export:

```text
http://127.0.0.1:8008/?print-pdf
```

Use the browser print dialog and save as PDF.

## Contents

- `index.html`: reveal.js deck with speaker notes.
- `theme.css`: custom thesis progress-review styling.
- `build_plots.py`: regenerates the data-driven figures used in the deck.
- `assets/`: local copies of plots used in the deck.
- `vendor/reveal.js/`: local reveal.js distribution and plugins for offline use.

## Source Material

The visual template is a self-contained custom reveal.js theme in `theme.css`. It uses a dark technical grid, versioned-API color accents, and local plot assets; it no longer layers an external reveal theme on top of the custom styling.

The deck synthesizes:

- `main.pdf`
- `docs/research/2026-05-26-thesis-research-question-framing.md`
- `docs/research/2026-05-26-thesis-methodology-chapter-framing.md`
- `docs/kb/concepts/single-api-knowledge-injection.md`
- `docs/kb/concepts/version-aware-api-benchmark.md`
- `docs/kb/concepts/api-version-hallucination-target.md`
- `docs/research/2026-04-17-why-overlap-v2-barely-moved-the-benchmark.md`
- `docs/research/2026-05-05-eval-benchmark-t1l2-qwen-fim-sweep-analysis.md`
- `docs/research/2026-05-22-api-knowledge-injection-synthesis.md`
- `docs/research/2026-05-22-chat-sft-api-knowledge-injection-literature.md`
- `docs/research/2026-05-22-chat-sft-sweeps-summary.md`
- `docs/research/2026-05-24-api-knowledge-localization-gradient-isolation.md`
- `docs/research/2026-05-24-staged-anchor-target-chat-sft-results.md`

Result curation rules for this deck:

- Training runs that exposed API documentation or signature blocks to the model
  are treated as invalid for the current methodology question and are not
  plotted.
- Documentation-free code context is the default condition, so the slides use
  task-shape labels such as `Code-gap chat`, `Prefix + anchors`, and
  `Task-diverse chat` instead of naming that absence as a separate method.
- Plots explicitly mark whether they aggregate over all Torch version slices or
  report per-version trends.
