# Event Ticket

Go 기반 이벤트 티켓 예약 시스템을 개발하고 운영하는 SRE 포트폴리오.

## 목표
- 동시 예약에도 좌석 중복 판매 방지
- 장애와 재시도에도 예약 및 티켓 데이터의 일관성 유지
- 메트릭·로그·트레이스를 통한 장애 진단
- 부하 테스트와 장애 실험으로 성능 및 복구 동작 검증

## 기술 구성
- 애플리케이션: Go, gRPC
- 데이터: PostgreSQL, Redis, Kafka
- 플랫폼: 별도 서버의 WSL2, k3s
- 서비스 메시: Istio Ambient
- 외부 진입점: Istio Ingress Gateway, MetalLB
- 관측: Prometheus, Grafana, OpenTelemetry
- 인프라 설정 관리: Helm, Kustomize

## 디렉터리
| 경로 | 용도 |
|---|---|
| services/ | Go 서비스 구현 |
| proto/ | gRPC API 계약 |
| deploy/apps/ | 애플리케이션 배포 설정 |
| deploy/data/ | PostgreSQL, Redis, Kafka 설정 |
| deploy/istio/ | Istio Ambient 및 Gateway 설정 |
| deploy/monitoring/ | 관측 및 알림 설정 |
| docs/ | 설치 기록, 설계, 운영 문서 |

## 관리 원칙
- 설정 변경은 파일에 반영하고 Git으로 기록한다.
- 차트 및 이미지 버전을 명시한다.
- 비밀번호, 토큰, 개인 키, kubeconfig는 커밋하지 않는다.
- Git push만으로 서버에 자동 배포되지는 않는다.

현재 구축 중이며, 설치 및 검증 여부는 docs/에 기록한다.
