Normal Form
=============



1 NF 
------

第一正規化

- 排除 ``重複群``
- 每個欄位的值都只能是單一值

|

2 NF
-----

第二正規化

- 規則是要求資料表裡的所有資料都要和該資料表的鍵（主鍵與候選鍵）有 ``完全依賴關係``


- 一個資料表符合第二正規化若且唯若

  |
  - 它符合第一正規化 
  - 所有非鍵欄位都不能是候選鍵非全體欄位的函式


|


3 NF
-----

第三正規化

- 要求所有非主鍵屬性都只和候選鍵 (candidate key) 有相關性，也就是說非主鍵屬性之間應該是獨立無關的

.. image:: https://i.imgur.com/szPOKYX.png



