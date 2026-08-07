---
# the default layout is 'page'
title: 프로젝트
icon: fas fa-diagram-project
order: 1
---

개인 · 팀 프로젝트를 최신순으로 정리했습니다. 각 항목의 **자세히 보기**를 펼치면 기술적인 구현 내용을 확인할 수 있습니다.

## Tune Share Hub — 플레이리스트 공유 플랫폼

`2026.05` · 팀 프로젝트 (백엔드 단독 담당) · [GitHub](https://github.com/orgs/kosa-2026-1/repositories)

Spring Boot 기반 음악 플레이리스트 공유 서비스의 백엔드를 단독으로 개발했습니다. REST API 설계부터 Spring AI를 이용한 챗봇 기능 통합까지 진행했습니다.

**기술 스택:** `Spring Boot` `MyBatis` `MySQL` `Spring AI` `Bootstrap 5`

<details markdown="1">
<summary>자세히 보기</summary>

- 플레이리스트 CRUD, 트랙 관리, 댓글 · 좋아요 REST API 설계 및 구현
- 조회수 집계 및 인기 플레이리스트 랭킹 로직 구현
- MyBatis DAO 패턴 적용 (XML Mapper 기반 쿼리 분리), 커스텀 예외 처리 구조 설계
- JWT 인증 인터셉터(`AccessTokenCheckInterceptor`)로 인증 처리 일원화
- Spring AI 기반 챗봇 UI 통합 — `/ai/chat-model` 스트리밍 응답 처리, 프롬프트 엔지니어링(zero-shot / few-shot / CoT) 적용
- MyBatis resultMap 매핑 불일치 등 실제 쿼리 오류를 디버깅하며 원인 분석 및 해결

</details>

---

## 보험 보장 분석 데모

`2026.02` · 개인 프로젝트 · [GitHub](https://github.com/dlwldP/banksalad)

보험 지급 거절 통보서를 업로드하면 약관을 근거로 소명 가능성과 반박 논리를 자동으로 생성해주는 AI 프로토타입입니다. 문제 정의부터 기획, 개발까지 전 과정을 단독으로 진행했습니다.

**기술 스택:** `Next.js 16` `TypeScript` `Tailwind CSS` `Claude API`

<details markdown="1">
<summary>자세히 보기</summary>

**문제 정의**
보험 약관의 복잡성으로 인해 지급 거절 시 대부분의 고객이 소명을 포기하는 문제를, AI로 해결하고자 기획했습니다.

**주요 기능**
- PDF 드래그앤드롭 업로드 → 거절 통보서 자동 분석
- 보험사 · 진단명 · 청구 금액 · 거절 사유를 카드 형태로 시각화
- 약관 논리 기반 소명 성공률 예측(0~100%) 및 핵심 반박 근거 자동 추출
- 소명 편지 자동 작성 + 복사 기능
- PDF 없이도 전체 흐름을 시연할 수 있는 샘플 케이스 지원

**Claude API 활용**
- OCR 없이 PDF를 base64로 인코딩해 Claude에 직접 전달, 약관 원문 전체를 분석에 활용
- 시스템 프롬프트로 JSON 구조화 출력을 강제해 프론트엔드에서 바로 파싱
- API 키는 서버(Route Handler)에서만 처리해 브라우저에 노출되지 않도록 설계

**한계**
실제 법적 효력이 있는 소명 자료가 아닌 시연 목적의 프로토타입이며, 진료 기록과 결합한 손해사정 리포트 기능은 확장 과제로 남겨두었습니다.

</details>

---

## BangCheck — 자취방 계약 체크리스트

`2026.03 – 2026.05` · 팀 프로젝트 (백엔드 담당) · [Live](https://bangcheck.site) · SWYP 13기

자취방 계약 전 점검 항목을 관리하고 방 상태를 기록 · 공유하는 웹 서비스입니다. 백엔드 4명 중 한 명으로 인증/인가와 배포 인프라를 담당했습니다.

**기술 스택:** `Spring Boot 3.6` `Spring Security` `JPA` `MySQL` `AWS EC2`

<details markdown="1">
<summary>자세히 보기</summary>

**담당 영역 — 인증/인가**
- Naver · Google OAuth2 소셜 로그인 구현 (Spring Security 기반 인증 흐름 설계)
- JWT 발급 · 검증 · 갱신 처리

**담당 영역 — 인프라 / 배포**
- AWS EC2 프로비저닝 및 Elastic IP 고정 할당
- Gabia 도메인 DNS A레코드 연동 (`bangcheck.site`)
- OAuth2 리다이렉트 URI 운영 환경 반영
- `application-local.yml` / `application-prod.yml` 프로파일 분리로 환경별 설정 관리

**배운 점**
OAuth2 + JWT 인증 흐름 설계부터 실제 배포까지 전 과정을 경험했고, 브랜치 전략 · PR 컨벤션 등 팀 협업 규칙을 제안하고 적용했습니다.

</details>

---

## 유연의료 플랫폼 — 정부 R&D 과제

`2025.07 – 2026.01` · 인턴 개발자 (프론트 · 인프라 백엔드 · AI 백엔드)

정부 R&D 과제로 운영 중인 의료 플랫폼에, 확정된 기능 명세를 기반으로 프론트엔드부터 인프라 백엔드까지 전 파트를 구현했습니다.

**기술 스택:** `React` `TypeScript` `Spring Boot` `Kubernetes` `KubeVirt` `Harbor`

<details markdown="1">
<summary>자세히 보기</summary>

- **SW 가상 로깅 화면**: Kubernetes Java Client로 VM/컨테이너 로그를 조회해 프론트에 실시간 시각화. Recoil로 상태 관리, `ReactJson`으로 JSON·텍스트 로그 파싱 렌더링
- **SW 가상 자원 리스트**: 클러스터 노드 및 K8s 서버 목록 조회 API 및 테이블 렌더링
- **SW 자동 패키지 검사**: Harbor 레지스트리와 Helm OCI Repository를 연동한 패키지 자동 검사 기능 (프론트/백엔드 전 구간)
- **GPU VM 생성 시도**: KubeVirt 기반 GPU passthrough 구조와 Kubernetes Extended Resource 개념을 학습하며 리소스 할당 실험
- 짧은 기간 내 KubeVirt, Helm OCI 등 낯선 기술 스택을 습득해 실무에 바로 적용

</details>

---

## EKS 기반 중고거래 플랫폼 인프라 구축

`2024` · 팀 프로젝트 (Architecting · Monitoring 담당)

가상 고객사 시나리오를 기반으로, 중고거래 서비스를 위한 AWS EKS 기반 3-tier 인프라를 설계 · 구축한 클라우드 교육 프로젝트입니다.

**기술 스택:** `AWS (EKS·RDS Aurora·ALB·CloudFront)` `Kubernetes` `Docker` `Prometheus` `Grafana`

<details markdown="1">
<summary>자세히 보기</summary>

**고객 요구사항 대응**
- **안정성 · 비용**: RDS MySQL → Aurora 전환, 가용영역 2개 → 3개로 확장해 트래픽 급증 시 지연 문제 해결
- **운영 자동화**: EKS 기반 컨테이너 오케스트레이션 도입으로 수동 확장 · 배포 부담 제거
- **보안 · 모니터링**: AWS WAF로 외부 공격 차단, Prometheus/Grafana로 성능 및 이상 징후 실시간 감지

**구현 내용**
- 3개 가용영역에 Public/Private/DB 서브넷 구성, Bastion Host를 통한 Private EC2 접근
- IAM 그룹별 권한 분리, CloudTrail·Inspector·Security Hub로 보안 점검 체계 구축
- Prometheus + Grafana Helm 배포로 클러스터 모니터링 대시보드 구성

**트러블슈팅**
Node.js 서버의 라우팅 경로 오류(`Cannot GET /`)를 정적 파일 디렉토리 참조 문제로 진단하고 경로를 수정해 해결했습니다.

</details>

---

## ColorGlow — 딥러닝 퍼스널 컬러 진단 앱

`2024.03 – 2024.05` · 팀 프로젝트 (Android 개발 담당) · [GitHub](https://github.com/dlwldP/Capstone2024)

얼굴 사진을 CNN으로 분석해 퍼스널 컬러를 진단하고 맞춤 화장품을 추천하는 Android 앱입니다. 교내 캡스톤 디자인 프로젝트로 진행했습니다.

**기술 스택:** `Kotlin` `Node.js` `Python/TensorFlow` `Firebase`

<details markdown="1">
<summary>자세히 보기</summary>

- CNN 모델로 얼굴 이미지를 분석해 12가지 퍼스널 컬러 유형으로 분류 (Validation Accuracy 91.67%)
- 연예인 이미지 약 13만 장을 크롤링 · 전처리해 6만 장 규모의 학습 데이터셋 구축
- 진단 결과 기반 화장품 추천, 진단 이력 관리, 커뮤니티(게시글 · 댓글 · 좋아요) 기능 구현
- Firebase(Firestore · Storage · Authentication) 기반 데이터/인증 처리

</details>
