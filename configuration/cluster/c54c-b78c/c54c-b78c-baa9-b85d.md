## 5.5.1 알람 목록

---

알람은 다음 목록에서 발생 조건이 지속 시간 만큼 계속될 경우 발생한다.

* #### AlertManager

| 알람 ID | **ALM-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | AlertmanagerDown |
| 지속 시간 | 5분 |
| 발생 조건 | Alertmanager 메트릭 수집이 안 될 경우 발생 |
| 조치 사항 | Prometheus의 로그 및 Alertmanager의 로그와 이벤트를 확인한다. 필요할 경우, Pod를 재시작한다. |

| 알람 ID | **ALM-002** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | AlertmanagerFailedReload |
| 지속 시간 | 10분 |
| 발생 조건 | Alertmanager의 설정 변경시, 설정 다시읽기 작업 실패시 발생 |
| 조치 사항 | 해당 Pod의 로그를 확인하여 ConfigMap의 설정 오류를 수정한다. |

* #### ETCD3

| 알람 ID | **ETC-001** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | InsufficientMembers |
| 지속 시간 | 3분 |
| 발생 조건 | ETCD 메트릭 수집이 안 될 경우 발생 |
| 조치 사항 | ETCD 클러스터의 상태를 확인한다. Prometheus의 로그 및 해당 노드의 etcd 상태를 확인한다. |

| 알람 ID | **ETC-002** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | NoLeader |
| 지속 시간 | 1분 |
| 발생 조건 | ETCD 리더가 없을 경우 발생 |
| 조치 사항 | ETCD 클러스터의 상태를 확인한다. Disk Latency로 인한 문제 일 수 있으므로 다음 명령을 ETCD 클러스터 전체 노드에서 싷행한다. ```$ sudo ionice -c2 -n0 -p \`pgrep etcd\````  |

| 알람 ID | **ETC-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighNumberOfLeaderChanges |
| 지속 시간 | 즉시 |
| 발생 조건 | 최근 1시간 동안 3번 이상의 리더 변경이 발생할 경우 |
| 조치 사항 |  |

| 알람 ID | **ETC-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighNumberOfFailedGRPCRequests |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5 분 이내에 gRPC 메소드 호출의 1% 이상 실패한 경우 |
| 조치 사항 | ETCD 클러스터와 Kubernetes 클러스터의 대역폭을 늘리거나 클러스터의 Sacale-Up 필요. |

| 알람 ID | **ETC-005** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | HighNumberOfFailedGRPCRequests |
| 지속 시간 | 5분 |
| 발생 조건 | 최근 5 분 이내에 gRPC 메소드 호출의 5% 이상 실패한 경우 |
| 조치 사항 | ETCD 클러스터와 Kubernetes 클러스터의 대역폭을 늘리거나 클러스터의 Sacale-Up 필요. |

| 알람 ID | **ETC-006** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | GRPCRequestsSlow |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안 gRPC 메서드 요청 대기 시간 중 99 번째 백분위가 150ms보다 클 경우 |
| 조치 사항 | ETCD 클러스터와 Kubernetes 클러스터의 대역폭을 늘리거나 클러스터의 Sacale-Up 필요. |

| 알람 ID | **ETC-007** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighNumberOfFailedHTTPRequests |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5 분 이내에 HTTP 엔드 포인트에 대한 요청의 1% 이상이 실패한 경우 |
| 조치 사항 | ETCD 클러스터와 Kubernetes 클러스터의 대역폭을 늘리거나 클러스터의 Sacale-Up 필요. |

| 알람 ID | **ETC-008** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | HighNumberOfFailedHTTPRequests |
| 지속 시간 | 5분 |
| 발생 조건 | 최근 5 분 이내에 HTTP 엔드 포인트에 대한 요청의 5% 이상이 실패한 경우 |
| 조치 사항 | ETCD 클러스터와 Kubernetes 클러스터의 대역폭을 늘리거나 클러스터의 Sacale-Up 필요. |

| 알람 ID | **ETC-009** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HTTPRequestsSlow |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안의 HTTP 요청 대기 시간 중 99번째 백분위가 150ms보다 클 경우 |
| 조치 사항 | ETCD 클러스터와 Kubernetes 클러스터의 대역폭을 늘리거나 클러스터의 Sacale-Up 필요. |

| 알람 ID | **ETC-010** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | EtcdMemberCommunicationSlow |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안의 멤버간 통신 대기 시간 중 99번째 백분위가 150ms보다 클 경우 |
| 조치 사항 | ETCD 클러스터의 대역폭을 늘리거나 클러스터의 Scale-Up 필요. |

| 알람 ID | **ETC-011** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighNumberOfFailedProposals |
| 지속 시간 | 즉시 |
| 발생 조건 | 최근 1시간 동안 5개 이상의 실패한 raft protocol 요청이 있을 경우. \(RAFT Protocol은 ETCD 동기화 Protocol\) |
| 조치 사항 | ETCD 메트릭 문서\(https://github.com/coreos/etcd/blob/master/Documentation/metrics.md\)에 따르면 리더 선출의 일시적인 실패 또는 멤버 부족으로 인한 ETCD 클러스터 중단 시간이 길어질 경우 발생합니다. 리더가 있는지, 중단된 ETCD 멤버가 있는지 확인 |

| 알람 ID | **ETC-012** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighFsyncDurations |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안의 wal fsync 지속 시간의 99번째 백분위가 500ms보다 클 경우 \(wal fsync: 로그 항목을 적용하기 전에 디스크에 저장시 호출.\) |
| 조치 사항 | ETCD 메트릭 문서\(https://github.com/coreos/etcd/blob/master/Documentation/metrics.md\)에 따르면 디스크에 문제가 있을 경우 발생한다고 함. |

| 알람 ID | **ETC-013** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | HighCommitDurations |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 5분 동안의 커밋 지속 시간 중 99번째 백분위가 250ms보다 클 경우 \(backend commit: 디스크에 대한 최근 변경 사항의 증분 스냅 샷의 커밋.\) |
| 조치 사항 | ETCD 메트릭 문서\(https://github.com/coreos/etcd/blob/master/Documentation/metrics.md\)에 따르면 디스크에 문제가 있을 경우 발생한다고 함. |

* #### General

| 알람 ID | **GEN-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | TargetDown |
| 지속 시간 | 10분 |
| 발생 조건 | 메트릭 수집 작업이 안 될 경우 발생. 어떤 작업이 실패인지 표시됨. |
| 조치 사항 | Prometheus의 로그 및 해당 작업에 해당하는 Pod의 로그 및 이벤트를 확인한다. |

| 알람 ID | **GEN-002** |
| :--- | :--- |
| 중요도 | ~~none~~ |
| 알람 이름 | DeadMansSwitch |
| 지속 시간 | 즉시 |
| 발생 조건 | DeadMansSwitch 알림. |
| 조치 사항 | 해당 알람은 사용자에게 통지되지 않습니다. |

| 알람 ID | **GEN-003** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | TooManyOpenFileDescriptors |
| 지속 시간 | 10분 |
| 발생 조건 | file descriptor 사용율이 95%이상 일때 발생 |
| 조치 사항 | 노드의 Limit값을 변경한다.\(노드의 재시작 필요\) |

| 알람 ID | **GEN-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | FdExhaustionClose |
| 지속 시간 | 10분 |
| 발생 조건 | 단순회귀분석\(simple linear regression\)을 이용하여 4시간 이내에 file descriptor 고갈이 예측될 경우 발생 |
| 조치 사항 | 해당 Pod의 로그 및 이벤트를 확인한다. 필요한면 노드의 Limit값을 변경한다.\(노드의 재시작 필요\) |

| 알람 ID | **GEN-005** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | FdExhaustionClose |
| 지속 시간 | 10분 |
| 발생 조건 | 단순회귀분석\(simple linear regression\)을 이용하여 1시간 이내에 file descriptor 고갈이 예측될 경우 발생 |
| 조치 사항 | 해당 Pod의 로그 및 이벤트를 확인한다. 필요한면 노드의 Limit값을 변경한다.\(노드의 재시작 필요\) |

* #### Kube-ApiServer

| 알람 ID | **KAS-001** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SApiserverDown |
| 지속 시간 | 5분 |
| 발생 조건 | kube-apiserver 메트릭 수집이 안 될 경우 발생 |
| 조치 사항 | Prometheus의 로그 및 kube-apiserver의 로그와 이벤트를 확인한다. 필요할 경우, Pod를 재시작한다. |

| 알람 ID | **KAS-002** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | K8SApiServerLatency |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 10분 동안의 요청 대기 시간 중 99번째 백분위가 1s보다 클 경우 발생 |
| 조치 사항 | 계속 발생할 경우, 마스터 노드를 증설한다. |

* #### Kube-ControllerManager

| 알람 ID | **KCM-001** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SControllerManagerDown |
| 지속 시간 | 5분 |
| 발생 조건 | kube-controller-manager 메트릭 수집이 안 될 경우 발생 |
| 조치 사항 | Prometheus의 로그 및 kube-controller-manager의 로그와 이벤트를 확인한다. 필요할 경우, Pod를 재시작한다. |

* #### Kube-Scheduler

| 알람 ID | **KSC-001** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SSchedulerDown |
| 지속 시간 | 5분 |
| 발생 조건 | kube-scheduler 메트릭 수집이 안 될 경우 발생 |
| 조치 사항 | Prometheus의 로그 및 kube-scheduler의 로그와 이벤트를 확인한다. 필요할 경우, Pod를 재시작한다. |

* #### Kube-State-Metrics

| 알람 ID | **KSM-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | DeploymentGenerationMismatch |
| 지속 시간 | 15분 |
| 발생 조건 | Deployment에 설정한 generation과 수집된 generation이 다를 경우 발생 |
| 조치 사항 | Deployment의 로그 및 이벤트를 확인한다. 필요하면 Deployment를 재배포한다. |

| 알람 ID | **KSM-002** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | DeploymentReplicasNotUpdated |
| 지속 시간 | 15분 |
| 발생 조건 | Deployment에 설정한 replica 개수와 변경되거나 available 상태의 replica 개수가 다를 경우 발생 |
| 조치 사항 | Deployment 수정 사항이 반영이 안 된 상태이므로 Deployment 및 Pod의 로그 및 이벤트를 확인한다. |

| 알람 ID | **KSM-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | DaemonSetRolloutStuck |
| 지속 시간 | 15분 |
| 발생 조건 | DaemonSet에 상태가 Ready가 아닌 Pod가 있을 경우 발생 |
| 조치 사항 | 해당 Daemonset과 Pod의 로그 및 이벤트를 확인한다. |

| 알람 ID | **KSM-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | K8SDaemonSetsNotScheduled |
| 지속 시간 | 10분 |
| 발생 조건 | DaemonSet에 실행되어 할 Pod 개수 보다 실행중인 Pod 개수가 작을 경우 발생 |
| 조치 사항 | 해당 Daemonset과 Pod의 로그 및 이벤트를 확인한다. 배포가 안 된 노드가 정상인지 확인한다. 마스터 노드가 격리된 경우, Daemonset에 toleration 설정이 되어 있는지 확인한다. |

| 알람 ID | **KSM-005** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | DaemonSetsMissScheduled |
| 지속 시간 | 10분 |
| 발생 조건 | DaemonSet에 잘못 스케쥴된 Pod가 생겼을 경우 발생 |
| 조치 사항 | 해당 Daemonset과 Pod의 로그 및 이벤트를 확인한다. |

| 알람 ID | **KSM-006** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | PodFrequentlyRestarting |
| 지속 시간 | 10분 |
| 발생 조건 | 최근 1시간 동안 Pod 재시작 횟수가 5회 이상일 경우 발생 |
| 조치 사항 | 해당 Pod의 로그 및 이벤트를 확인한다. 필요하면 Pod를 재시작한다. |

* #### Kubelet

| 알람 ID | **KBL-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | K8SNodeNotReady |
| 지속 시간 | 1시간 |
| 발생 조건 | Node 상태가 Ready가 아닐 경우 발생 |
| 조치 사항 | 해당 노드의 상태 및 이벤트를 확인한다. ssh를 통해 노드에 접속하여 kubelet의 상태를 확인한다. |

| 알람 ID | **KBL-002** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SManyNodesNotReady |
| 지속 시간 | 1분 |
| 발생 조건 | 클러스터 전체에서 Node 상태가 Ready가 아닌 비율이 20%이상일 경우 발생 |
| 조치 사항 | 해당 노드들의 상태 및 이벤트를 확인한다. ssh를 통해 노드에 접속하여 kubelet의 상태를 확인한다. |

| 알람 ID | **KBL-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | K8SKubeletDown |
| 지속 시간 | 1시간 |
| 발생 조건 | 클러스터 전체에서 3%이상의 kubelet 메트릭 수집이 안 될 경우 발생 |
| 조치 사항 | Prometheus의 로그 및 해당 노드의 상태 및 이벤트를 확인한다. ssh를 통해 노드에 접속하여 kubelet의 상태를 확인한다. |

| 알람 ID | **KBL-004** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SKubeletDown |
| 지속 시간 | 1시간 |
| 발생 조건 | 클러스터 전체에서 10%이상의 kubelet 메트릭 수집이 안 될 경우 발생 |
| 조치 사항 | Prometheus의 로그 및 해당 노드들의 상태 및 이벤트를 확인한다. ssh를 통해 노드에 접속하여 kubelet의 상태를 확인한다. |

| 알람 ID | **KBL-005** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | K8SKubeletTooManyPods |
| 지속 시간 | 즉시 |
| 발생 조건 | Node의 배치된 Pod의 수가 100개가 넘으면 발생.\(제한값은 110\) |
| 조치 사항 | 제한값에 도달할 경우, 더 이상 Pod 생성이 안됨. 다른 노드들의 상태도 같이 확인하여 여유가 없을 경우, 노드를 증설한다. |

* #### Node

| 알람 ID | **NOD-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | NodeExporterDown |
| 지속 시간 | 10분 |
| 발생 조건 | NodeExporter 메트릭 수집이 안 될 경우 발생 |
| 조치 사항 | Prometheus의 로그 및 NodeExporter의 로그와 이벤트를 확인한다. 필요할 경우, Pod를 재시작한다. |

| 알람 ID | **NOD-002** |
| :--- | :--- |
| 중요도 | **critical** |
| 알람 이름 | K8SNodeOutOfDisk |
| 지속 시간 | 즉시 |
| 발생 조건 | Node 상태가 OutOfDisk일 때 발생 |
| 조치 사항 | 해당 노드의 디스크를 증설한다. |

| 알람 ID | **NOD-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | K8SNodeMemoryPressure |
| 지속 시간 | 즉시 |
| 발생 조건 | Node 상태가 MemoryPressure일 때 발생 |
| 조치 사항 | 해당 노드의 메모리를 증설한다. |

| 알람 ID | **NOD-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | K8SNodeDiskPressure |
| 지속 시간 | 즉시 |
| 발생 조건 | Node 상태가 DiskPressure일 때 발생 |
| 조치 사항 | 노드에서 로그, 미사용 dodkcer image, pv backup 등 디스크 공간을 확보한다. 계속 발생할 경우, 해당 노드의 디스크를 증설한다. |

| 알람 ID | **NOD-005** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | NodeCPUUsage |
| 지속 시간 | 30분 |
| 발생 조건 | Node 최근 5분간 평균 CPU 사용량이 90%를 넘을 경우 발생 |
| 조치 사항 | 해당 노드의 CPU를 증설한다. |

| 알람 ID | **NOD-006** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | NodeMemoryUsage |
| 지속 시간 | 30분 |
| 발생 조건 | Node Memory 사용량이 90%를 넘을 경우 발생 |
| 조치 사항 | 해당 노드의 메모리를 증설한다. |

* #### Prometheus

| 알람 ID | **PRM-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | PrometheusFailedReload |
| 지속 시간 | 10분 |
| 발생 조건 | Prometheus의 설정 변경시, 설정 다시읽기 작업 실패시 발생 |
| 조치 사항 | 해당 Pod의 로그를 확인하여 ConfigMap의 설정 오류를 수정한다. |

* #### Cocktail

| 알람 ID | **CKT-001** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | PvLowRequestDisk |
| 지속 시간 | 30분 |
| 발생 조건 | PV가 요청한 디스크의 크기 대비 사용량이 80%가 넘으면 발생 |
| 조치 사항 | PV의 크기를 늘린다. 단, 서버를 재배포 해야함. |

| 알람 ID | **CKT-002** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | PvLowTotalDisk |
| 지속 시간 | 30분 |
| 발생 조건 | PV가 마운트된 디스크의 크기 대비 사용량이 80%가 넘으면 발생 |
| 조치 사항 | 마운트된 디스크의 상태를 확인하고 필요하면 디스크를 증설한다. 미사용 PV를 제거한다. |

| 알람 ID | **CKT-003** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | PodCPULimitUsage |
| 지속 시간 | 30분 |
| 발생 조건 | Resource Limit 설정값 대비 CPU 사용율이 90%가 넘으면 발생 |
| 조치 사항 | 계속 발생할 경우, Deployment의 CPU Limit 값 변경 |

| 알람 ID | **CKT-004** |
| :--- | :--- |
| 중요도 | warning |
| 알람 이름 | PodMemoryLimitUsage |
| 지속 시간 | 30분 |
| 발생 조건 | Resource Limit 설정값 대비 Memory 사용율이 90%가 넘으면 발생 |
| 조치 사항 | 계속 발생할 경우, Deployment의 Memory Limit 값 변경 |



