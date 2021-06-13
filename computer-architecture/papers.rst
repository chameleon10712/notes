Papers
========



Osiris: A Low-Cost Mechanism to Enable Restoration of Secure Non-Volatile Memories
--------------------------------------------------------------------------------------



Terms
++++++++

Asynchronous DRAM Refresh（ADR）

針對掉電保護，Intel 提出了 Asynchronous DRAM Refresh（ADR）的概念，負責在掉電時把 Data in-flight 回寫到 PMem 上，保證數據持久性。目前 ADR 只能保護 iMC 里的 Write Pending Queue（WPQ）和 PMem 的緩存中的數據，但無法保護 CPU Cache 中的數據。在 Intel 下一代的產品中，將推出 Enhanced ADR（eADR），可以進一步做到對 CPU Cache 中數據的保護。

|

Block cipher mode of operation 區塊加密法工作模式

密碼學中，區塊密碼的工作模式（mode of operation）允許使用同一個區塊密碼密鑰對多於一塊的資料進行加密，並保證其安全性。區塊密碼自身只能加密長度等於密碼區塊長度的單塊資料，若要加密變長資料，則資料必須先被劃分為一些單獨的密碼塊。通常而言，最後一塊資料也需要使用合適填充方式將資料擴充到符合密碼塊大小的長度。一種工作模式描述了加密每一資料塊的過程，並常常使用基於一個通常稱為初始化向量的附加輸入值以進行隨機化，以保證安全。

工作模式主要用來進行加密和認證。對加密模式的研究曾經包含資料的完整性保護，即在某些資料被修改後的情況下密碼的誤差傳播特性。後來的研究則將完整性保護作為另一個完全不同的，與加密無關的密碼學目標。部分現代的工作模式用有效的方法將加密和認證結合起來，稱為認證加密模式。

雖然工作模式通常應用於對稱加密，它亦可以應用於公鑰加密，例如在原理上對RSA進行處理，但在實用中，公鑰密碼學通常不用於加密較長的資訊，而是使用結合對稱加密和公鑰加密的混合加密方案。

- 歷史和標準化

  最早出現的工作模式，ECB，CBC，OFB和CFB可以追溯到1981年。2001年，NIST修訂了其早先發布的工作模式工作列表，加入了AES，並加入了CTR模式。最後，在2010年1月，NIST加入了XTS-AES，而其餘的可信模式並沒有為NIST所認證。例如CTS是一種密文竊取的模式，許多常見的密碼學執行庫提供了這種模式。

  ECB，CBC，OFB，CFB，CTR和XTS模式僅僅提供了機密性；為了保證加密資訊沒有被意外修改或惡意篡改，需要採用分離的訊息驗證碼，例如CBC-MAC。密碼學社群認識到了對專用的保證完整性的方法的需求，NIST因此提出了HMAC，CMAC和GMAC。HMAC在2002年通過了認證，CMAC在2005年通過，GMAC則在2007年被標準化。


|

Initialization Vector (IV) 初始化向量


初始化向量（IV，Initialization Vector）是許多工作模式中用於將加密隨機化的一個位塊，由此即使同樣的明文被多次加密也會產生不同的密文，避免了較慢的重新產生金鑰的過程。

初始化向量與金鑰相比有不同的安全性需求，因此IV通常無須保密，然而在大多數情況中，不應當在使用同一金鑰的情況下兩次使用同一個IV。對於CBC和CFB，重用IV會導致泄露明文首個塊的某些資訊，亦包括兩個不同訊息中相同的字首。對於OFB和CTR而言，重用IV會導致完全失去安全性。另外，在CBC模式中，IV在加密時必須是無法預測的；特別的，在許多實現中使用的產生IV的方法，例如SSL2.0使用的，即採用上一個訊息的最後一塊密文作為下一個訊息的IV，是不安全的


|

Message authentication code (MAC) 訊息鑑別碼

在密碼學中，訊息鑑別碼（英語：Message authentication code，縮寫為MAC），又譯為訊息認證碼、檔案訊息鑑別碼、消息認證碼、資訊認證碼，是經過特定演算法後產生的一小段資訊，檢查某段訊息的完整性，以及作身分驗證。它可以用來檢查在訊息傳遞過程中，其內容是否被更改過，不管更改的原因是來自意外或是蓄意攻擊。同時可以作為訊息來源的身分驗證，確認訊息的來源。

訊息鑑別碼的演算法中，通常會使用帶密鑰的雜湊函式（HMAC），或者塊密碼的帶認證工作模式（如GCM，CCM）。

|

.. image:: https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/MAC.svg/661px-MAC.svg.png


Reference

- `2020 存儲技術熱點與趨勢總結 <https://kknews.cc/digital/lv6gjyz.html>`_
- `[wiki] 訊息鑑別碼 <https://zh.wikipedia.org/wiki/%E8%A8%8A%E6%81%AF%E9%91%91%E5%88%A5%E7%A2%BC>`_
- `[wiki] 區塊加密法工作模式 <https://zh.wikipedia.org/wiki/%E5%88%86%E7%BB%84%E5%AF%86%E7%A0%81%E5%B7%A5%E4%BD%9C%E6%A8%A1%E5%BC%8F>`_








