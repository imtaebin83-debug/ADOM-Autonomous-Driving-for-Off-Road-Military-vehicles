# Scripts

반복 작업 자동화 스크립트를 보관합니다.

예상 범위:

- dataset preparation
- training launch helpers
- evaluation and metric aggregation
- ONNX/TensorRT export
- Jetson benchmark helpers

스크립트가 특정 실험에만 쓰이면 먼저 `experiments/<name>/`에 두고, 여러 실험에서 재사용되면 이곳으로 옮깁니다.
