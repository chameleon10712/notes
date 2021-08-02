Blob
=======

The Blob object represents a blob, which is a file-like object of immutable, raw data; they can be read as text or binary data, or converted into a ReadableStream so its methods can be used for processing the data.

Blobs can represent data that isn't necessarily in a JavaScript-native format. The File interface is based on Blob, inheriting blob functionality and expanding it to support files on the user's system.

|

Blob(Binary large Object)物件，主要目的是提供可代表及操作與儲存 JavaScript native 以外的格式，
所以能夠讀取binary data，例如利用Blob讀寫照片檔，但其保存的數據是不可改寫的(immutable)。


而我們常用在<input type=file>來拿到的File物件也是一種特殊的Blob物件，其繼承了Blob的屬性。




