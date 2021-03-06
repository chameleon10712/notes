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

- Initialization Vector (IV) 初始化向量

  初始化向量（IV，Initialization Vector）是許多工作模式中用於將加密隨機化的一個位塊，由此即使同樣的明文被多次加密也會產生不同的密文，避免了較慢的重新產生金鑰的過程。

  初始化向量與金鑰相比有不同的安全性需求，因此IV通常無須保密，然而在大多數情況中，不應當在使用同一金鑰的情況下兩次使用同一個IV。對於CBC和CFB，重用IV會導致泄露明文首個塊的某些資訊，亦包括兩個不同訊息中相同的字首。對於OFB和CTR而言，重用IV會導致完全失去安全性。另外，在CBC模式中，IV在加密時必須是無法預測的；特別的，在許多實現中使用的產生IV的方法，例如SSL2.0使用的，即採用上一個訊息的最後一塊密文作為下一個訊息的IV，是不安全的

|

- 計數器模式（CTR）

  |
  - CTR模式（Counter mode，CM）也被稱為ICM模式（Integer Counter Mode，整數計數模式）和SIC模式（Segmented Integer Counter）
  
  - 與OFB相似，CTR將塊密碼變為串流加密法。它通過遞增一個加密計數器以產生連續的金鑰流，其中，計數器可以是任意保證長時間不產生重複輸出的函式，但使用一個普通的計數器是最簡單和最常見的做法。使用簡單的、定義好的輸入函式是有爭議的：批評者認為它「有意的將密碼系統暴露在已知的、系統的輸入會造成不必要的風險」。目前，CTR已經被廣泛的使用了，由輸入函式造成的問題被認為是使用的塊密碼的缺陷，而非CTR模式本身的弱點。無論如何，有一些特別的攻擊方法，例如基於使用簡單計數器作為輸入的硬體差錯攻擊。

  - CTR模式的特徵類似於OFB，但它允許在解密時進行隨機存取。由於加密和解密過程均可以進行並列處理，CTR適合運用於多處理器的硬體上。


|

- Message authentication code (MAC) 訊息鑑別碼

  在密碼學中，訊息鑑別碼（英語：Message authentication code，縮寫為MAC），又譯為訊息認證碼、檔案訊息鑑別碼、消息認證碼、資訊認證碼，是經過特定演算法後產生的一小段資訊，檢查某段訊息的完整性，以及作身分驗證。它可以用來檢查在訊息傳遞過程中，其內容是否被更改過，不管更改的原因是來自意外或是蓄意攻擊。同時可以作為訊息來源的身分驗證，確認訊息的來源。

  訊息鑑別碼的演算法中，通常會使用帶密鑰的雜湊函式（HMAC），或者塊密碼的帶認證工作模式（如GCM，CCM）。

|

.. image:: https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/MAC.svg/661px-MAC.svg.png


|

|

Error-Correcting Code memory (ECC)


修正錯誤記憶體（英語：Error-Correcting Code memory，縮寫：ECC memory或ECC）指能夠實現錯誤檢查和糾正錯誤技術的記憶體。

在ECC技術出現之前，記憶體中應用最多的另外一種錯誤檢查技術，是奇偶校驗位（Parity）技術。

在數位電路中，最小的資料單位是「位元（bit）」，也叫「位元」。「位元」也是記憶體中的最小單位，它是通過「1」和「0」來表示資料高、低電平訊號。在數字電路中8個連續的位元是一位元組，不帶「奇偶校驗」的記憶體中的每個位元組只有8位元，若它的某一位儲存出了錯誤，就會使其中儲存的相應資料發生改變而導致應用程式發生錯誤。

而帶有「奇偶校驗」的記憶體在每一位元組（8位元）外又額外增加了一位用來進行錯誤檢測。比如一個位元組中儲存了某一數值（1、0、1、0、1、0、1、1），把這每一位相加起來（1＋0＋1＋0＋1＋0＋1＋1=5）。對於偶校驗，若其結果是奇數，校驗位就定義為1，反之則為0；對於奇校驗則相反。當CPU返回讀取儲存的資料時，它會再次相加前8位元中儲存的資料，計算結果是否與校驗位相一致。當CPU發現二者不同時就會試圖糾正這些錯誤。

但奇偶校驗位技術有個缺點，當記憶體查到某個資料位有錯誤時，由於不一定能確定錯誤在哪一個位，也就不一定能修正錯誤。所以帶有奇偶校驗的記憶體的主要功能僅僅是「發現錯誤」，並不能糾正錯誤。

此外，奇偶校驗技術是通過在原來資料位的基礎上增加一個資料位來檢查當前8位元資料的正確性，但隨著資料位的增加，用來檢驗的資料位也成倍增加，就是說當資料位為16位元時它需要增加2位用於檢查，當資料位為32位元時則需增加4位元，依此類推。特別是當資料量非常大時，資料出錯的機率也就越大，對於只能糾正簡單錯誤的奇偶檢驗的方法就顯得力不從心了。正是基於這樣一種情況，錯誤檢查和糾正（Error Checking and Correcting）應運而生了。

ECC與奇偶校驗不同的是，如果資料位是8位元，則需要增加5位來進行ECC錯誤檢查和糾正。資料位每增加一倍，ECC只增加一位核對位元。也就是說當資料位為16位元時ECC位為6位，32位元時ECC位為7位，資料位為64位元時ECC位為8位元，依此類推。在記憶體中ECC能夠容許錯誤，並可以將錯誤自動更正，使系統得以正常的操作，不致因錯誤而中斷。


|

LLC（Last Level Cache）

ex. L3 cache



|

Merkle tree
++++++++++++++

雜湊樹（hash tree；Merkle tree），在密碼學及電腦科學中是一種樹形資料結構，每個葉節點均以資料塊的雜湊作為標籤，而除了葉節點以外的節點則以其子節點標籤的加密雜湊作為標籤 。雜湊樹能夠高效、安全地驗證大型資料結構的內容，是雜湊鏈的推廣形式。


雜湊樹中，雜湊值的求取通常使用諸如SHA-2的加密雜湊函式，但如果只是用於防止非故意的資料破壞，也可以使用不安全的校驗和取得，比如CRC（Cyclic redundancy check，循環冗餘校驗）。

雜湊樹的頂部為頂部雜湊（top hash），亦稱根雜湊（root hash）或主雜湊（master hash）。以從 P2P 網路下載檔案為例：通常先從可信的來源取得頂部雜湊，如朋友告知、網站分享等。得到頂部雜湊後，則整棵雜湊樹就可以通過 P2P 網路中的非受信來源取得。下載得到雜湊樹後，即可根據可信的頂部雜湊對其進行校驗，驗證資料是否完整、是否遭受破壞。


.. image:: https://upload.wikimedia.org/wikipedia/commons/9/95/Hash_Tree.svg





Reference

- `2020 存儲技術熱點與趨勢總結 <https://kknews.cc/digital/lv6gjyz.html>`_
- `[wiki] 訊息鑑別碼 <https://zh.wikipedia.org/wiki/%E8%A8%8A%E6%81%AF%E9%91%91%E5%88%A5%E7%A2%BC>`_
- `[wiki] 區塊加密法工作模式 <https://zh.wikipedia.org/wiki/%E5%88%86%E7%BB%84%E5%AF%86%E7%A0%81%E5%B7%A5%E4%BD%9C%E6%A8%A1%E5%BC%8F>`_
- `[blog] <https://ithelp.ithome.com.tw/articles/10249953>`_
- `[知乎] L1，L2，L3 Cache究竟在哪裡？ <https://zhuanlan.zhihu.com/p/31422201>`_






