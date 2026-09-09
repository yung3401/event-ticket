# 관측 및 알림

서비스와 클러스터의 상태를 관측하기 위한 설정을 관리한다.

## 구성 방향
- Prometheus: 메트릭 수집 및 저장
- Grafana: 대시보드 및 데이터 조회
- OpenTelemetry Collector: 텔레메트리 수집·처리·전송
- Alertmanager: 알림 그룹화 및 전달
- 로그·트레이스 저장소: Loki, Tempo 또는 Jaeger 중 구성 확정 후 반영

## 관리 대상
- Helm values 및 버전
- ServiceMonitor, PodMonitor 및 수집 설정
- 알림 규칙과 전달 경로
- Grafana 대시보드
- 보존 기간, 저장 용량, 샘플링 설정

## 주요 관측 대상
- 요청량, 오류율, 지연 시간
- 예약 성공·실패 및 만료
- Kafka 소비 지연
- DB 연결과 쿼리 성능
- Pod 재시작과 CPU·메모리 사용량

Discord webhook URL 등 인증 정보는 커밋하지 않는다.
SLO와 알림 대응 절차는 docs/에 기록한다.
