# Configs

학습, 평가, 배포 설정 파일을 두는 공간입니다.

권장 하위 구조:

```text
configs/
├── datasets/
├── models/
├── training/
├── evaluation/
└── deployment/
```

초기에는 실험별 설정을 `experiments/<name>/`에 두고, 여러 실험에서 공유되는 설정만 이곳으로 승격합니다.
