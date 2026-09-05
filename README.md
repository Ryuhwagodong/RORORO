# RORORO

> TouchDesigner로 만드는 3인 미디어 아트 프로젝트의 협업 공간

현재 이 저장소에는 기존 작품 파일이 포함되어 있지 않습니다. 팀 협업 규칙과 새 작업을 시작하기 위한 빈 템플릿만 관리합니다.

## 작업 원칙

- 같은 `.toe` 파일은 동시에 한 명만 편집합니다.
- 기능은 가능한 한 `.tox`, Python, GLSL 파일로 분리합니다.
- 모든 작업은 개인 브랜치에서 진행하고 Pull Request로 합칩니다.
- `main`에는 전시 또는 공연에서 실행 가능한 상태만 유지합니다.
- 대용량 TouchDesigner·미디어 파일은 Git LFS를 사용합니다.

## 팀 작업 흐름

1. GitHub Issue에서 작업과 담당 파일을 선언합니다.
2. `feature/이름-작업` 브랜치를 만듭니다.
3. 작은 단위로 저장하고 커밋합니다.
4. Pull Request를 만들고 팀원 1명의 검토를 받습니다.
5. 실행 테스트 후 `main`에 병합합니다.

## 저장소 구성

- `COLLABORATION.md` — 역할, 브랜치, 충돌 대응 및 공연 릴리스 규칙
- `team-template/` — 새 작품을 시작할 때 복사하는 빈 작업공간
- `.github/ISSUE_TEMPLATE/` — 작업 담당 파일을 선언하는 Issue 양식
- `.github/pull_request_template.md` — 실행 환경과 검수 항목

## 시작하기

세 팀원 모두 Git과 [Git LFS](https://git-lfs.com/)를 설치하고 동일한 TouchDesigner 버전을 사용합니다. 자세한 과정은 `COLLABORATION.md`를 확인하세요.

---

**중요:** 현재 각자의 컴퓨터에 있는 작품은 자동으로 업로드되지 않습니다. 팀이 공유하기로 합의한 파일만 명시적으로 추가합니다.
