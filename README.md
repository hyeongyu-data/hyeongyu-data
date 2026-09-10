# 최현규 · 데이터 플랫폼 & MLOps

**주문·결제 데이터를 다루던 웹개발 경험에서, 데이터가 안정적으로 흐르는 플랫폼으로.**

이커머스 플랫폼을 1인 개발·운영했고, 5인 팀 ML 플랫폼 프로젝트에서 GCP·Kubernetes 인프라를 전담했습니다.
설정과 실제 실행 상태를 대조해 장애 원인을 찾고, 해결 과정을 코드와 운영 문서에 남깁니다.

SK플래닛 생성형AI 활용 데이터엔지니어 과정 2기를 수료했으며, 데이터 플랫폼·MLOps 엔지니어로 전환하고 있습니다.

[이메일](mailto:hyeongyu.data@gmail.com) · [인프라 프로젝트](https://github.com/SKYAHO/Autoresearch-infra) · [최근 작업](https://github.com/hyeongyu-data/ecommerce-etl-pipeline)

---

## 대표 프로젝트

### 01 · Auto Research — ML 실험 자동화 플랫폼

> 2026.06–08 · SK플래닛 교육과정 캡스톤 · 5인 팀 · **인프라 전담**

가설을 입력하면 AI 에이전트가 Kubernetes에서 실험을 실행하고 리포트를 생성하는 플랫폼입니다.
클라우드 인프라와 배포·관측 환경을 담당했습니다.

- **구축** — VPC·GKE·Cloud SQL·CI 인증을 Terraform으로 구성. 초기 관리 리소스 25개를 적용한 뒤 `plan`의 `No changes`를 확인했습니다.
- **관측** — 관측 공백을 8개 이슈로 나눠 1.5일 안에 Prometheus/Grafana·ELK 환경을 배포·검증했습니다.
- **장애 대응** — 45시간 지속된 Airflow crash-loop의 원인을 오래된 `tfvars`와 NetworkPolicy 설정 불일치로 진단했습니다.
- **운영 개선** — 누락된 Kubernetes Service Account를 IaC 관리에 편입하고, Claude Code 기반 PR 검증 절차를 설계했습니다.

`GCP` `Terraform` `Kubernetes` `ArgoCD` `Prometheus` `Grafana`

[인프라](https://github.com/SKYAHO/Autoresearch-infra) · [앱](https://github.com/SKYAHO/Autoresearch) · [Airflow](https://github.com/SKYAHO/Autoresearch-airflow)

### 02 · Ecommerce ETL — 이종 주문 데이터 수집·정제

> 2026.09– · **개인 프로젝트 · 진행 중**

서로 다른 결제·오픈마켓 주문 데이터를 대조하던 실무 경험을 Airflow 파이프라인으로 구현하고 있습니다.

- **구현** — 합성 PG 주문과 로컬 목업 오픈마켓 HTTP API를 수집하는 DAG 2개.
- **데이터 품질** — 원천별 필드를 통합 스키마로 매핑하고 Parquet staging에 저장하며 품질을 검사합니다.
- **후속 계획** — GA4 이벤트 수집, BigQuery 적재, 대시보드 구현.

`Python` `Airflow` `pandas` `PyArrow` `Docker Compose`

[코드와 로컬 실행 방법 →](https://github.com/hyeongyu-data/ecommerce-etl-pipeline)

### 03 · Construction Risk Agent — 건설 리스크·추가공사비 산정

> 2026.06 · 5인 팀 · **라우터·결과 합성·장비비 에이전트 담당**

질문에 필요한 비용 분석 노드를 조합해 공사 리스크 리포트를 만드는 LangGraph 시스템입니다.

- **실행 흐름** — 플래너 기반 동적 라우팅과 `synthesize` 결과 합성 노드를 설계·구현했습니다.
- **장비비 계산** — 장비명 정규화 → 규격 매칭 → 일대여료 조회 → 대기비 산정 로직을 구축했습니다.

`Python` `LangGraph` `AWS Bedrock` `PostgreSQL`

[프로젝트와 담당 영역 →](https://github.com/hyeongyu-data/construction-risk-agent)

### 04 · Air Quality Project — 서울 기상 알림 파이프라인

> 2026.04–08 · 개인 프로젝트 · 로컬 Docker 재현

기상청·에어코리아 데이터를 수집해 Kafka로 전달하고, 규칙 기반 판정 결과를 OpenSearch와 알림 채널에 기록·발송하는 이벤트 파이프라인입니다.

- **운영 신뢰성** — 결측값을 0으로 대체하지 않고 `정보없음`으로 처리하며, DLQ·수동 커밋·멱등 event ID로 재처리를 안전하게 했습니다.
- **검증 결과** — 테스트 195개, CI에 ruff·pip-audit·gitleaks·hadolint를 포함하고 실데이터 알림 수신을 확인했습니다.
- **관측·보안** — 처리 메트릭·하트비트·구조화 로그와 운영 보안 프로필을 구성했습니다. 현재 구성은 로컬 검증용이며 인터넷 공개 운영용이 아닙니다.

`Python` `Airflow` `Kafka` `OpenSearch` `Docker Compose`

[코드와 운영 기록 →](https://github.com/hyeongyu-data/air-quality-project)

---

## 기술과 경험

| 분야 | 직접 사용한 기술과 경험 |
| --- | --- |
| 인프라·배포 | GCP, Terraform, GKE/Kubernetes, Docker, Helm, ArgoCD, GitHub Actions |
| 관측·운영 | Prometheus, Grafana, ELK, Airflow 실행 환경과 장애 대응 |
| 데이터·개발 | Python, SQL, MySQL, PostgreSQL, Airflow DAG, LangGraph |
| 이전 실무 | PHP·JavaScript 기반 커머스 개발, 결제·오픈마켓 API 연동, GA4/GTM 이벤트 수집 |

<details>
<summary>이커머스 경험과 일하는 방식</summary>

- 그누보드5/영카트5 기반 헬스·뷰티 커머스를 1인 개발·운영하며 15개 이상 브랜드로 확장했습니다.
- 결제 4종과 네이버·쿠팡 주문 데이터를 통합 조회하는 관리자와 정산 업무 지원 기능을 개발했습니다.
- 장애 해결 후 같은 원인의 재발 가능성을 확인하고, 설정·권한·배포 절차와 문서를 함께 수정합니다.
- AI가 작성한 변경도 근거와 검증 결과를 확인하며, 실제 담당 범위와 팀 전체 성과를 구분해 기록합니다.

</details>

**함께 만든 도구** · [repo-walk](https://github.com/hyeongyu-data/repo-walk) — 저장소의 커밋·이슈·PR 이력을 단계별로 설명하고 중요한 변경을 리포트로 정리하는 개발 도구.
