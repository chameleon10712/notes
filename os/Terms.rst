Real Time Systems
------------------

`Reference <http://www.csie.ntnu.edu.tw/~swanky/os/chap1.htm#RealTimeSystem>`_


- Def：

  對於工作(job)的完成時間有極為嚴格的要求，若工作未能在規定時間內完成，即算失敗(失效)
  eg.核能安控、軍事防衛、工廠自動化生產系統 etc.

- Real Time System 可分為兩種

  - Hard Real-Time System
   
    - Def:
    
      對工作的完成時間有極嚴格的限制要求
      工作必須在規定的時間內完成，因此sensor data傳送的時間、處理時間、control signal傳輸的時間加總，必須小於規定的時間，也會影響HW的選擇。此外，在此系統中，OS不宜介入太多，以免造成dispatch latency太長，進而影響工作完成時間，所以大部分此類系統無OS或是microkernel OS(僅提供基本功能)
  
  - Soft Real-Time System

    - Def：
    
      需要即時處理的(有即時性的)process具有較高的優先權，且保證
      
      - 高優先權的process必定先於低優先權process完成
      - 優先權值不會有任何改變，直到完成

|


Time Sharing Systems
---------------------
 
 
 
 
Asymmetric Clustering
----------------------




Spooling
---------



