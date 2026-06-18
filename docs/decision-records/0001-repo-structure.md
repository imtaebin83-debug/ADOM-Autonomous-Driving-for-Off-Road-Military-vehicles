# 0001. Initial Repository Structure

## Status

Accepted

## Context

ADOM은 오프로드 semantic segmentation 연구, 모델 경량화, Jetson 온보드 배포, ROS2 기반 perception-control 통합을 모두 포함한다. 따라서 학습용 코드, 실험용 코드, 실제 시스템 코드가 한 레포 안에서 섞일 위험이 크다.

## Decision

- `study/`는 팀원별 학습 노트, 논문 요약, 작은 테스트만 보관한다.
- 외부 오픈소스 전체 코드는 기본적으로 main repo에 복사하지 않는다.
- 외부 코드를 수정해야 하면 개인 fork를 쓰고, 프로젝트 빌드에 직접 필요해질 때만 `external/`에 submodule 또는 명확한 설치 안내로 연결한다.
- `experiments/`는 재현 가능한 연구 단위로 관리한다.
- 여러 실험에서 공유되는 학습, 평가, 추론, mapping 로직은 `src/`로 승격한다.
- ROS2 코드는 같은 repo 안의 `ros2_ws/`에서 관리한다.
- 대용량 데이터셋, checkpoint, TensorRT engine, ROS bag은 git에 커밋하지 않는다.

## Rationale

현재 단계에서는 팀원이 각자 빠르게 학습하고 실험해야 한다. 동시에 레포가 무거워지거나 실험 코드가 실제 시스템 코드처럼 굳어지는 것을 막아야 한다. `study`, `experiments`, `src`의 역할을 분리하면 빠른 탐색과 장기 유지보수를 함께 가져갈 수 있다.

## Consequences

- 팀원별 공부 기록은 한곳에서 볼 수 있어 onboarding이 쉬워진다.
- 외부 오픈소스 수정 이력은 fork/submodule에서 추적되므로 license와 upstream 업데이트 관리가 명확해진다.
- 실험 코드가 충분히 검증되기 전까지 `src/`를 가볍게 유지할 수 있다.

## Open Questions

1. RELLIS-3D, STONE, 자체 수집 데이터의 저장 위치와 접근 권한은 어떻게 관리할 것인가?
2. 군사/연구 보안상 공개 repo에 올리면 안 되는 자료의 기준은 무엇인가?

## Follow-Up Decisions

- 1차 목표, 타깃 하드웨어, metric, 실험 추적 방식은 [0002. Initial Benchmark Scope](0002-initial-benchmark-scope.md)에서 결정한다.
