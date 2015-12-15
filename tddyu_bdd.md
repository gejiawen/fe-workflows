# TDD与BDD

测试是一个很大的话题。什么叫测试？它用用来干啥的？简单来说，软件工程中的测试就是用来保证软件质量的一种手段。

专业点来说，BDD和TDD是软件工程中针对软件测试提出的两种方法论。简单来说，就是两种不同的测试目的。

BDD是**行为驱动的开发**（Behavior-Driven Development）的简称，指的是写出优秀测试的最佳实践的总称。BDD认为，不应该针对代码的实现细节写测试，而是要针对行为写测试。BDD测试的是行为，即软件应该怎样运行。

BDD接口一般提供以下方法，

- `describe()`，声明测试套件
- `it()`，声明测试用例
- `before()`，所有测试用例的前置动作
- `after()`，所有测试用例的后置动作
- `beforeEach()`，每个测试用例的前置动作
- `afterEach()`，每个测试用例的后置动作


TDD是**测试驱动开发**（Test-Driven Development）的简称，它的组织方式是使用测试集（suite）和测试（test）。

每个测试集都有`setup`和`teardown`函数。这些方法会在测试集中的测试执行前执行，它们的作用是为了避免代码重复以及最大限度使得测试之间相互独立。

TDD接口提供的方法如下，

- `suite`：类似BDD中`describe()`
- `test`：类似BDD中`it()`
- `setup`：类似BDD中`before()`
- `teardown`：类似BDD中`after()`
- `suiteSetup`：类似BDD中`beforeEach()`
- `suiteTeardown`：类似BDD中`afterEach()`
- 
