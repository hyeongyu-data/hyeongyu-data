# 최현규
## 데이터 엔지니어링 · MLOps

[hyeongyu.data@gmail.com](mailto:hyeongyu.data@gmail.com) · [github.com/hyeongyu-data](https://github.com/hyeongyu-data)

이전에는 이커머스 플랫폼을 1인 개발·운영했으며, 현재는 데이터 엔지니어링과 MLOps를 중심으로 역량을 확장하고 있습니다. 5인 팀 프로젝트에서 클라우드 인프라와 배포·모니터링 환경을 전담했습니다. 문제가 생기면 원인을 확인하고 해결 과정과 재발 방지 방법을 코드와 문서에 남깁니다.

### 핵심 역량

- **인프라·배포** — GCP, Terraform, GKE/Kubernetes, Docker, Helm, ArgoCD, GitHub Actions, WIF
- **관측·운영** — Prometheus, Grafana, ELK, Airflow 실행 환경 구축 및 장애 대응
- **데이터·개발** — Python, SQL, pandas, PyArrow, PHP, MySQL, PostgreSQL, GA4/GTM

### 주요 프로젝트

#### Auto Research | ML 실험 자동화 플랫폼
**2026.06–08 · 8주 캡스톤 · 5인 팀 · 인프라 전담** · [저장소](https://github.com/SKYAHO/Autoresearch-infra)

- AI 에이전트가 Kubernetes에서 실험을 실행하고 리포트를 생성하는 플랫폼의 GCP 인프라·배포·관측 환경을 담당했습니다.
- VPC·GKE·Cloud SQL·Artifact Registry·CI 인증 기반을 **1주일 내 구축**했습니다. 초기 Terraform 관리 리소스 25개 적용 후 `plan`으로 코드와 배포 상태의 일치를 확인했습니다.
- 관측 공백을 **8개 이슈로 나눠 1.5일 내 배포·검증**했습니다. GKE·Airflow·MLflow·서빙의 메트릭과 로그를 확인할 수 있도록 Prometheus/Grafana·ELK를 구성했습니다.
- 45시간 지속된 Airflow crash-loop의 원인을 오래된 `tfvars`에서 비롯된 NetworkPolicy 설정 불일치로 진단했습니다. 재구축 시 누락된 Kubernetes Service Account는 Terraform 관리에 편입했습니다.
- Terraform apply 진입점을 2개에서 1개로 통합하고, 서비스 계정·WIF 권한 경계를 분리했습니다. IAM·시크릿·롤백을 점검하는 Claude Code PR 리뷰 절차를 구성했습니다.

#### Air Quality Project | 기상·대기질 알림 파이프라인
**2026.04–09 · 개인 프로젝트 · 로컬 Docker 검증** · [저장소](https://github.com/hyeongyu-data/air-quality-project)

- 기상청·에어코리아 데이터를 Airflow로 수집하고 Kafka → 소비자 → OpenSearch·알림 채널로 연결했습니다.
- 결측값을 `정보없음`으로 처리하고, event ID 기반 upsert·수동 커밋·DLQ를 적용했습니다. 알림 전송이 모두 실패하면 다음 처리에서 재시도할 수 있도록 중복 억제 상태를 관리했습니다.
- 회귀 테스트와 ruff·pip-audit·gitleaks·hadolint 검사를 CI에 구성했습니다. 실제 데이터 수집과 알림 수신을 로컬 환경에서 확인했습니다.

#### Ecommerce ETL | 이종 주문 데이터 수집·정제
**2026.09–진행 중 · 개인 프로젝트** · [저장소](https://github.com/hyeongyu-data/ecommerce-etl-pipeline)

- 합성 PG 주문·로컬 목업 오픈마켓 API·GA4 목업 보고서를 수집하는 Airflow DAG 3개를 구현했습니다.
- 원천별 데이터를 18개 컬럼의 통합 스키마로 변환하고 품질 검사 후 Parquet staging에 저장합니다. DuckDB 날짜별 통합 적재 DAG를 구현하고 기존 Docker E2E에서 152행·재실행 중복 0건을 확인했습니다.
- BigQuery 실연결·실제 GA4 API·분석 대시보드는 후속 범위입니다. 목업 데이터와 실제 외부 연동의 범위를 구분해 문서화했습니다.

<!-- pagebreak -->

# 최현규
## 경력 · 프로젝트 · 교육

### 경력

#### 오디너리퍼슨 · 휴먼이즈 | 웹개발자
**오디너리퍼슨 2024.03–2026.02 · 휴먼이즈 2023.10–2024.03**

동일 대표와 이어진 커머스 플랫폼 개발·운영 업무입니다. 휴먼이즈 사원, 오디너리퍼슨 초기 약 9개월 이사 이후 사원으로 근무했습니다.

- 그누보드5·영카트5 기반 헬스·뷰티 이커머스 플랫폼을 **1인 개발자로 설계·배포·운영하고 15개 이상 브랜드로 확장**했습니다.
- KCP·Payple·네이버페이·LG유플러스 결제와 네이버·쿠팡 주문을 통합 조회하는 관리자를 개발하고, 결제수단별 정산 화면과 대사 업무를 지원했습니다.
- 네이버 CheckoutAPI(SOAP/XML)·쿠팡 Open API로 주문·취소·상태 데이터를 수집·동기화하고 주문·배송·재고 리포트를 운영했습니다.
- GTM으로 GA4·Meta Pixel의 조회·장바구니·결제·구매 이벤트를 구성하고 결제수단별 구매 이벤트를 구분했습니다.

**기술** — PHP, MySQL, JavaScript, 외부 API, GA4, GTM

#### 필로소피 | 웹개발자 · 사원
**2022.10–2023.10**

- 자사몰·네이버·쿠팡의 주문 테이블을 기간별로 조회하는 통합 관리자 대시보드를 설계·개발했습니다.
- 채널별 수수료를 반영한 정산 계산과 15개 이상 유입 채널 분류·분석 기능을 구현했습니다.

#### 후즈 | 웹개발자 · 감사
**2021.07–2022.08** · 반려견 커머스 `waal`의 정기결제 서비스를 구축했습니다.

#### 위글로우 | 웹개발자 · 사원
**2021.02–2021.06** · 웹 서비스 기능 개발을 담당했습니다.

### 추가 프로젝트

#### Construction Risk Agent | 건설 리스크·추가공사비 산정
**2026.06 · 5인 팀 · 라우터·결과 합성·장비비 에이전트 담당** · [저장소](https://github.com/hyeongyu-data/construction-risk-agent)

- LangGraph의 고정 분기를 플래너 기반 동적 라우팅으로 바꾸고, 질문과 직전 대화 맥락에 따라 필요한 비용 노드만 호출하도록 구현했습니다.
- `synthesize` 노드와 답변 유형별 few-shot 예시로 여러 노드의 결과를 비용 리포트와 구조화된 응답으로 합성했습니다.
- 장비명 정규화 → 규격 매칭 → 일대여료 조회 → 대기율·일수 반영 로직과 DB 스키마·초기 데이터·테스트를 작성했습니다.

**기술** — Python, LangGraph, AWS Bedrock, PostgreSQL

### 교육·학력

- **SK플래닛 생성형 AI 활용 데이터 엔지니어 과정 2기 수료** · 2026.02.25–08.25
- **학점은행제 경영 전문학사** · 2021.04–2023.02 · 3.03/4.5
- 선문대학교 환경생명화학공학 · 2014.03–2018.06 · 1학년 수료 후 중퇴
