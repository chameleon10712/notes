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


- `ref <https://www.itread01.com/content/1542697143.html>`_




