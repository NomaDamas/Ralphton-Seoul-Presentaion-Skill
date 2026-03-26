---
name: ralphthon-seoul-mid-presentation-ko
description: 랄프톤 서울 중간발표 양식에 맞춘 slides-grab 기반 인터뷰형 워크플로우입니다. 사용자가 한국어 발표 덱을 원할 때, 필수 인터뷰를 먼저 진행하고 slide-outline.md를 만든 뒤 HTML 슬라이드를 생성·검증하고 viewer를 빌드한 다음 반드시 slides-grab editor까지 실행합니다.
metadata:
  short-description: 한국어 랄프톤 중간발표 slides-grab 워크플로우
---

# 랄프톤 서울 중간발표 (한국어)

사용자가 `slides-grab`으로 **랄프톤 서울 중간발표용 HTML 슬라이드**를 빠르게 만들고 싶을 때 이 스킬을 사용합니다.

## 목표
아래 흐름을 끝까지 수행합니다.
1. `slides-grab` 설치/사용 가능 여부 확인
2. 설치된 `$slides-grab` 스킬 호출
3. 필수 인터뷰 진행
4. `slide-outline.md` 도출
5. HTML 슬라이드 생성
6. 검증 및 viewer 빌드
7. **HTML 슬라이드 생성 후 반드시 editor 실행**

인터뷰를 생략하지 마세요. outline 작성 후에는 유저에게 평가를 요청하세요. HTML만 만들고 끝내지 마세요. HTML 슬라이드를 만든 뒤에는 반드시 `slides-grab edit --slides-dir <path>` 실행을 언급하고 실제로 실행하세요.

## 필수 설치 확인
인터뷰 전에 환경부터 확인합니다.

1. `slides-grab` 사용 가능 여부 확인:
   - `slides-grab --help`
   - 또는 `npm exec -- slides-grab --help`
2. 없으면 `references/slides-grab-setup.md` 기준으로 설치를 안내합니다.
3. Codex용 `slides-grab` 스킬이 없으면 공식 npm 패키지 기준으로 아래 설치를 안내하고 Codex 재시작을 요청합니다.
   - `npm install slides-grab`
   - `npx playwright install chromium`
   - `npx skills add ./node_modules/slides-grab -g -a codex --yes --copy`
4. CLI 사용 가능 상태가 된 뒤 인터뷰를 이어갑니다.
5. 설치가 끝나면 **반드시 설치된 `$slides-grab` 스킬을 호출**하고, 계획/HTML 생성/검증/viewer/editor 흐름은 그 instruction을 기준으로 진행합니다.

## 필수 인터뷰
outline 작성 전에 반드시 질문을 던지세요. 체크리스트는 `references/interview-checklist.md`를 따릅니다.

최소한 아래 항목은 확보하거나 확인해야 합니다.
- 프로젝트명
- 팀명 / 팀원 / GitHub URL
- 누구의 어떤 문제인지
- 그 문제가 얼마나 자주 발생하는지
- 얼마나 고통스러운지
- 개인 경험 또는 고객 사례 등 설득력 있는 사례
- 프로덕트를 한 문장으로 정의한 문장
- 보여줄 핵심 기능 또는 워크플로우
- 사용한 AI 에이전트 / 모델 / 툴
- 랄프를 지속하기 위해 사용한 운영 방식
- 현재 진행 상황 요약(옵션)

필수 항목이 비어 있으면 후속 질문을 하세요. 답을 지어내지 마세요.

## 기본 덱 구조
랄프톤 서울 중간발표 양식에 맞춰 기본적으로 아래 구조를 사용합니다.
1. 표지 — 프로젝트명, 팀, 팀원, GitHub
2. 문제 정의 — 누구의 문제인지, 어떤 문제인지, 빈도, 고통, 사례/증거
3. 솔루션 / 프로덕트 — 한 문장 정의 + 핵심 흐름
4. 나의 랄프 세팅 / 랄프 역량 — AI 에이전트, 워크플로우, 지속 전략
5. 현재 진행 상황 — 옵션, 내용이 있을 때만 포함

사용자 정보가 충분하면 문제/솔루션을 2장 이상으로 나눌 수 있지만, 발표 흐름은 짧고 강하게 유지하세요.

## 워크플로우
1. 필수 정보가 채워질 때까지 인터뷰합니다.
2. `slide-outline.md`를 작성합니다.
3. outline을 짧게 보여주고, 슬라이드 제작 전 사용자 승인을 받습니다.
4. **반드시 `$slides-grab`를 호출하고 그 설치된 instruction을 기준으로** 슬라이드 제작을 진행합니다.
5. 슬라이드 작업 경로는 `decks/<deck-name>/`를 사용합니다.
6. `slides-grab` 워크플로우 안에서 `slide-XX.html` 파일을 생성합니다.
7. `slides-grab validate --slides-dir <path>`를 실행합니다.
8. 검증이 통과할 때까지 HTML/CSS를 수정합니다.
9. `slides-grab build-viewer --slides-dir <path>`를 실행합니다.
10. viewer 위치를 사용자에게 알려줍니다.
11. **HTML 슬라이드가 준비되면 반드시 `slides-grab edit --slides-dir <path>`를 실행합니다.** 이 워크플로우에서는 editor 실행이 필수라고 명시하세요.

## 규칙
- 기본 진행 언어는 한국어입니다.
- `$slides-grab`를 우회하지 마세요. 이 스킬은 설치된 `slides-grab` 스킬 위에 랄프톤 중간발표 제약을 덧씌우는 래퍼입니다.
- 랄프톤 양식의 핵심 평가 포인트를 우선합니다: 문제의 매력도, 솔루션의 효과성, 랄프 역량.
- 추상적인 수식보다 구체적인 사용자 고통과 실제 워크플로우를 우선합니다.
- 슬라이드는 짧고 피치 중심으로 만듭니다.
- 이 스킬에서는 export까지 진행하지 않습니다. editor 실행 후 종료합니다.
- 이후 export가 필요하면 표준 `slides-grab-export` 워크플로우로 넘깁니다.

## 참고
- `references/interview-checklist.md`
- `references/slides-grab-setup.md`
