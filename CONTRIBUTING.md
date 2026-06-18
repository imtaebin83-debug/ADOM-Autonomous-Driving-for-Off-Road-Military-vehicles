# Contribution Guide

## Branching

- Use short, topic-based branches such as `feature/segformer-baseline` or `experiment/tensorrt-fp16`.
- Keep commits focused on one meaningful change.

## Folder Rules

- Put learning notes and one-off checks in `study/<member>/`.
- Put reproducible experiments in `experiments/<experiment-name>/`.
- Move reusable training, inference, mapping, or integration code into `src/`.
- Keep large files out of git. Use `data/` and `models/` only for README files, metadata, and path conventions.

## Experiment Checklist

Each experiment should include:

- goal and hypothesis
- dataset version and split
- model/config used
- metrics to compare
- hardware/runtime environment
- result summary and known failure cases
- one row in `results/benchmark-results.csv` when it produces benchmark numbers

## Documentation

- Use `docs/meeting-notes/` for meeting logs.
- Use `docs/decision-records/` for decisions that affect repo structure, model choice, data policy, or deployment.
- Use `docs/system-architecture/` for diagrams and integration notes.
- Use `docs/setup-guides/` for reproducible setup instructions.

## Required Benchmark Metrics

For the first project phase, benchmark experiments should report:

- mIoU
- class IoU
- rare obstacle recall
- FPS
- latency p50/p95
- Jetson Orin NX power draw
- costmap update rate, if the experiment touches mapping
