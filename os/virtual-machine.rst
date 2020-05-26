Virtual Machine
=================

- purpose and types of virtualization
- virtual file systems
- Hypervisors



Terms
------

- virtualization

  - 虛擬化是透過軟體以虛擬形式呈現物件的過程，例如虛擬的應用程式、伺服器、儲存裝置和網路。無論企業屬於何種規模，虛擬化都是降低 IT 開銷、提高效率和靈活性的最有效方式

|

- virtual machine

  - VM 是一種嚴密隔離且內含作業系統和應用程式的軟體容器。各個虛擬機都具備完整功能，而且能完全獨立。將數個虛擬機放入同一部電腦後，只要使用一部實體伺服器 (或稱「主機」)，就能執行數個作業系統和應用程式。
  



|


Hypervisor
=============


Hypervisor

- A hypervisor, also known as a virtual machine monitor, is a process that creates and runs virtual machines (VMs). A hypervisor allows one host computer to support multiple guest VMs by virtually sharing its resources, like memory and processing. 

- ex.

  - Xen
  - VMware ESXi


|

KVM
======

Kernel-Based Virtual Machine 基於核心的虛擬機器，是Linux核心的一個可載入模組，通過呼叫Linux本身核心功能，實現對CPU的底層虛擬化和記憶體的虛擬化，使Linux核心成為虛擬化層，需要x86架構的，支援虛擬化功能的硬體支援（比如Intel-VT，AMD-V），是一種全虛擬化架構。

|

Cloud Services
=================

- `雲端服務(Cloud Services)介紹 <https://scitechvista.nat.gov.tw/c/sBwv.htm>`_
- `公有雲、私有雲、以及混合雲的差異與優勢 <https://oosga.com/thinking/public-private-and-hybrid-cloud/>`_

|

OpenStack
============

OpenStack 組合開放原始碼工具（又稱專案），採用集中式虛擬資源來建構和管理私有雲 和 公共雲。其中的六個專案負責處理運算、網路、儲存、身份識別和映像服務等核心雲端運算服務，而其它的十幾個選擇性專案則可結合在一起，以建構獨特且可供部署的雲端服務。

中，儲存、CPU 和 RAM 等資源是擷取自各種特定供應商方案，並由虛擬器管理器拆解後，再視需求來分配。OpenStack 則利用一套一致性的應用程式介面（API）將這些虛擬資源進一步擷取出來，再放進分離的資源池中，以驅動與管理人員和使用者直接互動的標準雲端運算工具。



`[ref] <https://www.redhat.com/zh-tw/topics/openstack>`_

|

Kubernetes
============

Kubernetes，又稱為k8s（首字母為k、首字母與尾字母之間有8個字符、尾字母為s，所以簡稱k8s）或者簡稱為"kube" ，是一種可自動實施Linux容器操作的開源平台。它可以幫助用戶省去應用容器化過程的許多手動部署和擴展操作。也就是說，您可以將運行Linux容器的多組主機聚集在一起，由Kubernetes幫助您輕鬆高效地管理這些集群。而且，這些集群可跨公共雲、私有云或混合雲部署主機。因此，對於要求快速擴展的雲原生應用而言（例如借助Apache Kafka進行的實時數據流處理），Kubernetes是理想的託管平台。


`[ref] <https://www.redhat.com/zh/topics/containers/what-is-kubernetes>`_

|

Docker
=========

Docker容器 與虛擬機器類似，但原理上，容器是將作業系統層虛擬化，虛擬機器則是虛擬化硬體，因此容器更具有可攜式性、高效地利用伺服器。 容器更多的用於表示 軟體的一個標準化單元。由於容器的標準化，因此它可以無視基礎設施（Infrastructure）的差異，部署到任何一個地方。另外，Docker也為容器提供更強的業界的隔離相容

Swarm Mode
------------

當說到 Docker Swarm 時，一般是指單獨專案 Docker Swarm。而在Docker 1.12時，將swarm mode整合到Docker 引擎中，可用Docker引擎API 和 CLI 命令直接使用。官方推薦用戶使用整合的 swarm mode。

Swarm Mode 內建 kv 儲存功能，提供了眾多的新特性，比如：具有容錯能力的去中心化設計、內建服務發現、負載均衡、路由網格、動態伸縮、滾動更新、安全傳輸等。使得 Docker 原生的 Swarm 叢集具備與 Mesos、Kubernetes 競爭的實力。

cluster(中文：叢集)，Docker將叢集定義為：一群共同作業並提供高可用性的機器。swarm(中文：群)，是指一個叢集的Docker引擎以swarm mode形式執行。swarm mode是指Docker引擎內嵌的叢集管理和編排功能。當你初始化了一個swarm(cluster)或者將節點加入一個swarm時，其Docker引擎就會以swarm mode的形式執行。

`[ref] <https://zh.wikipedia.org/wiki/Docker>`_



Docker & K8s
==============

- `知乎 <https://zhuanlan.zhihu.com/p/53260098>`_
- `Redhat - Docker <https://www.redhat.com/zh/topics/containers/what-is-docker>`_
- `Blog <https://blog.toright.com/posts/6416/kubernetes-intro.html>`_
- `Google slide - Container <https://speakerdeck.com/jbeda/containers-at-scale>`_

|

Virtualization
=================

按虛擬的物件分類

- Hardware virtualization
- Virtual machine
- ...






按照抽象程度分類

- Instruction Set Architecture Level
|

- Hardware Abstraction Level 

  - 硬體抽象層等級的虛擬化
  - VMware ESXi、Hyper-V


- Operating System Level

  - 作業系統等級的虛擬化
  - Docker、LXC、OpenVZ
|
  
- Programming Language Level

- Library Level

  - Wine




