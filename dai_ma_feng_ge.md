# 代码风格

本部分将按照javascript，css，html这三种语法来分别描述。

## Javascript

| 条目 | 说明 |
| :--- | :--- |
| 文件 | 使用无 BOM 的 UTF-8 编码 |
| 缩进 | 使用 4 个空格做为一个缩进层级，不允许使用 2 个空格 或 tab 字符。 |
| 空格 | 二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格。 |
| 分号 | 不得省略语句结束的分号 |
| 命名 | 变量采用小驼峰，常量全大写，类采用大驼峰 |
| 文档化注释 | 建议添加文档化注释 |
| 变量声明 | 变量在使用前总是使用`var`声明，且即用即声明 |
| `===`，`!==` | 总是使用`===`，`!==`进行判断 |
| 字面量 | 尽量使用字面量的数组，对象，字符串 |

更多内容可参考：[SPEC:Javascript](https://github.com/gejiawen/spec/blob/master/javascript-style-guide.md)

## CSS

| 条目 | 说明 |
| :--- | :--- |
| 文件 | 使用无 BOM 的 UTF-8 编码 |
| 缩进 | 使用 4 个空格做为一个缩进层级，不允许使用 2 个空格 或 tab 字符。 |
| 空格 | 选择器与`{`必须有空格。属性与值之间要有空格 |
| 双引号 | 选择器的值使用双引号 |
| 属性对 | 遵循每一个选择器规则独占一行 |

更多内容可参考：[SPEC:CSS](https://github.com/gejiawen/spec/blob/master/css-style-guide.md)

## HTML

| 条目 | 说明 |
| :--- | :--- |
| 缩进 | 使用 4 个空格做为一个缩进层级，不允许使用 2 个空格 或 tab 字符。 |
| doctype | 总是使用html5的doctype |
| class命名 | 使用全小写，使用`-`链接多个单词，且尽量有意义 |
| 元素ID | 在同一个页面保持唯一性 |
| 标签和属性 | html标签采用全小写 |
| 自闭合 | 不允许无需闭合的标签自闭合 |
| 合理使用标签 | 语义化使用，防止滥用div |

更多内容可参考：[SPEC:HTML](https://github.com/gejiawen/spec/blob/master/html-style-guide.md)