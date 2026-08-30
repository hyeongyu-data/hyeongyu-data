<h1 align="center">안녕하세요, 최현규입니다. 👋</h1>
<h3 align="center">이커머스 데이터 문제를 인프라로 풀어온 경험을 바탕으로, 데이터가 안정적으로 흐르는 플랫폼을 만드는 엔지니어를 지향합니다.</h3>

<div align="center">
  <a href="mailto:hyeongyu.data@gmail.com"><img src="https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://komarev.com/ghpvc/?username=hyeongyu-data&label=Profile%20views&color=0e75b6&style=for-the-badge" alt="hyeongyu-data" />
</div>

---

## 🙋‍♂️ About Me

- ☁️ **SK플래닛 생성형 AI 활용 데이터 엔지니어 과정 2기** 수료. 8주 팀 캡스톤(Auto Research)에서 5인 중
  인프라를 단독 전담했습니다.
- 💼 이전에는 헬스/뷰티 이커머스 플랫폼을 **3년간 1인 개발자로 설계~운영**하며 15개+ 브랜드로 확장,
  결제·오픈마켓 데이터를 통합하고 GA4·GTM 트래킹을 직접 구축한 경험이 데이터 엔지니어링 전환의 계기입니다.
- 🔍 겉으로 보이는 증상만 고치지 않고 **같은 유형의 문제가 왜 반복되는지 구조적으로 파고드는** 방식으로
  일합니다. AI 도구도 빠른 생성보다 **팀 검증 프로세스에 편입**시키는 데 집중합니다(Claude Code PR 리뷰
  게이트 직접 설계).

---

## 🚀 Projects

### 1. Auto Research — 에이전트가 쓰는 ML 플랫폼 ⚙️

`Terraform` `GKE` `ArgoCD` `Prometheus/Grafana` `ELK` `GitHub Actions` `Google Secret Manager`

> 5인 팀 · 2026.06–08(8주 캡스톤) · SK플래닛 최종 프로젝트 · 담당: 인프라 전담
> 레포: [Autoresearch-infra](https://github.com/SKYAHO/Autoresearch-infra) · [Autoresearch](https://github.com/SKYAHO/Autoresearch) · [Autoresearch-airflow](https://github.com/SKYAHO/Autoresearch-airflow) *(팀 조직 저장소)*

가설을 제출하면 AI 에이전트가 Kubernetes에서 실험을 실행하고 리포트를 자동 생성하는 ML 라이프사이클
자동화 플랫폼.

- VPC부터 GKE·CI/CD까지 dev 인프라를 **1주일 만에 0에서 구축**, Terraform 리소스 **25개 무결점 적용**
- 관측 스택 부재 문제를 3-에이전트 병렬 조사로 **8개 이슈로 분해 → 1.5일 만에 전량 배포·검증**
  (Grafana 대시보드 6장, ELK 구조화 로깅)
- Prometheus 실측으로 리소스 요청 대비 실사용률이 **11~48%**에 불과함을 발견해 데이터 기반 스케일링 기준 재설계
- Airflow **45시간 crash-loop** 장애를 "로컬 tfvars 설정 drift"로 근본 진단, 같은 유형 사고 3건을
  추가로 찾아 원인 클래스로 일반화·재발 방지책 설계
- 인프라 비용 실측·관리 — **월 $270**, Artifact Registry·CIDR `/20`·OIDC 인증 등 모든 결정에 트레이드오프 직접 판단
- Claude Code를 팀 PR 리뷰 게이트로 설계 — IAM·시크릿·배포 안전성 자동 점검 + "이해도 확인" 질문에
  근거 기반 답변을 요구하는 검증 구조

### 2. construction_risk_agent — 공사 리스크·추가비용 산정 에이전트 🏗️

`LangGraph` `Airflow` `FastAPI` `Python`

> 팀 프로젝트 · 2026.06

기상·공정지연·자재리스크로 발생하는 추가공사비를 산정해 공무 담당자용 리포트를 생성하는 LangGraph
멀티에이전트. 라우터/synthesize 로직과 few-shot 예시 세트를 설계하고, **조달청 자재단가 자동 갱신
Airflow DAG**를 신규 개발(수집 → 전처리 → DB 갱신, 매월 자동 실행).

### 3. 헬스/뷰티 이커머스 플랫폼 — 결제·마케팅 데이터 통합 🛒

`PHP` `MySQL` `GTM` `GA4` `Meta Pixel` `Mixpanel`

> 1인 개발 · 2023.10–2026.02(2년 5개월) · 담당: 설계·개발·배포·운영 전체
> 그누보드5/영카트5 오픈소스 기반, 15개+ 브랜드로 확장 *(비공개 저장소 — 이전 직장 코드)*

결제 4종(KCP·Payple·네이버페이·LG유플러스)·오픈마켓 2종(네이버·쿠팡)의 서로 다른 데이터를 통합하고,
GTM 기반 GA4·메타 픽셀·Mixpanel 풀퍼널 트래킹을 직접 설계·구축한 경험이 데이터 엔지니어 전환의 계기.

- 3년간 **859커밋**, 이종 결제·마켓플레이스 데이터를 통합 관리자로 집계하는 구조 설계
- 조회→장바구니→결제→구매→가입 풀퍼널을 GA4·메타 픽셀에 병행 연동, 결제수단별(PG/네이버페이) 이벤트 분리 설계
- 브랜드 3곳(재직 기간 2025년 기준) 합산 **구매 9.2만 건 · 매출 약 94억원**을 직접 구축한 트래킹으로 추적

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

**Marketing & Analytics**

![Google Analytics](https://img.shields.io/badge/Google%20Analytics-E37400?style=flat&logo=googleanalytics&logoColor=white)
![Google Tag Manager](https://img.shields.io/badge/Google%20Tag%20Manager-246FDB?style=flat&logo=googletagmanager&logoColor=white)
![Mixpanel](https://img.shields.io/badge/Mixpanel-7856FF?style=flat&logo=mixpanel&logoColor=white)

**AI Tools**

![Claude](https://img.shields.io/badge/Claude%20Code-D97757?style=flat&logo=anthropic&logoColor=white)

---

<p align="center"><img src="https://github-readme-stats.vercel.app/api?username=hyeongyu-data&show_icons=true&theme=default&hide_border=true" alt="hyeongyu-data github stats" /></p>
