# Results

Markdown/CSV 기반 실험 추적 공간입니다.

초기에는 별도 experiment tracking 플랫폼을 쓰지 않고 다음 두 가지로 관리합니다.

- `benchmark-results.csv`: benchmark 숫자 한 줄 요약
- 실험별 Markdown: `experiments/<track>/README.md` 또는 별도 run note

대용량 output, checkpoint, rendered mask, TensorRT engine은 이 폴더에 커밋하지 않습니다.
