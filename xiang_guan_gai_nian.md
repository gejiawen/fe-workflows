# 相关概念

下面将会阐述一些测试中常用的一些概念。

## 测试框架集

所谓**测试框架集**，就是运行测试方方面面内容的一个容器。目前社区里常用的几个测试框架集有[Mocha](http://mochajs.org/)，[Jasmine](http://jasmine.github.io/)，[Karma](http://karma-runner.github.io/)，[Tape](https://github.com/substack/tape/)等。

## 测试套件

所谓**测试套件**（test suite）指的是，一组针对软件规格的某个方面的测试用例。也可以看作，对软件的某个方面的描述（describe）。看下面的一个示例，

```javascript
describe('加法函数的测试', function() {
    // TODO
});
```

上面示例中就是使用`describe`语法声明了一个测试套件。*加法函数的测试*是这个测试套件的名字，回调函数的内容就是此测试套件具体要做的事情。

此外，测试套件是可以嵌套的，比如，

```javascript
describe('四则运算的测试', function() {
    describe('加法测试', function() {
        // TODO
    });
    
    describe('减法测试', function() {
        // TODO
    });
    
    // ...
});
```

## 测试用例

所谓**测试用例**，就是在测试套件中定义的具体测试内容。一般来说测试要尽可能的覆盖各个边界。比如，

```javascript
describe('加法函数的测试', function() {
    it('1 + 1 = 2', function() {
        expect(1 + 1).to.be.equal(2);
    });
    
    it('0 + 0 = 0', function() {
        expect(0 + 0).to.be.equal(0);
    });
    
    // more test case.
});
```

如上所示，`describe`中的`it`语法就是用来声明测试用例的。它的本质其实还是个函数，第一个参数是测试用例的名称，第二个参数是一个回调函数，里面定义了具体的断言逻辑。

那么，示例中的`expect`这样的语法又是啥意思呢？它就是我们接下来要说的测试断言了。


## 断言

何为断言？所谓断言，简单的来说就是**对代码行为的一个预测**。而代码的最终行为要么是符合你的预测，要么就是不符合你的预测。前者意味着断言通过，后者即断言失败，而断言失败将会导致测试用例不通过。

Node.js中内置了一个`assert`模块，这里的是它的[文档](https://nodejs.org/api/assert.html)（中文版文档在[这里](http://nodejs.cn/api/assert.html)）。

现在你应该大概知道断言是怎么一回事了。那么问题又来了，前面的示例中，

```javascript
expect(1 + 1).to.be.equal(2);
```

这样一行代码也叫断言么？怎么跟Node.js提供的内置assert模块的语法不一样呢？

这个问题涉及到一个断言风格的问题。

主流的断言风格有如下几种，每一种断言风格的语法糖都不太一样，

| 断言风格 | 特征 | 说明 | 示例 | 开源库 |
| :--- | :--- | :--- | :--- | :--- |
| **assert** | `assert` | TDD经典的assert方式 | `assert.equal(variable, "value")` | 内置支持, [chai.js](http://chaijs.com/), [better-assert](https://github.com/tj/better-assert) |
| **expect** | `expect` | 在BDD中最为常见，提供链式语法 |  `expect(variable).to.equal("value")` | [expect.js](https://github.com/Automattic/expect.js), [chai.js](http://chaijs.com/) |
| **should** | `should` | 也是一种常用的BDD断言方式 | `variable.should.equal("value")` | [should.js](https://github.com/shouldjs/should.js), [chai.js](http://chaijs.com/), [unexpected](http://unexpected.js.org/) |

从上表中，可以看出[chai.js](http://chaijs.com/)基本上都支持这三种主流的断言风格，所以一般社区里面大家起的新项目都会逐渐转向chai.js。

其实博主最早是使用[should.js](http://shouldjs.github.io/)的，不过还是抵不住`expect`语法所拥有的特性，良好的链式结构以及仿自然语言的语境，无疑更加有吸引力。

关于各个断言库的具体用法这里就不作细述了。
