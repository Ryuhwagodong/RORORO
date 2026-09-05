# RORORO 협업 가이드

## 1. 세 사람의 권장 역할

역할은 고정 직책이 아니라 한 작업 주기 동안의 책임입니다.

| 역할 | 책임 |
|---|---|
| 통합 담당 | 메인 `.toe` 조립, Perform Mode와 최종 출력 확인 |
| 비주얼 담당 | GLSL, TOP/SOP 네트워크, 룩 개발 |
| 인터랙션 담당 | 센서·카메라·MediaPipe·Python 및 입력 안정화 |

각자 독립 파일에서 작업하고, 통합 담당이 검증된 기능을 메인 `.toe`에 순서대로 넣는 방식이 가장 안전합니다. 역할은 주 단위로 바꿔도 됩니다.

## 2. 작업 보드

동일한 바이너리 파일을 동시에 편집하지 않도록 작업을 시작할 때 아래 표를 갱신합니다. GitHub Issues/Projects를 쓰기 시작하면 이 표는 링크로 대체해도 됩니다.

| 상태 | 담당자 | 브랜치 | 대상 파일/기능 | 시작일 |
|---|---|---|---|---|
| 예시: 진행 중 | 이름 | `feature/name-camera` | `NEON_HAND_WEB.toe` 카메라 입력 | YYYY-MM-DD |

상태는 `예정`, `진행 중`, `검토 요청`, `완료` 중 하나를 사용합니다.

## 3. 브랜치와 커밋

- `main`: 공연/전시에 실행 가능한 상태만 유지합니다.
- `feature/이름-기능`: 새 기능이나 비주얼 작업입니다.
- `fix/이름-문제`: 오류 수정입니다.
- `experiment/이름-실험`: 버려도 되는 실험입니다.

커밋 메시지는 `feat:`, `fix:`, `art:`, `docs:`, `chore:` 중 하나로 시작합니다. 한 커밋에는 되돌릴 수 있는 한 가지 변경만 담습니다.

## 4. Pull Request 체크

- 수정한 `.toe`와 담당자가 작업 보드에 일치하는가?
- 사용한 TouchDesigner 버전이 팀 기준과 같은가?
- 프로젝트를 새로 열었을 때 Missing File/Operator 오류가 없는가?
- 외부 파일 경로가 상대경로인가?
- 최소 1분 이상 실행해 센서, 프레임률, 메모리 이상이 없는가?
- 해상도, FPS, 오디오 장치, 카메라 번호 등 실행 조건을 PR에 적었는가?
- UI가 바뀌었다면 미리보기 이미지나 짧은 영상을 첨부했는가?

## 5. 충돌이 났을 때

`.toe` 충돌을 텍스트처럼 직접 병합하지 않습니다. 두 버전의 백업 브랜치를 남기고, 팀에서 기준 버전을 정한 뒤 다른 버전의 변경을 TouchDesigner 안에서 수동으로 다시 적용합니다. 이 때문에 작은 단위로 자주 병합하는 것이 중요합니다.

Python, GLSL, Markdown처럼 텍스트인 파일은 일반적인 Git 충돌 해결이 가능합니다.

## 6. GitHub 저장소 최초 연결

한 사람이 GitHub에서 빈 저장소 `RORORO`를 만들되 README, `.gitignore`, 라이선스 자동 생성을 선택하지 않습니다. 그다음 이 폴더에서 아래 명령을 실행합니다.

```text
git lfs install
git add .
git commit -m "chore: initialize RORORO collaboration repository"
git branch -M main
git remote add origin <GitHub 저장소 주소>
git push -u origin main
```

GitHub 저장소 설정에서 다음을 권장합니다.

- 팀원 두 명을 Collaborator로 초대합니다.
- `main` 브랜치에 Pull Request 필수와 승인 1명 규칙을 켭니다.
- 강제 푸시는 금지합니다.
- 기능 단위로 GitHub Issue를 만들고 담당자를 지정합니다.

## 7. 공연 직전 릴리스

검증된 커밋에 `show-YYYY-MM-DD` 형식의 태그를 붙입니다. 공연 컴퓨터에는 해당 태그를 내려받고 네트워크가 없어도 모든 외부 파일이 열리는지 확인합니다. 공연 당일 수정은 별도 `hotfix/` 브랜치에서 한 뒤 검증 후 병합합니다.

