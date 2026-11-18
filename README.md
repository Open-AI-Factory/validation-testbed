# validation-testbed

테스트베드 실증, 성능 검증 및 TCO 분석 저장소입니다.

## Upstream Open-Source Contributions

### 1. NVIDIA Dynamo (`ai-dynamo/dynamo`)

| 기여자 | PR 번호 및 제목 | 기여 내용 | 링크 |
| :--- | :--- | :--- | :--- |
| 이주은 | #9537 | DGDR `spec.sla.{ttft,itl}`을 PlannerConfig로 전파 — 사용자 SLA가 기본값에 덮이던 버그, 이슈 #8469 하위 건 | [PR #9537](https://github.com/ai-dynamo/dynamo/pull/9537) |
| 이주은 | #9877 | AIC 호출 시 로컬 PVC 모델 경로 사용 — 이슈 #9876 제보 → 해결, 단위테스트 16개 추가 | [PR #9877](https://github.com/ai-dynamo/dynamo/pull/9877) |
| 이주은 | #10086 | 병렬 구성 라벨을(`tp,pp,dp,moe_tp,moe_ep`)에 대해 단사로 수정 — 서로 다른 토폴로지가 같은 라벨로 뭉개지던 버그 | [PR #10086](https://github.com/ai-dynamo/dynamo/pull/10086) |
| 이주은 | #10092 | autoscale 모드에서 prefill/decode replicas 1 고정 — AIC 재배율이 picker 의도를 덮어쓰던 버그 | [PR #10092](https://github.com/ai-dynamo/dynamo/pull/10092) |
| 이주은 | #10125 | decode `num_request` 스윕을 KV-cache 용량 안으로 제한 — `attn_dp_size` 이중 곱으로 MoE 프로파일링 재시작 루프 유발 | [PR #10125](https://github.com/ai-dynamo/dynamo/pull/10125) |
| 이주은 | #10804 | 예측 부하·엔진 용량 게이지 5개를 throughput 틱에만 갱신 — Grafana가 항상 0을 읽던 문제, #8575 가드 확장 | [PR #10804](https://github.com/ai-dynamo/dynamo/pull/10804) |
| 이주은 | #10824 | Grafana planner 대시보드의 죽은 Correction Factor 패널 3개 제거 — #7961 메트릭 삭제 후 미정리분 | [PR #10824](https://github.com/ai-dynamo/dynamo/pull/10824) |
| 이주은 | #10791 | `sin_load_generator` isl/osl 인자 설명 정정 — min/max가 아닌 프리셋 명, 문서만 변경 | [PR #10791](https://github.com/ai-dynamo/dynamo/pull/10791) |
| 이주은 | #11221 | GlobalPlanner GPU 예산이 v1beta1 DGD에서 비활성화되는 버그 — 이슈 #11220 제보 → 메인테이너 PR #11990으로 해결(흡수) | [PR #11221](https://github.com/ai-dynamo/dynamo/pull/11221) |
| 박민철 | #10712 — SLA 기반 추론 성능 모니터링 고도화 | • NVIDIA Dynamo의 Grafana Dashboard에 TTFT 및 ITL SLA 목표값과 실측 지연시간을 비교하는 시각화 기능 구현.<br>• SLA 준수 여부에 대한 실시간 가시성을 확보하여 AI 추론 서비스의 성능 모니터링 및 운영 효율성 강화. | [PR #10712](https://github.com/ai-dynamo/dynamo/pull/10712) |
| 박민철 | #10770 — Observability 배포 안정성 개선 | • NVIDIA Dynamo의 모니터링 구성 스크립트에서 Kubernetes Namespace 불일치로 발생하는 Helm 배포 오류 수정.<br>• Namespace 동적 설정 기능을 도입하여 다양한 Kubernetes 배포 환경에 대한 호환성과 운영 안정성 개선. | [PR #10770](https://github.com/ai-dynamo/dynamo/pull/10770) |
| 박민철 | #10657 — Kubernetes CRD API 마이그레이션 자동화 | • NVIDIA Dynamo의 Kubernetes CRD API 버전(v1alpha1 → v1beta1) 자동 변환 CLI 유틸리티 개발.<br>• 기존 Operator의 Conversion Webhook을 활용하여 API 버전 전환 시 호환성 확보 및 수작업 마이그레이션 부담 최소화. | [PR #10657](https://github.com/ai-dynamo/dynamo/pull/10657) |
| 박민철 | #10032 — SLA 메트릭 기반 Observability 확장 | • NVIDIA Dynamo Planner에 TTFT 및 ITL SLA 목표값을 Prometheus 메트릭으로 제공하는 기능 구현.<br>• 추론 지연시간의 실측·예측값과 SLA 목표값을 연계하여 SLA 기반 성능 분석 및 모니터링 체계 강화. | [PR #10032](https://github.com/ai-dynamo/dynamo/pull/10032) |
| 남창현 | #13258 — PD 분리 환경 LMCacheMPConnector 지원 | • NVIDIA Dynamo vLLM 프론트엔드에서 LMCacheMPConnector가 "Unsupported kv_connector"로 거부되던 문제를 커넥터 프로토콜 등록 및 `produces_kv_transfer_params` 플래그 도입으로 해결.<br>• Dynamo에서 LMCache MP 기반 Prefill/Decode 분리 서빙 동작하도록 지원, 회귀 방지 테스트 5개 추가. | [PR #13258](https://github.com/ai-dynamo/dynamo/pull/13258) |
| 남창현 | #13444 — Kubernetes Operator CI 블로커 해소 | • PodSnapshot CRD 이동 이후 갱신되지 않은 kustomize OpenAPI 스키마 재생성.<br>• 전체 PR의 Pre Merge Recipe Check가 실패하던 CI 블로커를 해소하여 개발 파이프라인 안정성 복구. | [PR #13444](https://github.com/ai-dynamo/dynamo/pull/13444) |

---

### 2. NVIDIA NIXL (`ai-dynamo/nixl`)

| 기여자 | PR 번호 및 제목 | 기여 내용 | 링크 |
| :--- | :--- | :--- | :--- |
| 남창현 | #2146 — cuda_gds 백엔드 전송 상태 체크 non-blocking화 및 batch 라이프사이클 재설계 | • NVIDIA NIXL GPUDirect Storage(cuda_gds) 백엔드 핵심 전송 경로에서 상태 체크가 사실상 blocking으로 동작해 부분 완료 처리가 도달 불가능하던 구조적 결함과, cancel 이후 진행 중인 I/O가 재사용된 batch 버퍼를 덮어쓸 수 있던 데이터 안전성 문제를 해결: 상태 체크를 non-blocking으로 전환하고 cuFile 완료 보고까지 batch를 유지하도록 라이프사이클 재설계.<br>• in-flight batch가 남은 요청의 조기 release 차단, status 호출 실패 시 batch 컨텍스트 재생성 등 복구 경로를 새로 설계하고 poll-failure 복구 테스트를 기본 탑재, B200 + Gen5 NVMe 실측으로 처리량 저하 없음 확인. | [PR #2146](https://github.com/ai-dynamo/nixl/pull/2146) |
| 남창현 | #2068 — nixlbench 벤치마크 결과 신뢰성 개선 | • `--op_type` 오타가 WRITE로 조용히 실행되고 일관성 검사까지 스킵되던 문제를 인자 검증 추가로 차단.<br>• READ로 표기된 결과가 실제로는 WRITE였던 벤치마크 결과 오류 가능성 제거. | [PR #2068](https://github.com/ai-dynamo/nixl/pull/2068) |
| 남창현 | #2069 — cuda_gds 백엔드 에러 메시지 개선 | • cuFile 에러 메시지에 실패 API명, CUFILE_ERRSTR, 에러 코드를 포함하도록 개선.<br>• 실제 원인이 cuFile.log에만 남아 진단이 어렵던 문제를 해소하고 GDS_MT 백엔드와 로그 형식 통일. | [PR #2069](https://github.com/ai-dynamo/nixl/pull/2069) |
| 남창현 | #2070 — GDS compat mode 대용량 batch hang 트러블슈팅 문서화 | • nixlbench README에 bounce buffer 대기(기본 slab 수 < in-flight 엔트리 수)로 인한 hang 원인과 재현법 정리.<br>• DEBUG 로그 지표 및 `posix_pool_slab_count` 조정법을 문서화하여 운영자 자가 진단 지원. | [PR #2070](https://github.com/ai-dynamo/nixl/pull/2070) |
| 남창현 | #2143 — gds_mt IO 실패 로그 에러 디코딩 수정 | • cuFile 에러를 strerror 대신 CUFILE_ERRSTR로 디코딩하여 "Unknown error 5027" 같은 무의미한 메시지 수정.<br>• IS_CUFILE_ERR 헬퍼로 read/write 경로 에러 처리 통일. | [PR #2143](https://github.com/ai-dynamo/nixl/pull/2143) |
| 남창현 | #2305 — cuda_gds cuFile 에러 상세 정보 복원 | • 리팩토링(#1856) 과정에서 사라진 cuFile 에러 상세(#2069)를 gdsCuFileError() 헬퍼로 전 에러 지점에 복원.<br>• 기존 로그 prefix를 유지하여 테스트 ignore 패턴과의 호환성 보장. | [PR #2305](https://github.com/ai-dynamo/nixl/pull/2305) |
| 남창현 | #2307 — nixlbench `--filepath` 인자 사전 검증 | • 백엔드와 양쪽 프로세스 기동 후에야 실패하던 문제를 인자 파싱 단계에서 기존 디렉토리 여부 검증으로 조기 차단.<br>• README 예시 정정으로 사용자 혼란 방지. | [PR #2307](https://github.com/ai-dynamo/nixl/pull/2307) |

---

### 3. NVIDIA Modelexpress (`ai-dynamo/modelexpress`)

| 기여자 | PR 번호 및 제목 | 기여 내용 | 링크 |
| :--- | :--- | :--- | :--- |
| 이주은 | #729 | 하나의 mx 서버를 여러 네임스페이스에서 공유하는 방법 문서화 — 워커 측 설정과 공유 풀 영향 정리, 실측 검증 포함 | [PR #729](https://github.com/ai-dynamo/modelexpress/pull/729) |

---

### 4. LMCache (`LMCache/LMCache`)

| 기여자 | PR 번호 및 제목 | 기여 내용 | 링크 |
| :--- | :--- | :--- | :--- |
| 남창현 | #3935 — Dynamo + LMCache MP 통합 레시피 추가 | • aggregated/disaggregated 두 모드의 DGD 매니페스트와 로컬 런처 스크립트를 `examples/dynamo_integration`에 추가.<br>• disaggregated 모드에서 P/D worker가 MP 서버 하나를 공유하는 구조로, NVIDIA Dynamo 측 LMCache MP 지원(#13258)의 선행 검증 기반 마련. | [PR #3935](https://github.com/LMCache/LMCache/pull/3935) |
| 남창현 | #5772 — MP 모드 NIXL GDS L2 백엔드 동작 문서화 | • NVIDIA NIXL GDS/GDS_MT L2 백엔드가 GPU direct가 아닌 호스트 L1 풀 기준으로 동작함을 문서에 명시.<br>• GPU direct가 필요한 경우 GDS L1 티어로 안내하여 사용자 구성 오류 방지. | [PR #5772](https://github.com/LMCache/LMCache/pull/5772) |
