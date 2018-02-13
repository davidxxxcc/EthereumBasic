### assert module

assert模块是Node的内置模块，主要用于断言。如果表达式不符合预期，就抛出一个错误。该模块提供11个方法，但只有少数几个是常用的。

* assert\(\)
  * assert方法接受两个参数，当第一个参数对应的布尔值为true时，不会有任何提示，返回undefined。当第一个参数对应的布尔值为false时，会抛出一个错误，该错误的提示信息就是第二个参数设定的字符串。下面代码不会有任何输出，因为assert方法的第一个参数是true。

  * ```
    // 格式
    assert(value, message)

    // 例子
    var assert = require('assert');

    function add (a, b) {
      return a + b;
    }

    var expected = add(1,2);
    assert( expected === 3, '预期1加2等于3');
    ```





Link:

[http://javascript.ruanyifeng.com/nodejs/assert.html\#toc2](http://javascript.ruanyifeng.com/nodejs/assert.html#toc2)

