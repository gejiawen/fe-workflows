# 基于milestone的需求管理及分解

## 说明

**需求管理** （ *项目管理* ）其实是一个很大的topic，在这里，我们不对其作深入的探讨，只针对我们自己的项目，结合版本控制系统说一些具体的做法。

## 参考文章

*TODO*

## ChangeLog

- 2014/9/24
    - create
- 2014/9/26
    - update "milestone分类与管理"

## 目录

- 正文
    - 1 milestone的建议
    - 2 需求的分解
    - 3 创建需求点issue
    - 4 需求点的实现及变更
    - 5 milestone分类与管理

## 正文

### 1 milestone的建立

当完成一个需求审批时，就意味着一个新的milestone即将被建立。

一个milestone应该包含如下要素，

- 标题，表示本次迭代的核心内容是什么（也可以使用日期来表述，表示日常的迭代维护，比如 *八月迭代* ，*九月迭代* ）
- deadline，每个迭代周期都会有一个确定的时间点
- issues，每一个迭代的具体内容都是由一个个issue来表现

具体的做法，

在gitlab的 *issues* 中，选择 *Milestones* 功能项，即可建立milestone，创建时，应该给出必要的description信息，一般为本次milestone迭代的简要内容。

### 2 需求的分解

milestone确立后，接下来的工作即是需求分解。其实就是抽象出本次迭代具体要做什么事情。

需求分解之后，我们将会得到一系列的需求点（ *feature point* ），之后针对各个需求点我们在 *issues* 中提出issue，并指定 *assignee* 。这样每一个需求点都和相应的rd建立了联系。方便接下来的开发工作。

### 3 创建需求点issue

创建feature point issue时，提供一些必要的说明，重要的是指定 *assignee* 和贴上合适的标签。

关于issues的labels，一般在开发阶段有如下几个常用的标签，

- `feature` 标识此issue是一项待实现的功能
- `bug` 标识此issue是一个bug
- `enhancement` 此issue将会描述一些待提升的问题
- `feedback` 此issue内容为用户的反馈

labels最忌讳的就是：取名随意、缺乏管理、数量泛滥

更加详细的内容请参见[issue管理策略](issue-management.md)

### 4 需求点的实现及变更

issue的assignee可以在 *comment* 中给出一些实现过程中遇到的问题以及解决方案，可以 *@someone* 进行讨论等。

当某一个feature point发生变更时，应该在此issue的 *comment* 中进行详细说明，并以 *@someone* 的方式指出所有参与需求变更的人员。

总之，这里可以记录相关过程，以便日后追溯。

### 5 milestone分类与管理

一般而言，每一个迭代周期将会对应一个 *milestone* ，在 *milestone* 中将会承载我们所有的 *issue* 。

当一个迭代的生命周期完结，那么对应的 *milestone* 中的 *issue* 也应该全部都被 *close* ，即，当完成结束一个迭代周期，其 *complete* 应该是 **100%** 。

但是实际的操作中，我们可能会遇到这种情况：某一个 *issue* 由于需求的变更，不再适合被包含在当前的milestone中了。此时我们可以视情况将此 *issue* 移动至适合的 *milestone* 中。

~~此外，像 **用户反馈** 这一类没有明确 *milestone* 归属的 *issue* ，我们创建一个长期的 *milestone* ，叫做 **OPW** （operate per week），意在收集这些不确定的归属的 *issue* 。~~

