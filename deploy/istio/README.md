# Istio Ambient

사이드카를 애플리케이션 Pod마다 주입하지 않는 Ambient 메시 설정을 관리한다.

## 구성 요소
- base: Istio CRD 및 공통 리소스
- istiod: 컨트롤 플레인
- istio-cni: 트래픽을 Ambient 데이터 플레인으로 연결
- ztunnel: 노드별 프록시
- Ingress Gateway: 외부 요청 수신 및 라우팅
- waypoint: 필요한 경우 메시 내부 L7 기능 제공

## 관리 원칙
- Helm으로 설치하고 구성 요소별 values 파일을 관리한다.
- Istio 구성 요소의 차트 버전을 함께 기록한다.
- k3s 환경에 맞는 CNI 플랫폼 설정을 적용한다.
- Ambient 적용 namespace를 명시적으로 관리한다.
- Gateway API 사용 시 필요한 CRD 버전도 기록한다.

MetalLB는 Gateway의 외부 IP 제공을 담당하며 별도로 관리한다.
설치 결과와 검증 명령은 docs/에 기록한다.
