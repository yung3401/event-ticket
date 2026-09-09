# 애플리케이션 배포

직접 개발한 Go 서비스의 Kubernetes 리소스를 관리한다.

## 관리 대상
- Deployment, Service, ServiceAccount
- ConfigMap 및 Secret 참조
- startup/readiness/liveness probe
- CPU·메모리 requests와 limits
- 필요 시 HPA, PDB 및 애플리케이션 트래픽 정책

## 구성 방향
- 공통 리소스는 Kustomize base에 둔다.
- 환경별 변경은 overlays에 둔다.
- 이미지 버전과 설정 변경을 코드 변경과 함께 기록한다.

Go 소스는 services/, gRPC 계약은 proto/에서 관리한다.
