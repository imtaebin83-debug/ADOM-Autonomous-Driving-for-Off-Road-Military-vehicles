# Data

데이터셋 원본과 전처리 산출물은 git에 커밋하지 않습니다.

권장 로컬 구조:

```text
data/
├── raw/          # 원본 데이터셋
├── interim/      # 중간 전처리 결과
├── processed/    # 학습/평가에 바로 쓰는 데이터
└── external/     # 외부 공개 데이터셋 또는 symlink
```

데이터를 추가할 때는 이 파일이나 별도 메타데이터 문서에 다음 정보를 남깁니다.

- dataset name and source
- download/access date
- license or usage restriction
- class ontology
- train/validation/test split
- preprocessing command
