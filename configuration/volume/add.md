### 5.4.1 스토리지 추가

---

볼륨을 추가하여 사용 할 수 있다.

##### **a\) 클러스터 **→** 클러스터 선택.**![](/assets/KR/3.0.0/5.4.1_1.png)

##### b**\) 클러스터 상세화면에서  볼륨 선택**![](/assets/KR/3.0.0/5.4.1_2.png)

##### c\) 클러스터, 이름, 설명, 스토리지 플러그인, 정책, 스토리지 클래스 이름을 차례로 기입한다.![](/assets/KR/3.0.0/5.4.1_3.png)

| **스토리지 등록 정보** | **설명** |
| :--- | :--- |
| 이름 | PV 이름 |
| 설명 | PV 사용자 설명 |
| 유형 | 스리지 유형 (Single, Shared)
| 스토리지 플러그인 | 스토리지 종류\(NFS/NFS Named, EBS, Google Persistent Disk, Azure Disk\) |
| 정책 | PV 사용 정책\(RETAIN/DELETE\) |

| **유형** | **설명** |
| :--- | :--- |
| Single | 워크로드 하나에서만 사용 가능한 스토리 |
| Shared | 워크로드 간에 공유하여 사용 가능한 스토리지 |

| **정책** | **설명** |
| :--- | :--- |
| Retain | PersistentVolumeClaim\(PVC\)가 삭제되도 PersistentVolume\(PV\)안에 데이터가 남는다. 추후 재사용 가능하지만 재사용시 PV를 다시 등록해야 한다. |
| Delete | PVC가 삭제되면서 해당 PV도 함께 삭제된다. |

##### 

##### d\) 사용하는 스토리지 플러그인에 따라 스토리지 클래스와 파라미터 설정.

* ##### NFS 스토리지 플러그인 사용 시![](/assets/KR/3.0.0/5.4.1_4.png)

| 스토리지 플러그인 | **NFS** |
| :--- | :--- |
| 총용량 | 스토리지 총용량(Gb) |
| 정책 | Dynamic 플러그인은 Retain과 Delete 정책을 지원 |
| 스토리지 클래스 이름 | cocktail-nfs\(기본값\) |
| 스토리지 프로비저닝 | 스토리지 프로비저닝 값 입력 |

* **NFS Named 스토리지 플러그인 사용 시**![](/assets/KR/3.0.0/5.4.1_5.png)

| 스토리지 플러그인 | **NFS** Named |
| :--- | :--- |
| 정책 | NFS Named 플러그인은 Retain 단일 정책을 지원 |
| 총용량 | 스토리지 총용량(Gb) |
| server | 스토리지의 IP Address |
| path | mount 경로 |

* **아마존 스토리지 플러그인 사용 시**![](/assets/KR/3.0.0/5.4.1_6.png)

| 스토리지 플러그인 | AWS EBS \(AWS의 스토리지 서비스\) |
| :--- | :--- |
| 정책 | Retain과 Delete 정책을 지원 |
| 스토리지 클래스 이름 | default\(고정값\) |
| type | io1, gp2, sc1, st1을 선택 |

* **구글 스토리지 플러그인 사용 시**![](/assets/KR/3.0.0/5.4.1_7.png)

| 스토리지 플러그인 | Google Persistent Disk \(GCP의 스토리지 서비스\) |
| :--- | :--- |
| 정책 | Retain과 Delete 정책을 지원 |
| 스토리지 클래스 이름 | standard\(기본값\) |
| type | pd-standard, pd-ssd 선택 |

* **Azure 스토리지 플러그인 사용 시**![](/assets/KR/3.0.0/5.4.1_8.png)

| 스토리지 플러그인 | Azure Disk \(Azure의 스토리지 서비스\) |
| :--- | :--- |
| 정책 | Retain과 Delete 정책을 지원 |
| 스토리지 클래스 이름 | default\(기본값\) |
| storageAccount | storageAccount 값 입력 |



