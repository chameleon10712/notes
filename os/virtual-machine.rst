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
  - VMware


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

--

Reference

- `IT Read <https://www.itread01.com/content/1542697143.html>`_
- `VMware <https://www.vmware.com/tw/solutions/virtualization.html>`_




