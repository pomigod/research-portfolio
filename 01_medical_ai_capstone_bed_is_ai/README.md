# Bed is AI (`침대는 AI다`) — Multimodal Patient Posture & Pressure-Ulcer Prevention

Course project for **AI Capstone Design I (`AI 캡스톤디자인 I`)**, Department of Artificial Intelligence, Konyang University (`건양대학교 인공지능학과`).
Team **Bed is AI**: Minsoo Kang, Junhyuk Kang, Geunhyuk Jang, Jin Hwang.

## Problem & Architecture

Bedridden patients under blankets suffer severe keypoint occlusion in overhead RGB streams, degrading standard human pose estimation and delaying pressure-ulcer (`욕창`) risk alerts.

- **Vision Branch**: Overhead RGB capture + pseudo-depth preprocessing (`grayscale` + `3x3 emboss kernel` + unsharp masking) + fine-tuned `YOLO26s-Pose` (14 anatomical keypoints) + 4-layer **Graph Convolutional Network (`GCN`)** skeletal topology refinement (`best_gcn.pt`).
- **Tactile Branch**: Arduino pressure sensor matrix generating real-time 2D load heatmaps and peak-pressure alerts.
- **Multimodal Fusion**: Cross-checks predicted joint coordinates against localized bed-pressure peaks to discard hallucinated blanket-wrinkle poses and compute sustained pressure risk.

## Quantitative Results (`SLP` Benchmark, Week 5 Report)

| Pipeline | Speed (FPS) | PCKh@0.5 | mAP@0.50 | MPJPE (lower is better) |
| :--- | :---: | :---: | :---: | :---: |
| `YOLO26s-Pose` (Baseline) | `52.517` | `0.487` | `0.340` | `0.210` |
| `YOLO26s-Pose + GCN` (`best_gcn.pt`) | `49.310` | **`0.518`** | `0.340` | **`0.191`** |

- **`best_gcn.pt` Checkpoint Metadata**: `epoch = 77`, best `val_loss = 0.08098`, `config = {in_dim: 3, hidden_dim: 64, num_layers: 4, dropout: 0.1, out_dim: 2}`.
- Cross-domain generalization checks also documented on `OCHuman` (`5,081` images) and `COCO-Pose` (`163,957` raw / `12,700` toy subset).

## Repository Contents

| File | Description |
| :--- | :--- |
| [week3_presentation.pdf](./week3_presentation.pdf) | Week 3 Capstone concept & literature slide deck (`[AI캡스톤디자인1] 3주차 PPT_침대는 AI다.pdf`) |
| [week3_team_report.pdf](./week3_team_report.pdf) | Week 3 formal team report detailing web dashboard & miniature bed prototype |
| [week4_eda_preprocessing_report.pdf](./week4_eda_preprocessing_report.pdf) | Week 4 report: SLP dataset EDA (`58,347` raw -> `9,470` clean pose frames), split strategy, and baseline occlusion failure analysis |
| [week5_yolo_gcn_report.pdf](./week5_yolo_gcn_report.pdf) | Week 5 report: 4-layer GCN kinematic refinement, pseudo-depth preprocessing, and quantitative ablation |
| [best_gcn.pt](./best_gcn.pt) | Trained PyTorch 4-layer GCN checkpoint (`epoch 77`, `val_loss 0.08098`) |
| [architecture_diagram_dark.png](./architecture_diagram_dark.png) | Dark-mode end-to-end multimodal architecture diagram |
| [linear_multimodal_pipeline.png](./linear_multimodal_pipeline.png) | Illustrated horizontal RGB + Arduino pressure fusion workflow |
| [multimodal_pressure_ulcer_architecture.png](./multimodal_pressure_ulcer_architecture.png) | English block diagram of Pose Estimation + Pressure Sensing risk pipeline |

## References Cited

- Liu et al., *Simultaneously-Collected Multimodal Lying Pose Dataset: Enabling In-Bed Human Pose Monitoring*, IEEE TPAMI (SLP Dataset, 2022).
- Kipf & Welling, *Semi-Supervised Classification with Graph Convolutional Networks*, ICLR 2017 ([arXiv:1609.02907](https://arxiv.org/abs/1609.02907)).
- Eren & Taşar, *Transforming patient care: AI-powered sleep posture classification for pressure injury prevention*, Biomedical Signal Processing and Control (2026).
