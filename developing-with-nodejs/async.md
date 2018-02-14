### Async/Await

當`async`函式被呼叫時，它會回傳一個[`Promise`](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Global_Objects/Promise)。如果該`async`函式回傳了一個值，`Promise`的狀態將為一個帶有該回傳值的 resolved。如果`async`函式拋出例外或某個值，`Promise`的狀態將為一個帶有被拋出值的 rejected。

async 函式內部可以使用[`await`](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Operators/await)表達式，它會暫停此 async 函式的執行，並且等待傳遞至表達式的 Promise 的解析，解析完之後會回傳解析值，並繼續此 async 函式的執行。

`async/await`函式的目的在於簡化同步操作 promise 的表現，以及對多個`Promise`物件執行某些操作。就像`Promise 類似於具結構性的回呼函式，同樣地，async/await 好比將 generator 與 promise 組合起來。`

