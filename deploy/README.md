# 배포 설정

클러스터에 적용할 인프라 및 애플리케이션 설정을 관리한다.

## 구성
- apps/: 직접 개발한 Go 서비스의 배포 설정
- data/: PostgreSQL, Redis, Kafka의 Helm values 및 관련 리소스
- istio/: Ambient 구성 요소와 Ingress Gateway 설정
- monitoring/: 메트릭, 로그, 트레이스, 알림 설정

## 관리 원칙
- Helm 차트 원본보다 프로젝트에서 변경한 values를 관리한다.
- 설치 명령에 차트 버전과 values 파일 경로를 명시한다.
- Kustomize 설정은 base와 환경별 overlays로 확장한다.
- 설치 순서, 선행 조건, 확인 방법은 docs/에 기록한다.
- 실제 비밀 값이 포함된 Secret YAML은 커밋하지 않는다.

MetalLB 설정은 구성 단계에서 별도 디렉터리를 추가한다.
