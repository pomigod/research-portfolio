# Declarative AI Video Generation Pipelines (`정음 1446` & `Project IV`)

**Author**: Jin Hwang (`황진`), Department of Artificial Intelligence, Konyang University
**Video Showcase**: [`youtube.com/@extendedseamless`](https://www.youtube.com/@extendedseamless)
**Original Korean Titles**: `정음 1446 프로젝트 진행도 (2025-12-04)` & `프로젝트 IV: 선언형 3초 결정론 및 AI 영상 제작 파이프라인 (2026-11-30)`

## Core Methodology

Multi-clip generative video pipelines often suffer severe background drift and hallucination when daisy-chained via iterative `Extend` calls. Comparing a 2025 iterative production baseline (`Jeongeum 1446`) against 2026 dual-reference & standalone synthesis (`Project IV`) establishes three architectural principles:

1. **Dual-Reference Character Sheets (`3D Matte Character Blueprint`)**: Separating multi-pose 3D matte turnarounds from clean daylight scene photography prevents style bleed during image-to-video synthesis.
2. **Three-Second Determinism (`0-3s 결정 구간`)**: Quantitative pixel/background shift curves across `0–10 s` show that clips failing to transition within the first `3 s` exhibit `0%` recovery during `3–10 s` — motivating early 3-second 360p fast-fail filtering before 4K rendering.
3. **Standalone 4K Generation + Lossless FFmpeg Concatenation**: Synthesizing independent `10 s` shots (`Scene 0–5`) and stitching via lossless FFmpeg eliminates cumulative drift.

## Repository Contents

*(Raw `39.8 MB` `.pptx` decks and superseded draft `v0.04.drawio` omitted; crisp vector PDFs, empirical graphs, 5 exported PNGs, and 3 `.drawio` schemas are included.)*

| File | Description |
| :--- | :--- |
| [jeongeum1446_project_progress_19p.pdf](./jeongeum1446_project_progress_19p.pdf) | `2025-12-04` 19-slide original AI short film pipeline deck (`정음 1446`) |
| [project4_final_declarative_pipeline_v2.pdf](./project4_final_declarative_pipeline_v2.pdf) | `2026-11-30` 10-slide final pipeline evolution & comparative evaluation deck |
| [project4_end_to_end_workflow.png](./project4_end_to_end_workflow.png) | 7-stage end-to-end declarative production workflow diagram |
| [three_second_determinism_bg_shift_graph.png](./three_second_determinism_bg_shift_graph.png) | Empirical `0–10 s` background composition shift curves (`4 transitioning` vs `4 static`) |
| [drawio_pipelines/01_jeongeum1446_ai_film_pipeline_v0_06.drawio](./drawio_pipelines/01_jeongeum1446_ai_film_pipeline_v0_06.drawio) | Latest editable Draw.io XML schema (`v0.06`, supersedes `v0.04`) |
| [drawio_pipelines/01_jeongeum1446_ai_film_pipeline_v0_06.png](./drawio_pipelines/01_jeongeum1446_ai_film_pipeline_v0_06.png) | High-res (`5568x3514`) export of Jeongeum 1446 shot architecture |
| [drawio_pipelines/02_project4_public_service_video_pipeline.png](./drawio_pipelines/02_project4_public_service_video_pipeline.png) | Public-service AI video architecture diagram |
| [drawio_pipelines/03_project4_hwaseong_mascot_reskin_pipeline.png](./drawio_pipelines/03_project4_hwaseong_mascot_reskin_pipeline.png) | Mascot visual consistency & reskin pipeline diagram |
| [drawio_pipelines/04_5pole3spec_dual_reference_extend_chain.drawio](./drawio_pipelines/04_5pole3spec_dual_reference_extend_chain.drawio) | Editable `.drawio` schema for dual-reference extend chaining |
| [drawio_pipelines/04_5pole3spec_dual_reference_extend_chain.png](./drawio_pipelines/04_5pole3spec_dual_reference_extend_chain.png) | Rendered PNG (`3240x1890`) of dual-reference extend chain |
| [drawio_pipelines/05_pps_all4k_staged_production_diagram.drawio](./drawio_pipelines/05_pps_all4k_staged_production_diagram.drawio) | Editable `.drawio` schema for staged All-4K public media production |
| [drawio_pipelines/05_pps_all4k_staged_production_diagram.png](./drawio_pipelines/05_pps_all4k_staged_production_diagram.png) | Rendered PNG (`2781x6516`) of staged All-4K production workflow |
