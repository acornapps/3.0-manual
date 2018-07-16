## 5.5.1 알람 목록

---

알람은 다음 목록에서 발생 조건이 지속 시간 만큼 계속 될 경우 발생한다.

* #### AlertManager

| 알람 ID | **ALM-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | AlertmanagerDown |
| 지속 시간 | 5분 |
| 발생 조건 | Alertmanager 메트릭 수집이 안 될 경우 발생 |

| 알람 ID | **ALM-002** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | AlertmanagerFailedReload |
| 지속 시간 | 10분 |
| 발생 조건 | Alertmanager의 설정 변경시, 설정 다시읽기 작업 실패시 발생 |

* #### ETCD3

| 알람 ID | **ETC-001** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | InsufficientMembers |
| 지속 시간 | 3분 |
| 발생 조건 | ETCD 메트릭 수집이 안 될 경우 발생 |

| 알람 ID | **ETC-002** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | NoLeader |
| 지속 시간 | 1분 |
| 발생 조건 | ETCD 리더가 없을 경우 발생 |

| 알람 ID | **ETC-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighNumberOfLeaderChanges |
| 지속 시간 | 즉시 |
| 발생 조건 | 최근 1시간 동안 3번 이상의 리더 변경이  발생할 경우 |

| 알람 ID | **ETC-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighNumberOfFailedGRPCRequests |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5 분 이내에 gRPC 메소드 호출의 1% 이상 실패한 경우 |

| 알람 ID | **ETC-005** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | HighNumberOfFailedGRPCRequests |
| 지속 시간 | 5분 |
| 발생 조건 | 최근 5 분 이내에 gRPC 메소드 호출의 5% 이상 실패한 경우 |

| 알람 ID | **ETC-006** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | GRPCRequestsSlow |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안 gRPC 메서드 요청 대기 시간 중 99 번째 백분위가 150ms보다 클 경우 |

| 알람 ID | **ETC-007** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighNumberOfFailedHTTPRequests |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5 분 이내에 HTTP 엔드 포인트에 대한 요청의 1% 이상이 실패한 경우 |

| 알람 ID | **ETC-008** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | HighNumberOfFailedHTTPRequests |
| 지속 시간 | 5분 |
| 발생 조건 | 최근 5 분 이내에 HTTP 엔드 포인트에 대한 요청의 5% 이상이 실패한 경우 |

| 알람 ID | **ETC-009** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HTTPRequestsSlow |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안의 HTTP 요청 대기 시간 중 99번째 백분위가 150ms보다 클 경우 |

| 알람 ID | **ETC-010** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | EtcdMemberCommunicationSlow |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안의 멤버간 통신 대기 시간 중 99번째 백분위가 150ms보다 클 경우 |

| 알람 ID | **ETC-011** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighNumberOfFailedProposals |
| 지속 시간 | 즉시 |
| 발생 조건 | 최근 1시간 동안 5개 이상의 실패한 raft protocol 요청이있을 경우 |

| 알람 ID | **ETC-012** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighFsyncDurations |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안의 fsync 지속 시간의 99번째 백분위가 500ms보다 클 경우 |

| 알람 ID | **ETC-013** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighCommitDurations |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안의 커밋 지속 시간 중 99번째 백분위가 250ms보다 클 경우 |

* #### General

| 알람 ID | **GEN-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | TargetDown |
| 지속 시간 | 10분 |
| 발생 조건 | 메트릭 수집 작업이 안 될 경우 발생. 어떤 작업이 실패인지 표시됨. |

| 알람 ID | **GEN-002** |
| :--- | :--- |
| 중요도 | ~~none~~ |
| 알람 이름 | DeadMansSwitch |
| 지속 시간 | 즉시 |
| 발생 조건 | DeadMansSwitch 알림 |

| 알람 ID | **GEN-003** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | TooManyOpenFileDescriptors |
| 지속 시간 | 10분 |
| 발생 조건 | file descriptor 사용율이 95%이상 일때 발생 |

| 알람 ID | **GEN-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | FdExhaustionClose |
| 지속 시간 | 10분 |
| 발생 조건 | 단순회귀분석(simple linear regression)을 이용하여 4시간 이내에 file descriptor 고갈이 예측될 경우 발생 |

| 알람 ID | **GEN-005** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | FdExhaustionClose |
| 지속 시간 | 10분 |
| 발생 조건 | 단순회귀분석(simple linear regression)을 이용하여 1시간 이내에 file descriptor 고갈이 예측될 경우 발생 |

* #### Kube-ApiServer

| 알람 ID | **KAS-001** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SApiserverDown |
| 지속 시간 | 5분 |
| 발생 조건 | kube-apiserver 메트릭 수집이 안 될 경우 발생 |

| 알람 ID | **KAS-002** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | K8SApiServerLatency |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 10분 동안의 요청 대기 시간 중 99번째 백분위가 1s보다 클 경우 발생 |

* #### Kube-ControllerManager

| 알람 ID | **KCM-001** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SControllerManagerDown |
| 지속 시간 | 5분 |
| 발생 조건 | kube-controller-manager 메트릭 수집이 안 될 경우 발생 |

* #### Kube-Scheduler

| 알람 ID | **KSC-001** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SSchedulerDown |
| 지속 시간 | 5분 |
| 발생 조건 | kube-scheduler 메트릭 수집이 안 될 경우 발생 |

* #### Kube-State-Metrics

| 알람 ID | **KSM-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KSM-002** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KSM-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KSM-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KSM-005** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KSM-006** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

* #### Kubelet

| 알람 ID | **KBL-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KBL-002** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KBL-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KBL-004** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **KBL-005** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

* #### Node

| 알람 ID | **NOD-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **NOD-002** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **NOD-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **NOD-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **NOD-005** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **NOD-006** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

* #### Prometheus

| 알람 ID | **PRM-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

* #### Cocktail

| 알람 ID | **CKT-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **CKT-002** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **CKT-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |

| 알람 ID | **CKT-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 |  |
| 지속 시간 |  |
| 발생 조건 |  |



