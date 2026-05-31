---
title: 김성진 | Seongjin Kim
---

개발자에서 엔지니어로, 엔지니어에서 리더로.
Backend 엔지니어 김성진입니다.

## Contacts

- Email: sjinkim000625@gmail.com
- Birth: 2000.06.25

{% include button.html text="Github" icon="github" link="https://github.com/ksj000625" color="#000000" %} {% include button.html text="LinkedIn" icon="linkedin" link="https://www.linkedin.com/in/seongjin-kim-92743b333" color="#0077b5" %} {% include button.html text="velog" link="https://velog.io/@playername_ltt" color="#20C997" %}

---

## Introduce

- 언제나 최적의 방법을 찾아 문제를 해결하는데 집중하는 엔지니어입니다.
- 단순 기능 구현을 넘어, 기능 구현을 수행할 때 마주하는 문제들을 **조직에 맞는 기술적 의사결정**을 통해 문제를 해결합니다.
- 한계를 정하지 않고, 트렌드에 매몰되지 않는 문제 해결의 본질을 파악할 줄 아는 엔지니어입니다.

---

## Work Experience

### (주)아롬정보기술 | Backend Engineer, 2024.08 -

- 소속: AI연구소(구 기업부설연구소)
- **Skill**: Spring Boot, FastAPI, HuggingFace, MySQL, MyBatis, JPA, QueryDSL, Redis Streams, Redis Pub/Sub, Vue.js, Quasar Framework, Flutter, NCloud
- 참여 프로젝트:
  - MICE AI - 국제 컨퍼런스 실시간 통번역 서비스
  - AromSR - 개인용 실시간 통역 서비스
  - 서울랜드 앱 관리자 페이지

#### ● 실시간 AI 통역 서비스 백엔드 개발

- WebSocket 기반으로 STT → LLM 통역 → TTS로 이어지는 실시간 통번역 파이프라인 개발
- gemma3, translategemma 모델을 활용한 통번역 에이전트 개발 및 운영
- 언어별 “통역 → TTS” 파이프라인을 비동기 구조로 고도화하여 실시간성 개선
- 구/절 단위 누적 번역과 문장별 분리 보정 로직을 언어별로 병렬 처리하도록 설계
- TTS Stream API 방식의 병렬 호출 구조를 설계하고, 통역 결과 품질 유지를 위한 순서 보장 로직 개발

#### ● LLM 번역 품질 및 지연시간 개선

- 기존 번역 과정에서 번역 속도 저하, 맥락 이해 부족, 불필요 텍스트 출력 문제가 발생
- 초기 페르소나 및 few-shot 중심 프롬프트 구조에서 시스템 프롬프트와 사용자 입력을 분리, 이전 맥락을 정규화하는 방식으로 개선
- 불필요한 few-shot을 제거하고, 실시간 통역에 필요한 세부 지침을 강화하여 번역 품질 개선
- gemma-3-27b-it 모델 대비 더 빠른 추론 시간과 적은 GPU 리소스 사용을 근거로 translategemma-12b-it 모델 도입
- GPU 인스턴스를 클라우드 플랫폼별 비교 후 자체 GPU
- COMET Score 기반으로 번역 품질을 검증한 뒤 최종 모델 변경
- 번역 속도 평균 1.2s → 0.6s로 **평균 50% 개선**
- COMET Score 평균 0.75 → 0.82로 약 **8.6% 개선, 자연스러운 번역결과 유도 성공**

#### ● Redis 기반 실시간 브로드캐스팅 구조 개발

- Scale-out 환경에서도 동일한 컨퍼런스 데이터를 안정적으로 수신할 수 있도록 Redis 기반 브로드캐스팅 로직 개발
- 세미나 세션별 참여자 세션 관리 및 Role-based Access Control 기반 역할별 데이터 브로드캐스팅 처리
- 번역 결과 및 원문은 스크립트 생성을 위해 Redis Streams에 저장
- TTS 데이터는 휘발성 데이터 특성을 고려하여 Redis Pub/Sub 기반으로 처리
- 실시간 메시징 처리와 캐싱 구조를 분리하여 데이터 성격에 맞는 저장 전략 설계

#### ● 백엔드 아키텍처 및 리소스 효율 최적화

- LLM API 호출 및 TTS 합성 등 외부 I/O 블로킹 구간에서 Thread Per Request 모델의 메모리 점유 문제가 발생
- Java Virtual Thread를 도입하여 블로킹 I/O 구간의 리소스 효율 개선
- 메모리 누수 방지를 위해 Context Cleanup 인터셉터를 구현
- 비정상 종료된 WebSocket 세션의 자원을 실시간으로 회수하여 시스템 가용성 유지
- WebSocket 세션 종료 시 잔존하는 ThreadLocal 및 비동기 작업의 Memory Leak 방지를 위한 Lifecycle 관리 로직 설계 및 자동화

#### ● 서울랜드 앱 관리자 서비스 개발

- 서울랜드 앱 관리자 웹 서비스의 백엔드 API 및 프론트엔드 기능 개발
- 기능 중심의 관리자 웹 개발을 수행하며, 서비스 유지보수용 UX에 집중
- Quasar Framework 기반 공통 컴포넌트 분리를 통해 유지보수성과 확장성 확보
- 기존 개발사의 리소스를 분석하고 리뉴얼 개발 수행
- 기존 DB 스키마를 유지하면서 복합 조건 기반 API 및 쿼리 개발
- 서울랜드 어트랙션 예약 서비스 ‘루나패스’ 관리 API 개발

#### ● 서울랜드 앱 'Bloom' 숏폼 백엔드 개발

- Spring Webflux와 Vimeo API를 활용한 비동기 영상 업로드 서버 개발
- 업로드 완료 시 웹훅 기능 개발
- 숏폼 컨텐츠 테이블 및 API 설계, 개발
- 유저 프로필 기능 2차 개발

---

## License

- **정보처리기사** |
  한국산업인력공단, 2025.09.12
- **SW개발\_L5_LV20** |
  한국산업인력공단, 2025.02.27
- **네트워크관리사 2급** |
  한국정보통신자격협회, 2022.04.12

---

## Awards

- 명지대학교 캡스톤디자인 경진대회 장려상 / 2024.06

---

## Education

#### 명지대학교 자연캠퍼스 / 컴퓨터공학과 학사 (2019.03 ~ 2025.02)

- 학점 : 3.56 / 4.5
- 소재지 : 경기도 용인

---

## Activity

#### AI 서비스 엔지니어링 트랙 6기 / 스파르타클럽 재직자 부트캠프 (2025.11 ~ 2026.02)

- 최우수 수료팀
- AI 서비스 개발 및 엔지니어링 실무 역량 강화
- LLM 기반 서비스 설계, 운영, 개선 관점의 실습 수행

---

## Side Projects

### Monix | 전체적인 개발 + 에이전트 기능 확장

**2025년, CMUX x AIM Intelligence Hackathon, Developer tooling track**

{% include button.html text="GitHub" icon="github" link="https://github.com/co-tox/monix" color="#000000" %}

- **Skill**: Python, Google Gemini, OpenAI Codex, MCP (Model Context Protocol)
- 터미널 네이티브 AI 어시스턴트로, 슬래시 명령어 CLI와 LLM 대화형 에이전트를 결합한 서버 모니터링 도구
- CPU, 메모리, 디스크, 프로세스, 서비스 로그 등 실시간 모니터링
- 자연어 기반 서버 모니터링 설정 및 제어
- Discord / Slack 웹훅 알림 연동
- MCP 서버 연동 지원

---

### BillBill | 백엔드 개발

**2025년, 사이드 프로젝트**

{% include button.html text="GitHub" icon="github" link="https://github.com/billbill-project/bill-api-server" color="#000000" %}

- **Skill**: Java, Spring Boot, JPA, QueryDSL, MySQL, RabbitMQ, Firebase FCM, AWS S3, Kakao OAuth, JWT, Docker
- 물건을 빌려주고 빌릴 수 있는 물품 대여 중개 플랫폼 API 서버
- 대여 게시물 CRUD 및 검색 기능 개발
- RabbitMQ 기반 채팅 기능 개발
- Firebase FCM 기반 푸시 알림 개발
- Kakao OAuth 소셜 로그인 개발

---

### ARY - All Review Young | 백엔드 개발

**2024년, 캡스톤 디자인 프로젝트**

{% include button.html text="GitHub" icon="github" link="https://github.com/Foolish-Bros/ARY-Server" color="#000000" %}

- **Skill**: Java, Spring Boot, JWT, Spring Security, OAuth2 (Google / Kakao / Naver), JPA, AWS Elastic Beanstalk
- 온라인 쇼핑몰 리뷰 기반 챗봇 Q&A 서비스
- Jsoup 기반 웹 크롤링 기능 개발
- Google / Kakao / Naver OAuth2 소셜 로그인 개발

---

### Clover | 프론트엔드 개발

**2023년, 시각디자인학과 전시회를 위한 관객참여형 웹 서비스**

{% include button.html text="GitHub" icon="github" link="https://github.com/2024Clover-website/Clover-Client" color="#000000" %}

- **Skill**: React, CSS Modules, Node.js, Nginx, AWS Elastic Beanstalk
- Web Media API를 이용한 음성파일 제어 기능 개발
- 프로젝트 구조 설계
