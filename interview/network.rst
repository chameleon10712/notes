Network
=========


apache和nginx的區別
-------------------


nginx 相對apache 的優點：

- 輕量級，同樣起web 服務，比apache 佔用更少的內存及資源
- 抗並發，nginx 處理請求是異步非阻塞的，支持更多的並發連接，而apache 則是阻塞型的，在高並發下nginx 能保持低資源低消耗高性能
- 配置簡潔
- 高度模塊化的設計，編寫模塊相對簡單
- 社區活躍


apache 相對nginx 的優點：

- rewrite ，比nginx 的rewrite 強大
- 模塊超多，基本想到的都可以找到
- 少bug ，nginx 的bug 相對較多
- 超穩定

|

Reference

- `Python Interview <https://github.com/taizilongxu/interview_python#1-%E4%B8%89%E6%AC%A1%E6%8F%A1%E6%89%8B>`_
