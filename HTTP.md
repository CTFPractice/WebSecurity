HTTP
===
## About
全世界最受歡迎的網路應用層協議（Application protocol）。

The most popular internet application protocol all over the world.
![](https://i.imgur.com/tQlcCz6.png)
[`圖片來源`](https://www.ntu.edu.sg/home/ehchua/programming/webprogramming/HTTP_Basics.html)

## HTTP Protocol
瀏覽器（browser）會將網址（URL）轉換成請求信息（request message）後，傳給伺服器（server）。
伺服器收到請求信息後，會從文件目錄下尋找是否有相對應的檔案，並回傳客戶端（client）回應訊息（response message）。

The browser translates the URL into a request message and sends the request message to the server.
After server receive the request message, it maps the file or program to the document directory then send the response message to client.

## HTTP Message
### Request Message
- 請求行 Request Line
```請求方法（request-method） 請求資源（request-URI） HTTP版本（HTTP-version）```
- 請求標頭 Request Headers
`request-header-value1, request-header-value2, ...`
- 斷行字元 CLRF
- 內容主體 Request Body

### Response Message
- 狀態列 Status Line
`HTTP版本（HTTP-version） 狀態碼編號（status-code） 狀態碼文字說明（reason-phrase）`
- 回應標頭 Response Headers
`response-header-value1, response-header-value2, ...`
- 斷行字元 CLRF
- 內容主體 Response Body

## HTTP Specifications
- HTTP/0.9
  - 於1990年發表（已廢止）
  - 由Tim Berners-Lee提出（www支付）
  - 運行模式
    - 用戶端以純文字構成單行命令，發出HTTP的要求（GET /），並以一個換行字元（CRLF）結束要求
    - 伺服器回應HTML文件，還沒有Header的概念
    - 每次執行完Request/Respnse就會自動關閉連線
- HTTP/1.0
  - 瀏覽器於1991到1995年間出現
  - 於1996年發表（RFC 1945）
  - 運行模式 v.s. HTTP/0.9
    - 用戶端可發送多行命令，出現HTTP Message架構
    - 每完成一次Request/Respnse交握就會關閉TCP/IP連線
- HTTP/1.1
  - 於1997年1月發表（RFC 2068）
  - 於1999年6月發布更新版（RFC 2616）
  - 於2014年6月再次更新並將規格文件拆成六份
  - 運行模式 v.s. HTTP/1.0
    - 解決了傳輸效率的問題
    - 新增要求方法
      - OPTIONS, PUT, DELETE, TRACE and CONNECT.
- HTTP/2.0
  - 於2015年5月發布（RFC 7540）
  - 僅針對HTTP/1.1的Message Syntax部分做出強化

## Request Methods
包括GET、HEAD、POST、OPTIONS、PUT、DELETE、TRACE、CONNECT等八種方法。
特定HTTP伺服器還可以擴充自定義方法（如PATCH）。

## Status Code
狀態碼是用以表示回應狀態的3位數字代碼。
- 1xx 參考資訊：請求已被伺服器接收，需要繼續處理
- 2xx 成功：請求已成功被伺服器接收、理解、並接受
- 3xx 重新導向：客戶端需採取進一步的操作才能完成請求
- 4xx 用戶端錯誤：請求含有詞法錯誤或者無法被執行
- 5xx 伺服器錯誤：伺服器在處理某個正確請求時發生錯誤

Status code  is a 3-digit number, which indicates the outcome of the request.
- 1xx Informational：Request has been received, server is continuing the process.
- 2xx Success：The request was successfully received, understood and accepted.
- 3xx Redirection：Further action must be taken in order to complete the request.
- 4xx Client Error：The request contains bad syntax or cannot be understood.
- 5xx Server Error：The server failed to fulfill an apparently valid request.

## Reference
- https://www.ntu.edu.sg/home/ehchua/programming/webprogramming/HTTP_Basics.html
- https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE#.E8.AF.B7.E6.B1.82.E6.96.B9.E6.B3.95