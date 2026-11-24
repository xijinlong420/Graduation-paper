# Academic Research Tools

A curated index of open-source tools for academic reading, literature discovery, evidence-grounded synthesis, and scholarly writing.

> This file is a resource catalogue, not a claim that the projects below have been installed or integrated into this repository. Review each upstream repository, dependencies, security posture, and license before vendoring or deploying code.

## Recommended starting points

| Project | Role | Upstream | License / integration note |
|---|---|---|---|
| PaperLab | Local-first research workspace: PDF reading, passage-linked notes, paper search, systematic-review screening, evidence cards, citation checks, BibTeX/RIS/APA export | https://github.com/khannoussi-malek/PaperLab | Apache-2.0; strongest all-in-one candidate. Review its Docker/model requirements and data-flow settings before use. |
| literature-review-skills | Agent-agnostic workflow for narrative, systematic, scoping, and umbrella reviews; human review gates and source-linked claims | https://github.com/Xuzhen-Li/literature-review-skills | Check the current repository license and platform instructions before installing or redistributing. |
| Beaver (Zotero) | Zotero-native research agent, library search, sentence-level citations, PDF annotations | https://github.com/jlegewie/beaver-zotero | AGPL-3.0; use as a separate Zotero extension, not copied into this repository without license review. |
| VibeScholar | MCP server for academic search, Semantic Scholar enrichment, PDF retrieval, citation graphs, and local corpus retrieval | https://github.com/kuff/vibescholar | MIT; optional MCP integration. Verify upstream search-source reliability and terms before production use. |
| PDF Scholar | Desktop/browser PDF reader, annotation, figure/table split view, document-grounded AI assistant | https://github.com/emilmsh/pdf-scholar | MIT; Windows is the reference build; macOS/Linux support status should be checked before adoption. |

## Suggested adoption order

1. **Start with PaperLab** for reading, evidence capture, systematic screening, and citation checking.
2. **Add literature-review-skills** as a workflow layer after checking its license and adapting its human approval gates.
3. **Connect VibeScholar through MCP** only if additional literature discovery and local-corpus retrieval are needed.
4. **Choose Beaver or PDF Scholar as an alternative reader**, rather than installing multiple overlapping PDF readers at once.

## Research integrity requirements

- Treat AI-generated summaries, screening suggestions, and evidence cards as drafts, not verified findings.
- Preserve exact source passages, page numbers, DOI, and bibliographic metadata for every material claim.
- Do not invent missing sample sizes, statistics, effect sizes, methods, or conclusions.
- Distinguish full-text evidence from abstract-only evidence.
- Keep inclusion/exclusion decisions and reasons under researcher control.
- Check retractions, corrections, preprints, and publication status.
- Verify every citation against the original paper before manuscript submission.

## Before integrating upstream code

For each candidate, record: upstream commit/tag, license and dependency licenses, last meaningful maintenance activity, supported operating systems, required API keys/models, network/data-sharing behavior, security review, tests, and rollback procedure.

Do not copy entire upstream repositories into this project until compatibility and license obligations have been reviewed.
