# Satellite-Driven Data Center Siting via Grid Suitability Index (`GSI`)

**Event**: 2026 AI Infrastructure & Sustainability Hackathon (`2026-01-16`)
**Team INFRA**: Doyun Kim (Chungnam National Univ.), Jaehun Jeong (Chungnam National Univ.), **Jin Hwang** (Konyang Univ.)
**Original Korean Title**: `위성 데이터 기반 데이터센터 최적 입지 선정 — 전력 인프라 부담을 최소화하는 GSI 기반 스크리닝 모델`

## Overview

Hyperscale AI data centers require continuous base-load power, yet grid telemetry is rarely public. This project constructs a **Grid Suitability Index (`GSI`)** pre-screening pipeline combining **Google Earth Engine (`ee` / `geemap`)** satellite and open geospatial layers with **`OSMnx`** road/infrastructure proximity modeling across South Korea (focusing on Haenam Opportunity Zones and Gangwon Province).

## Contents

| File | Description |
| :--- | :--- |
| [team_infra_datacenter_gsi_presentation.pdf](./team_infra_datacenter_gsi_presentation.pdf) | 21-slide final hackathon deck (`Team INFRA`, `2026-01-16`) detailing problem definition, spatial signals, and screening outputs |
| [korea_datacenter_gsi_gee.ipynb](./korea_datacenter_gsi_gee.ipynb) | Sanitized 3-cell Google Earth Engine + OSMnx GIS screening notebook (`YOUR_EARTH_ENGINE_PROJECT_ID` placeholder; HTML widget blobs stripped) |
| [regional_micro_siting_cluster_map.png](./regional_micro_siting_cluster_map.png) | Regional micro-siting cluster visualization comparing candidate opportunity corridors against existing industrial power hubs |

## Notebook Execution Note

In [korea_datacenter_gsi_gee.ipynb](./korea_datacenter_gsi_gee.ipynb), replace `YOUR_EARTH_ENGINE_PROJECT_ID` in `ee.Initialize(project=...)` with your own active Google Earth Engine Cloud project before running cells.

## Third-Party Literature Citation

The hackathon background methodology draws upon published spatial regression work (external PDF intentionally omitted from redistribution):

- Woojin Lee et al., *"Data Center Optimal Site Selection Using Geographically Weighted Regression and Machine Learning (지리 가중 회귀와 머신러닝을 활용한 데이터 센터 최적 입지 선정)"*, *Journal of Korean Institute of Communications and Information Sciences (J-KICS)*, Vol. 50, No. 06, June 2025. DOI: [`10.7840/kics.2025.50.6.847`](https://doi.org/10.7840/kics.2025.50.6.847).
