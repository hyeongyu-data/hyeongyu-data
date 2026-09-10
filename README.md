<h1 align="center">안녕하세요, 최현규입니다. 👋</h1>
<h3 align="center">이전에는 이커머스 플랫폼을 1인 개발·운영했으며, 현재는 데이터 엔지니어링과 MLOps를 중심으로 역량을 확장하고 있습니다.</h3>

<div align="center">
  <a href="mailto:hyeongyu.data@gmail.com"><img src="https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
</div>

---

## 🙋‍♂️ About Me

- ☁️ SK플래닛 생성형 AI 활용 데이터 엔지니어 과정 2기를 수료했습니다. 팀 프로젝트 Auto Research에서 클라우드 인프라와 배포·모니터링 환경을 담당했습니다.
- 💼 이커머스 플랫폼을 1인 개발·운영하며 결제·주문 연동과 사용자 행동 데이터 수집을 경험했습니다.
- 🔍 문제가 생기면 원인을 확인하고 해결 과정과 재발 방지 방법을 코드와 문서에 남깁니다.

---

## 🚀 Projects

### 1. Auto Research — 에이전트가 쓰는 ML 플랫폼 ⚙️

`Terraform` `GKE` `ArgoCD` `Prometheus/Grafana` `ELK` `GitHub Actions` `Google Secret Manager`

> 5인 팀 · 2026.06–08(8주 캡스톤) · SK플래닛 최종 프로젝트 · 담당: 인프라 전담
> 레포: [Autoresearch-infra](https://github.com/SKYAHO/Autoresearch-infra) · [Autoresearch](https://github.com/SKYAHO/Autoresearch) · [Autoresearch-airflow](https://github.com/SKYAHO/Autoresearch-airflow) *(팀 조직 저장소)*

가설을 제출하면 AI 에이전트가 Kubernetes에서 실험을 실행하고 리포트를 자동 생성하는 ML 라이프사이클 자동화 플랫폼.

- VPC부터 GKE·CI/CD까지 dev 인프라를 1주일 만에 0에서 구축하고 Terraform 초기 관리 리소스 25개를 적용한 뒤 `plan`의 `No changes`를 확인했습니다.
- 관측 스택 부재 문제를 8개 이슈로 분해해 1.5일 만에 Prometheus/Grafana·ELK를 배포·검증했습니다.
- Airflow 45시간 crash-loop를 오래된 `tfvars`의 NetworkPolicy 설정 불일치로 진단하고 유사 설정 사고 3건을 재발 방지 과제로 정리했습니다.
- 인프라 비용을 월 약 270달러 규모로 추적하고 OIDC 인증·Secret 관리·권한 경계를 운영 문서로 남겼습니다.

### 2. Ecommerce ETL — 이종 주문 데이터 수집·정제 📦

`Python` `Airflow` `pandas` `PyArrow` `Docker Compose`

> 개인 프로젝트 · 2026.09– 진행 중
> 레포: [ecommerce-etl-pipeline](https://github.com/hyeongyu-data/ecommerce-etl-pipeline)

이커머스 현장에서 결제·오픈마켓 주문 데이터를 대조하던 경험을 재현 가능한 ETL 파이프라인으로 구현하고 있습니다.

- 합성 PG 주문과 로컬 목업 오픈마켓 HTTP API를 수집하는 Airflow DAG 2개를 구현했습니다.
- 원천별 필드를 통합 스키마로 매핑하고 Parquet staging에 저장하며 데이터 품질을 검사합니다.
- GA4 이벤트 수집·BigQuery 적재·대시보드는 후속 작업으로 명시해 진행 상태를 구분했습니다.

### 3. Construction Risk Agent — 공사 리스크·추가비용 산정 에이전트 🏗️

`LangGraph` `FastAPI` `AWS Bedrock` `PostgreSQL` `Python`

> 5인 팀 · 2026.06 · 담당: 라우터·결과 합성·장비비 에이전트
> 레포: [construction-risk-agent](https://github.com/hyeongyu-data/construction-risk-agent)

기상·공정지연·자재리스크로 발생하는 추가공사비를 산정해 공무 담당자용 리포트를 생성하는 LangGraph 멀티에이전트.

- 플래너 기반 동적 라우팅과 `synthesize` 노드를 설계·구현했습니다.
- 장비명 정규화 → 규격 매칭 → 일대여료 조회 → 대기율·일수 반영의 장비 대기비 산정 로직을 구축했습니다.

### 4. Air Quality Project — 서울 기상 알림 파이프라인 🌤️

`Python` `Airflow` `Kafka` `OpenSearch` `Docker Compose`

> 개인 프로젝트 · 2026.04–08 · 로컬 Docker 재현
> 레포: [air-quality-project](https://github.com/hyeongyu-data/air-quality-project)

기상청·에어코리아 데이터를 수집해 Kafka·OpenSearch·알림 채널로 연결하는 이벤트 파이프라인입니다.

- 결측값을 0으로 대체하지 않고 `정보없음`으로 처리하며 DLQ·수동 커밋·멱등 event ID로 재처리를 안전하게 했습니다.
- 테스트 195개와 ruff·pip-audit·gitleaks·hadolint 기반 CI 검증을 구성하고 실데이터 알림 수신을 확인했습니다.
- 현재 구성은 로컬 검증용이며 인터넷 공개 운영용이 아닙니다.

---

## 🛠️ Tech Stack

**Infra & Cloud**

![Terraform](https://img.shields.io/badge/Terraform-844FBA?style=flat&logo=terraform&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![ArgoCD](https://img.shields.io/badge/Argo%20CD-EF7B4D?style=flat&logo=argo&logoColor=white)
![Google Cloud](https://img.shields.io/badge/Google%20Cloud-4285F4?style=flat&logo=googlecloud&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat&logo=grafana&logoColor=white)

**Languages & Data**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)

**AI / Agents**

![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat&logo=langgraph&logoColor=white)
![AWS](https://img.shields.io/badge/AWS%20Bedrock-232F3E?style=flat&logo=amazonaws&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Claude](https://img.shields.io/badge/Claude%20Code-D97757?style=flat&logo=anthropic&logoColor=white)

**Marketing & Analytics**

![Google Analytics](https://img.shields.io/badge/Google%20Analytics-E37400?style=flat&logo=googleanalytics&logoColor=white)
![Google Tag Manager](https://img.shields.io/badge/Google%20Tag%20Manager-246FDB?style=flat&logo=googletagmanager&logoColor=white)
![Mixpanel](https://img.shields.io/badge/Mixpanel-7856FF?style=flat&logo=mixpanel&logoColor=white)
