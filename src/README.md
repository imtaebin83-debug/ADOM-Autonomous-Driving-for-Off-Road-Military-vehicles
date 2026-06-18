# Source Code

실제 프로젝트 코드가 들어가는 공간입니다.

초기에는 다음 경계를 기준으로 패키지를 나눌 수 있습니다.

```text
src/
├── perception/    # segmentation model loading, inference, post-processing
├── mapping/       # semantic mask to traversability/costmap
├── planning/      # planner integration helpers
├── control/       # high-level steering/speed command interface
└── common/        # shared types, config loading, utilities
```

이 폴더는 ROS2와 독립적으로 재사용 가능한 공통 로직을 우선합니다. ROS2 node, launch file, message adapter는 mono repo 안의 `ros2_ws/`에 둡니다.

아직 Python package skeleton은 만들지 않았습니다. 첫 benchmark 코드의 import 경계가 보이면 `src/adom/` 또는 track별 package로 구체화합니다.
