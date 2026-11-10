# Research evidence maintenance

Preserve the published research cutoff of 14 July 2026, the five selected objects, and the source-to-claim mapping.

- `04_evidence/` contains the source cards and evidence ledger.
- `08_content/slide_evidence_map.csv` binds the presentation to 63 evidence mappings.
- `10_deck/manifold_world_model_landscape_v1_4.pptx` is the current presentation.
- Generation code lives in `../generation/`; presentation checks live in `10_deck/tools/`.
- Changes to substantive research claims require checking their cited primary sources.
- Run `../../scripts/audit/verify_repository.ps1` and rebuild `../../provenance/file_manifest.csv` after changing this evidence package.
