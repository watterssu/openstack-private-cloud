# OpenStack Private Cloud Lab

> **Kolla-Ansible을 활용해 OpenStack을 직접 배포하고,  
> 퍼블릭 클라우드 뒤에서 동작하는 인프라 구조를 이해하기 위한 Private Cloud 구축 프로젝트**

Cloud Club 10기에서 진행하는  
**「퍼블릭 클라우드 뒤에는 뭐가 있을까: Kolla-Ansible로 OpenStack 직접 배포하기」**  
스터디의 학습 및 실습 기록임.

AWS와 같은 퍼블릭 클라우드를 사용하는 것에서 나아가,  
직접 OpenStack 환경을 구축하며 **Compute · Network · Storage · Virtualization이 실제로 어떻게 연결되는지** 학습하는 것을 목표로 함.

---

## Goals

- OpenStack 기반 Private Cloud 직접 구축
- Kolla-Ansible을 활용한 OpenStack 배포 자동화 이해
- Nova · Neutron · Keystone · Glance · Cinder 구조 이해
- VM Provisioning 과정 및 Service 간 통신 구조 이해
- KVM · QEMU · libvirt 기반 Virtualization Layer 이해
- OpenStack Instance 생성 및 Floating IP를 통한 SSH 접속
- 구축 과정에서 발생하는 장애를 Log 기반으로 분석하고 해결

최종 목표는 다음과 같음.

```bash
ssh cirros@<floating-ip>
```
직접 구축한 OpenStack 환경에서 Instance를 생성하고 외부에서 SSH 접속하는 것을 최종 목표로 함

---

## Tech Stack

**Cloud Platform**

`OpenStack` `Kolla-Ansible`

**Virtualization**

`KVM` `QEMU` `libvirt`

**Infrastructure**

`Linux` `Docker` `Ansible`

**OpenStack Infrastructure**

`MariaDB` `RabbitMQ` `Memcached`

**Networking**

`Virtual Network` `Subnet` `Router` `Security Group` `Floating IP`

---

## What I Focus On

단순히 OpenStack 배포에 성공하는 것보다 **각 컴포넌트가 왜 필요한지, 실제 요청이 어떤 계층을 거쳐 처리되는지 이해하는 것**에 중점을 둠.

### Architecture

- 각 OpenStack 컴포넌트가 어떤 역할을 담당하는가?
- 서비스들은 REST API와 Message Queue를 어떻게 활용하는가?
- VM 생성 요청은 어떤 컴포넌트를 거쳐 처리되는가?

### Virtualization

- Nova와 Hypervisor는 어떻게 연결되는가?
- libvirt · QEMU · KVM은 각각 어떤 역할을 담당하는가?
- 실제 VM은 어느 계층에서 생성되는가?

### Troubleshooting

- 장애가 발생한 계층은 어디인가?
- 어떤 로그와 명령어로 원인을 확인했는가?
- Root Cause는 무엇인가?
- 어떻게 해결했으며 재발을 방지할 수 있는가?

---

## Repository Structure

```text
openstack-private-cloud/
│
├── README.md
│
├── docs/
│   ├── 01-openstack-overview.md
│
├── images/
│   ├── openstack-architecture.png
│   └── openstack-vm-flow.png
│
├── scripts/
│
└── troubleshooting/
```

---

## Activity

**Cloud Club 10th**

- Study: `퍼블릭 클라우드 뒤에는 뭐가 있을까: Kolla-Ansible로 OpenStack 직접 배포하기`
- Topic: `OpenStack · Private Cloud · Virtualization`
- Season: `Season 1`
- Period: `2026.08 ~ 2026.10`
