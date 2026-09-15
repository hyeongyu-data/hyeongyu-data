# 최현규 · 지원 문서와 프로젝트 자료

데이터 엔지니어링·MLOps 지원 문서와 네 프로젝트의 소개·처리 흐름·운영 기록을 모았습니다.

## 지원 문서

- [이력서 PDF · 2쪽](resume.pdf) · [텍스트 원본](resume.md)
- [포트폴리오 PDF · 6쪽](portfolio.pdf) · [텍스트 원본](portfolio.md)

## 통합 프로젝트 자료

- [발표 PDF · 14쪽](projects.pdf)
- [편집 가능한 PPT · 14장](projects.pptx)
- [대시보드 HTML 다운로드](dashboard.html)
- [발표 원고](speaker-notes.md)
- [콘텐츠 데이터](projects.json)

GitHub의 파일 화면에서는 HTML이 실행되지 않습니다. 이 폴더를 내려받은 뒤 `dashboard.html`을 브라우저로 열면 프로젝트와 화면 유형을 선택할 수 있습니다. 외부 API에 연결하지 않는 발표용 화면입니다. HTML의 PDF·PPT 다운로드 링크를 사용하려면 같은 폴더의 파일을 함께 보관하세요.

## 프로젝트

| 프로젝트 | 담당 영역 | 저장소 |
|---|---|---|
| Auto Research | 5인 팀 인프라·배포·관측 | [Autoresearch-infra](https://github.com/SKYAHO/Autoresearch-infra) |
| 서울 기상 알림 | 개인 개발 · 수집·이벤트·저장·알림 | [air-quality-project](https://github.com/hyeongyu-data/air-quality-project) |
| Ecommerce ETL | 개인 개발 · 수집·품질·로컬 적재 | [ecommerce-etl-pipeline](https://github.com/hyeongyu-data/ecommerce-etl-pipeline) |
| Construction Risk Agent | 라우터·결과 합성·장비비 | [construction-risk-agent](https://github.com/hyeongyu-data/construction-risk-agent) |

## 검증 기준 · 2026-09-15

- 대기질: 최신 기본 브랜치에서 pytest 248개 통과, 커버리지 56.75%. 외부 API·실발송은 이번 검증에 포함하지 않았습니다. 별도 watcher의 발송 실패 후 쿨다운 문제는 운영 한계로 표시했습니다.
- ETL: pytest 91개 통과·1개 스킵(Airflow 미설치). 152행·중복 0건은 기존 Docker E2E 기록이며 현재 적재는 DuckDB입니다. BigQuery·실제 GA4 API·서비스 분석 대시보드는 후속 범위입니다.
- Auto Research의 규모 수치는 발표 당시의 가상 데이터 구성입니다. 건설 에이전트 화면의 비용·지연·신뢰도는 예시입니다.
- PDF의 텍스트·페이지 경계, PPT의 편집 가능한 도형, HTML의 필터와 외부 요청 유무를 검사했습니다. PPT 글꼴 대체 시 줄바꿈이 달라질 수 있으므로 고정 레이아웃은 PDF로 확인하세요.

이 자료는 프로젝트 전체 기능과 개인 담당 범위를 구분합니다. 학습·개발 환경의 검증을 상용 서비스 운영 성과로 표시하지 않습니다.
