# Benchmark Protocol

## Scope

1차 benchmark는 semantic segmentation model을 같은 dataset split, 같은 evaluation script, 같은 runtime 조건에서 비교하는 것을 목표로 한다.

## Target Hardware

- Primary edge target: NVIDIA Jetson Orin NX
- Training/server GPU는 별도로 기록하되, edge runtime 수치는 Orin NX 결과를 우선한다.

## Required Metrics

| Category | Metric | Unit | Notes |
| --- | --- | --- | --- |
| Segmentation | mIoU | percent | 전체 class 평균 IoU |
| Segmentation | class IoU | percent | class별 IoU, 특히 obstacle/traversability 관련 class 확인 |
| Segmentation | rare obstacle recall | percent | 구덩이, 진흙, 암석 등 희소 위험 class 기준 |
| Runtime | FPS | frames/sec | batch size 1 기준 |
| Runtime | latency p50 | ms | median end-to-end inference latency |
| Runtime | latency p95 | ms | tail latency 확인용 |
| Edge | power draw | W | Jetson Orin NX에서 측정 |
| Mapping | costmap update rate | Hz | segmentation output을 costmap으로 변환하는 실험부터 필수 |

## Reporting Rule

각 benchmark run은 다음 두 곳에 기록한다.

1. 실험별 Markdown 요약: `experiments/<track>/README.md` 또는 별도 run note
2. 통합 CSV 로그: `results/benchmark-results.csv`

## Minimum Run Metadata

- date
- git commit
- experiment id
- model
- dataset
- split
- input resolution
- precision: FP32, FP16, INT8
- hardware
- software stack
- measurement command
- known caveats

## Initial Comparison Set

- CNN speed baseline: YOLOv8-Seg or equivalent
- CNN precision baseline: DeepLabV3+
- Transformer baseline: SegFormer-B0 and/or SegFormer-B2
