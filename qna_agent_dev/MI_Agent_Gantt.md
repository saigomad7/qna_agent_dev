# MI Agent 프로젝트 간트차트 (6개월)

> 기간: 2026-04-27 ~ 2026-10-23 (26주)  
> 기술 스택: LangGraph | 개발 방식: Agent 1 / Agent 2 팀 **병렬 진행** (W9~W20)

---

## 간트차트

```mermaid
gantt
    title MI Agent 프로젝트 간트차트 (LangGraph 기반, A1/A2 병렬)
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%d

    section 공통 기반
    W1  킥오프 & 요구사항 인터뷰             :p1w1, 2026-04-27, 7d
    W2  요구사항 확정 (A1/A2 분리)           :p1w2, 2026-05-04, 7d
    W3  LangGraph 아키텍처 설계              :p1w3, 2026-05-11, 7d
    W4  기술스택 확정 & LangGraph Studio 셋업 :p1w4, 2026-05-18, 7d
    W5  공통 BaseState & ToolNode 구현       :p2w5, 2026-05-25, 7d
    W6  데이터 파이프라인 & LLM 래퍼 구현    :p2w6, 2026-06-01, 7d
    W7  Conditional Edge & HiTL 모듈 구현   :p2w7, 2026-06-08, 7d
    W8  E2E 프로토타입 검증 (LangGraph Studio):p2w8, 2026-06-15, 7d

    section Agent 1 — 시장 모니터링
    W9  MarketMonitoringState & 데이터 소스 Tool 구현   :a1w9,  2026-06-22, 7d
    W10 data_fetch_node & preprocessing_node 구현      :a1w10, 2026-06-29, 7d
    W11 anomaly_detection_node & 조건부 엣지 구현       :a1w11, 2026-07-06, 7d
    W12 market_analysis_node (LLM) 구현                :a1w12, 2026-07-13, 7d
    W13 alert_node & interrupt() Human Review 구현     :a1w13, 2026-07-20, 7d
    W14 report_generation_node & 피드백 로직            :a1w14, 2026-07-27, 7d
    W15 AsyncPostgresSaver & 장/단기 메모리 구현         :a1w15, 2026-08-03, 7d
    W16 A1 단위 테스트 (전 노드)                        :a1w16, 2026-08-10, 7d
    W17 이상 감지 정확도 & 프롬프트 최적화              :a1w17, 2026-08-17, 7d
    W18 A1 통합 파이프라인 테스트 & 파일럿 1주차        :a1w18, 2026-08-24, 7d
    W19 파일럿 2주차 & 피드백 반영                      :a1w19, 2026-08-31, 7d
    W20 A1 최종 검수 & 스테이크홀더 데모                :a1w20, 2026-09-07, 7d

    section Agent 2 — 딥리서치
    W9  ResearchState & 사내/외 정보소스 수집 파이프라인 :a2w9,  2026-06-22, 7d
    W10 retrieval_node (Hybrid Search) & Re-ranking    :a2w10, 2026-06-29, 7d
    W11 query_decomposition_node & Send API 병렬 서브그래프 :a2w11, 2026-07-06, 7d
    W12 synthesis_node & 반복 리서치 루프 구현           :a2w12, 2026-07-13, 7d
    W13 conversation_node & stream_mode 스트리밍 구현   :a2w13, 2026-07-20, 7d
    W14 insight_synthesis_node & 보고서 생성            :a2w14, 2026-07-27, 7d
    W15 Checkpointer 세션 이력 & 사내 권한 제어 구현    :a2w15, 2026-08-03, 7d
    W16 A2 단위 테스트 (전 노드 & 병렬 서브그래프)      :a2w16, 2026-08-10, 7d
    W17 RAG 품질 & 스트리밍 지연 최적화                 :a2w17, 2026-08-17, 7d
    W18 A2 통합 파이프라인 테스트 & 보안 점검            :a2w18, 2026-08-24, 7d
    W19 실사용자 인터랙티브 테스트 & 피드백 반영         :a2w19, 2026-08-31, 7d
    W20 A2 최종 검수 & 스테이크홀더 데모                :a2w20, 2026-09-07, 7d

    section 통합 & 배포
    W21 SupervisorAgent 구현 & A1→A2 자동 트리거        :intw21, 2026-09-14, 7d
    W22 A1+A2 E2E 통합 테스트 & LLM 비용 최적화         :intw22, 2026-09-21, 7d
    W23 QA & 보안 점검 & 런북 작성                       :intw23, 2026-09-28, 7d
    W24 UAT & 최종 안정화                               :intw24, 2026-10-05, 7d
    W25 운영 배포 (Blue/Green)                          :intw25, 2026-10-12, 7d
    W26 운영 이관 & 프로젝트 종료                        :intw26, 2026-10-19, 5d
```

---

## 마일스톤 타임라인

```mermaid
gantt
    title 마일스톤 요약
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%d

    section 마일스톤
    아키텍처 확정           :milestone, m1, 2026-05-24, 0d
    공통 프레임워크 완성    :milestone, m2, 2026-06-21, 0d
    A1/A2 단위 테스트 완료  :milestone, m3, 2026-08-16, 0d
    A1 & A2 개발 완료       :milestone, m4, 2026-09-13, 0d
    통합 완료               :milestone, m5, 2026-09-27, 0d
    UAT 완료                :milestone, m6, 2026-10-11, 0d
    운영 이관 완료          :milestone, m7, 2026-10-23, 0d
```

---

## 팀 구성 및 병렬 구조 요약

```
W1  ──── W8  : 전체 팀 공통 작업 (기획 + 공통 인프라)
                        │
              ┌─────────┴─────────┐
              ▼                   ▼
W9  ──── W20 : [A1 팀]          [A2 팀]
              시장 모니터링       딥리서치
              에이전트 개발       에이전트 개발
              └─────────┬─────────┘
                        │
W21 ──── W22 : 통합 (Supervisor 패턴, A1↔A2 연동)
W23 ──── W24 : QA / UAT / 안정화
W25 ──── W26 : 운영 배포 & 이관
```

---

## 주간 병렬 작업 현황 (W9~W20)

| 주차 | A1 팀 (시장 모니터링) | A2 팀 (딥리서치) |
|------|----------------------|----------------|
| W9  | MarketMonitoringState & 데이터 소스 Tool | ResearchState & 정보소스 수집 파이프라인 |
| W10 | data_fetch / preprocessing 노드 | retrieval_node (Hybrid Search) |
| W11 | anomaly_detection + 조건부 엣지 | query_decomposition + Send API 병렬 서브그래프 |
| W12 | market_analysis_node (LLM) | synthesis_node + 반복 리서치 루프 |
| W13 | alert_node + interrupt() Human Review | conversation_node + stream_mode 스트리밍 |
| W14 | report_generation + 피드백 로직 | insight_synthesis + 보고서 생성 |
| W15 | AsyncPostgresSaver + 장/단기 메모리 | Checkpointer 세션 이력 + 사내 권한 제어 |
| W16 | A1 전 노드 단위 테스트 | A2 전 노드 + 병렬 서브그래프 단위 테스트 |
| W17 | 이상 감지 정확도 & 프롬프트 최적화 | RAG 품질 & 스트리밍 지연 최적화 |
| W18 | A1 통합 테스트 + 파일럿 1주차 | A2 통합 테스트 + 보안 점검 |
| W19 | 파일럿 2주차 + 피드백 반영 | 실사용자 테스트 + 피드백 반영 |
| W20 | A1 최종 검수 & 데모 | A2 최종 검수 & 데모 |

---

*최종 업데이트: 2026-04-25 | LangGraph 기반 병렬 개발 구조*
