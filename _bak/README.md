# 全端开发流程的探索

## 说明

这里将会进行一些关于（前端？全端？）开发流程方面的探索，比如，

- git工作流模型
- issue管理
- 基于milestone的需求管理及分解
- 接口文档规范及写作
- ...

这里的文章都是初稿，肯定有许多的不足及有待提升之处。请在 [new issue](http://gitlab.baidu.com/scloud-fe/workflows/issues/new) 给出你的建议或者在 [issue list](http://gitlab.baidu.com/scloud-fe/workflows/issues) 进行讨论。

提issue时，请遵循以下格式，

**[哪篇文章][何种问题]标题**

如：

- [git工作流模型][建议]dev开支可以改成develop分支
- [git工作流模型][质疑]dev开支采用简写有利缩短分支名
- [git工作流模型][投票]dev vs develop

同时，为issue贴上合适的 *labels* 是一个好习惯！

## 参考文章

*TODO*

## ChangeLog

- 2014/9/18
    - create
- 2014/9/24
    - update contents
    - update header description
    - create [requirements-base-on-milestone.md](requirements-base-on-milestone.md)
    - update [interface-document-writing](interface-document-writing.md)

## 目录

- 正文
    - 1 git工作流模型
    - 2 基于milestone的需求管理及分解
    - 3 issue管理策略
    - 4 接口文档规范及协作
    - 5 前后端开发的分离与协作

## 正文

### 1 git工作流模型

我们这里一般采用`git`作为版本控制工具。我们抽象了两种不同复杂度的工作流模型，如下，

- [一种稍微复杂](git-branch.md)
- [一种稍微简单](git-branch-2.md)

经讨论，web这边将会采用第二种模型。

### 2 基于milestone的需求管理及分解

[here](requirements-base-on-milestone.md)

### 3 issue管理策略

[here](issue-management.md)


### 4 接口文档规范及写作

[here](interface-document-writing.md)

### 5 前后端开发的分离与协作

*TODO*
