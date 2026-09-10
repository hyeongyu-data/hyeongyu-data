# 최현규입니다 👋

데이터가 만들어지는 현장과 운영되는 환경을 함께 이해하는 엔지니어입니다.

이커머스 플랫폼을 1인 개발자로 설계·운영하며 결제·주문·사용자 행동 데이터가 시스템마다 다르게 쌓이는 문제를 경험했습니다. 지금은 그 경험을 바탕으로 데이터 플랫폼과 MLOps를 공부하고, 수집부터 실행·관측까지 이어지는 흐름을 직접 만들고 있습니다.

제가 일할 때 가장 중요하게 보는 것은 **코드와 실제 실행 상태의 일치**입니다. 장애가 발생하면 증상만 없애지 않고 설정, 권한, 배포 절차에서 같은 문제가 반복될 지점을 찾아 문서와 코드에 함께 반영합니다.

SK플래닛 생성형AI 활용 데이터엔지니어 과정 2기를 수료했으며, 데이터 플랫폼·MLOps 엔지니어로 전환하고 있습니다.

[이메일](mailto:hyeongyu.data@gmail.com) · [이력서](https://github.com/hyeongyu-data/resume) · [최근 작업](https://github.com/hyeongyu-data/ecommerce-etl-pipeline)

![프로필 조회수](https://komarev.com/ghpvc/?username=hyeongyu-data&label=프로필%20조회수&color=0e75b6&style=flat)

## 지금 집중하는 것

- Python과 Airflow로 재현 가능한 데이터 수집·정제 파이프라인 만들기
- Kubernetes·Terraform·GitOps 환경에서 ML 실행을 안전하게 운영하기
- 데이터 품질, 관측성, 재처리와 보안을 설계 단계부터 검증하기
- AI 도구가 만든 변경을 근거와 테스트로 검토하는 개발 흐름 만들기

## 제가 해온 일

| 경험 | 한 줄 설명 |
| --- | --- |
| 이커머스 개발 | 15개 이상 브랜드의 커머스 플랫폼을 1인 개발·운영하고 결제·오픈마켓 데이터를 통합했습니다. |
| ML 플랫폼 인프라 | 5인 팀 프로젝트에서 GCP·Terraform·GKE·배포·관측 환경을 전담했습니다. |
| 데이터 파이프라인 | Airflow·Kafka·OpenSearch 기반 수집, 품질 검사, 알림 파이프라인을 구현했습니다. |

## 대표 작업

<details>
<summary><strong>Auto Research · ML 실험 자동화 플랫폼</strong></summary>

2026.06–08 · SK플래닛 교육과정 캡스톤 · 5인 팀 · 인프라 전담

가설을 입력하면 AI 에이전트가 Kubernetes에서 실험을 실행하고 리포트를 생성하는 플랫폼입니다.

- VPC·GKE·Cloud SQL·CI 인증을 Terraform으로 구성하고 초기 관리 리소스 25개를 적용했습니다.
- 관측 공백을 8개 이슈로 나눠 1.5일 안에 Prometheus/Grafana·ELK 환경을 배포·검증했습니다.
- 45시간 지속된 Airflow crash-loop를 오래된 `tfvars`와 NetworkPolicy 설정 불일치로 진단했습니다.
- 인프라 비용을 월 약 270달러 규모로 추적했고, Artifact Registry·CIDR `/20`·OIDC 인증 선택의 근거를 문서화했습니다.
- Claude Code를 IAM·시크릿·배포 안전성을 확인하는 PR 검증 절차에 편입했습니다.

[인프라](https://github.com/SKYAHO/Autoresearch-infra) · [앱](https://github.com/SKYAHO/Autoresearch) · [Airflow](https://github.com/SKYAHO/Autoresearch-airflow)

</details>

<details>
<summary><strong>Ecommerce ETL · 이종 주문 데이터 수집·정제</strong></summary>

2026.09– · 개인 프로젝트 · 진행 중

합성 PG 주문과 로컬 목업 오픈마켓 API를 Airflow DAG로 수집하고 통합 스키마와 Parquet staging으로 정제합니다. GA4 이벤트, BigQuery 적재, 대시보드를 후속 작업으로 진행합니다.

[저장소와 실행 방법](https://github.com/hyeongyu-data/ecommerce-etl-pipeline)

</details>

<details>
<summary><strong>Construction Risk Agent · 건설 리스크 분석 에이전트</strong></summary>

2026.06 · 5인 팀 · 라우터·결과 합성·장비비 에이전트 담당

플래너 기반 동적 라우팅, `synthesize` 결과 합성, 장비명 정규화부터 대기비 산정까지의 흐름을 LangGraph로 구현했습니다.

[프로젝트와 담당 영역](https://github.com/hyeongyu-data/construction-risk-agent)

</details>

<details>
<summary><strong>Air Quality Project · 서울 기상 알림 파이프라인</strong></summary>

2026.04–08 · 개인 프로젝트 · 로컬 Docker 재현

기상청·에어코리아 데이터를 Airflow로 수집하고 Kafka·OpenSearch·알림 채널로 연결했습니다. 결측값의 `정보없음` 처리, DLQ·멱등 event ID, 테스트 195개와 CI 보안 검사를 포함합니다. 현재 구성은 로컬 검증용입니다.

[코드와 운영 기록](https://github.com/hyeongyu-data/air-quality-project)

</details>

<details>
<summary><strong>이커머스 플랫폼 · 결제·마케팅 데이터 통합</strong></summary>

2023.10–2026.02 · 1인 개발·운영 · 비공개 직장 코드

그누보드5/영카트5 기반 헬스·뷰티 커머스를 15개 이상 브랜드로 확장했습니다. KCP·Payple·네이버페이·LG유플러스 결제 4종과 네이버·쿠팡 주문을 통합 조회·정산하고, GTM 기반 GA4·Meta Pixel 이벤트를 설계했습니다.

2025년 재직 기간 기준 3개 브랜드에서 구매 약 9.2만 건·구매 수익 약 94억 원이 추적되는 데이터 수집 체계를 운영했습니다. 이 수치는 매출 증대 성과가 아니라 구축한 트래킹으로 확인한 거래 규모입니다.

</details>

## 기술

`Python` `SQL` `Airflow` `Kafka` `GCP` `Terraform` `Kubernetes` `Docker` `Prometheus` `Grafana` `OpenSearch` `LangGraph`

함께 만든 도구: [repo-walk](https://github.com/hyeongyu-data/repo-walk) — 저장소의 커밋·이슈·PR 이력을 설명하고 중요한 변경을 리포트로 정리합니다.
