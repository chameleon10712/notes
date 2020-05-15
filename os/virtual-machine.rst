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

- 一種執行在基礎物理伺服器和作業系統之間的中間軟體層,可允許多個作業系統和應用共享硬體。也可叫做VMM（ virtual machine monitor ），即虛擬機器監視器。

- Hypervisors是一種在虛擬環境中的“元”作業系統。他們可以訪問伺服器上包括磁碟和記憶體在內的所有物理裝置。Hypervisors不但協調著這些硬體資源的訪問，而且在各個虛擬機器之間施加防護。當伺服器啟動並執行Hypervisor時，它會載入所有虛擬機器客戶端的作業系統同時會分配給每一臺虛擬機器適量的記憶體，CPU，網路和磁碟。

|

KVM
======

Kernel-Based Virtual Machine 基於核心的虛擬機器，是Linux核心的一個可載入模組，通過呼叫Linux本身核心功能，實現對CPU的底層虛擬化和記憶體的虛擬化，使Linux核心成為虛擬化層，需要x86架構的，支援虛擬化功能的硬體支援（比如Intel-VT，AMD-V），是一種全虛擬化架構。


|

--

Reference

- `IT Read <https://www.itread01.com/content/1542697143.html>`_
- `VMware <https://www.vmware.com/tw/solutions/virtualization.html>`_




