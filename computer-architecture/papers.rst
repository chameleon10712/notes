Papers
========


Asynchronous DRAM Refresh（ADR）

針對掉電保護，Intel 提出了 Asynchronous DRAM Refresh（ADR）的概念，負責在掉電時把 Data in-flight 回寫到 PMem 上，保證數據持久性。目前 ADR 只能保護 iMC 里的 Write Pending Queue（WPQ）和 PMem 的緩存中的數據，但無法保護 CPU Cache 中的數據。在 Intel 下一代的產品中，將推出 Enhanced ADR（eADR），可以進一步做到對 CPU Cache 中數據的保護。




`ref <https://kknews.cc/digital/lv6gjyz.html>`_









