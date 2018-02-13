Promise是一個強大的異步執行流程語法結構，在ES6 Promise標準中，實作內容只有一個建構函式與一個

`then`方法、一個`catch`方法，再加上四個必需以`Promise`關鍵字呼叫的靜態函式，`Promise.resolve`、`Promise.reject`、`Promise.all`、`Promise.race`。

語法介紹頁面只有7頁，內容少之又少。但為何Promise結構不容易被理解？原因在於同步與異步回調函式執行的概念，以及其中很多流程運作需要用另一種方式來思考要如何進行。當然，需要理解的規則也很多。

Promise物件的設計就是針對異步函式的執行結果所設計的，promise物件最後的結果要不然就用一個回傳值來fulfilled\(實現\)，要不然就用一個理由\(錯誤\)來rejected\(拒絕\)。

Link:

[http://eddychang.me/blog/javascript/88-promise-basic-usage.html](http://eddychang.me/blog/javascript/88-promise-basic-usage.html)

