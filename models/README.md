# Models

체크포인트와 export 산출물의 로컬 배치 규칙을 기록합니다.

실제 모델 파일은 git에 커밋하지 않습니다.

권장 로컬 구조:

```text
models/
├── checkpoints/
├── exports/
│   ├── onnx/
│   └── tensorrt/
└── cards/
```

모델을 공유해야 할 때는 model card에 다음을 기록합니다.

- model architecture
- training dataset and split
- checkpoint source
- metrics
- export command
- known limitations
