=====================
		Mail		
=====================


MIME  多用途網際網路郵件擴展（MIME，Multipurpose Internet Mail Extensions）
是一個網際網路標準，它擴展了電子郵件標準，使其能夠支援:

- 非ASCII字符文本；
- 非文本格式附件（二進位、聲音、圖像等）；
- 由多部分（multiple parts）組成的消息體；
- 包含非ASCII字符的頭信息（Header information）。
https://zh.wikipedia.org/wiki/%E5%A4%9A%E7%94%A8%E9%80%94%E4%BA%92%E8%81%AF%E7%B6%B2%E9%83%B5%E4%BB%B6%E6%93%B4%E5%B1%95


MUA ( Mail User Agent )   &  MTA ( Mail Transport Agent )
	http://www.weithenn.org/2009/04/mail.html

Mail eXchanger（MX）
	http://www.synnex.com.tw/asp/fae_qaDetail.asp?group=&parent=&seqno=17451



IMAP ( Internet Message Access Protocol ) 互動郵件存取設定
	
	是一個應用層協定，用來從本地郵件用戶端（如Microsoft Outlook、Outlook Express、Foxmail、Mozilla Thunderbird）存取遠端伺服器上的郵件。



POP3 ( Post Office Protocol - Version 3 ) 郵局協定

	POP支援離線郵件處理。其具體過程是：郵件傳送到伺服器上，電子郵件用戶端呼叫郵件客戶機程式以連線伺服器，並下載所有未閱讀的電子郵件。這種離線存取模式是一種儲存轉發服務，將郵件從郵件伺服器端送到個人終端機器上，一般是PC機或MAC。一旦郵件傳送到PC機或MAC上，郵件伺服器上的郵件將會被刪除。但目前的POP3郵件伺服器大都可以「只下載郵件，伺服器端並不刪除」，也就是改進的POP3協定


SASL 
	簡單認證與安全層 (SASL) 
		是一個在網路協定中用來認證和資料加密的構架。它把認證機制從程式中分離開, 理論上使用SASL的程式協定都可以使用SASL所支援的全部認證機制。認證機制可支援代理認證, 這讓一個用戶可以承擔另一個用戶的認證。 SASL同樣提供資料安全層，這提供了資料完整驗證和資料加密。 DIGEST-MD5 提供了資料加密層，這是機制中的一個例子。支援SASL的應用程式通常也支援 傳輸層安全 (TLS) 作為對SASL提供的服務的補充。


SPF   ( Sender Policy Framework ) 
	發件人策略框架
		是一個電子郵件驗證系統，目的是解決電子郵件偽造。
		SPF允許管理員設定一個DNS TXT記錄或SPF記錄設定傳送郵件伺服器的IP範圍
	
	用途
		SPF 記錄的用途是阻止垃圾郵件發件人傳送假冒您的域中的「發件人」位址的電子郵件。收件人可以參考 SPF 記錄來確定號稱來自您的域的郵件是否來自授權郵件伺服器。對於大內送流量備援容錯機制流的郵件服務商，鑑別傳送者的SPF記錄有助於抵禦垃圾郵件給接收者帶來的騷擾。

	原理
		郵件接收方的收件伺服器在接受到郵件後，首先檢查域名的SPF記錄，來確定發件人的IP位址是否被包含在SPF記錄裡面，如果在，就認為是一封正確的郵件，否則會認為是一封偽造的郵件進行退回。
		SPF 記錄允許郵件系統管理員指定哪些郵件伺服器可以使用該域名來傳送郵件，接收伺服器會在收到郵件時驗證發件人在 SMTP 對談中執行 MAIL FROM 命令時的郵件位址是否與域名 SPF 記錄中所指定的源 IP 符合，以判斷是否為發件人域名偽造


DKIM（DomainKeys Identified Mail）





