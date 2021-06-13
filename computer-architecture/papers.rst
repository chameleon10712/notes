Papers
========



Osiris: A Low-Cost Mechanism to Enable Restoration of Secure Non-Volatile Memories
--------------------------------------------------------------------------------------


Asynchronous DRAM Refresh（ADR）

針對掉電保護，Intel 提出了 Asynchronous DRAM Refresh（ADR）的概念，負責在掉電時把 Data in-flight 回寫到 PMem 上，保證數據持久性。目前 ADR 只能保護 iMC 里的 Write Pending Queue（WPQ）和 PMem 的緩存中的數據，但無法保護 CPU Cache 中的數據。在 Intel 下一代的產品中，將推出 Enhanced ADR（eADR），可以進一步做到對 CPU Cache 中數據的保護。

|

Initialization Vector (IV) 初始化向量


初始化向量（IV，Initialization Vector）是許多工作模式中用於將加密隨機化的一個位塊，由此即使同樣的明文被多次加密也會產生不同的密文，避免了較慢的重新產生金鑰的過程。

初始化向量與金鑰相比有不同的安全性需求，因此IV通常無須保密，然而在大多數情況中，不應當在使用同一金鑰的情況下兩次使用同一個IV。對於CBC和CFB，重用IV會導致泄露明文首個塊的某些資訊，亦包括兩個不同訊息中相同的字首。對於OFB和CTR而言，重用IV會導致完全失去安全性。另外，在CBC模式中，IV在加密時必須是無法預測的；特別的，在許多實現中使用的產生IV的方法，例如SSL2.0使用的，即採用上一個訊息的最後一塊密文作為下一個訊息的IV，是不安全的[


|

Message authentication code (MAC)

在密碼學中，訊息鑑別碼（英語：Message authentication code，縮寫為MAC），又譯為訊息認證碼、檔案訊息鑑別碼、消息認證碼、資訊認證碼，是經過特定演算法後產生的一小段資訊，檢查某段訊息的完整性，以及作身分驗證。它可以用來檢查在訊息傳遞過程中，其內容是否被更改過，不管更改的原因是來自意外或是蓄意攻擊。同時可以作為訊息來源的身分驗證，確認訊息的來源。

訊息鑑別碼的演算法中，通常會使用帶密鑰的雜湊函式（HMAC），或者塊密碼的帶認證工作模式（如GCM，CCM）。

|

.. image:: https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/MAC.svg/661px-MAC.svg.png


Reference

- `2020 存儲技術熱點與趨勢總結 <https://kknews.cc/digital/lv6gjyz.html>`_









