# ZDocs
*声明：本项目与https://github.com/ZeroDream-CN/ZDocs 没有任何关系*
## 什么是 ZDocs
ZDocs 是一个基于[Zarkdown](https://yangzizhoudiwuxuande.GitHub.io/zarkdown/intro)的文档，适用于软件支持文档。
## 编写
ZDocs 使用`.zdoc`
文件（其实就是`.zkdn`文件，但略有不同。）

下面是`.zdoc`文件示例
```zdoc

---
title: 全语法测试大全
version: 1.0.0
---

/ 一级标题 (H1)

这是放在最顶部的元数据，Frontmatter 会在渲染时被自动隐藏。

// 二级标题 (H2)

/// 三级标题 (H3)

//// 四级标题 (H4)

----- 
(上面是分割线)

// 基础行内语法

这里有 ?粗体文字?、\斜体文字\、_下划线文字_ 和 -删除线文字-。
这里还有 `~行内代码~` 和 **Markdown 风格的粗体**。

如果你不想让特殊符号生效，可以使用转义符：^?这不是粗体^?，^/这不是标题。

// 链接与图片

这是一个外部链接：*访问 GitHub*(https://github.com)
这是一个内部链接：*返回首页*(01-欢迎使用.zdoc)

这是一张图片（源自网络）：
$Zarkdown Logo$(https://img.shields.io/badge/zarkdown-2.1.0-blue)

// 列表与引用

! 这是无序列表的第一项
! 这是无序列表的第二项
! 这是无序列表的第三项

| 这是一段引用文字，通常用于引用名言或者强调某段说明。
| 如果你在第二行也写了竖线，它也会被渲染为引用的一部分。

// 表格测试

| 语法名称 | 符号 | 是否支持嵌套 |
| :--- | :--- | :--- |
| 粗体 | ? ? | 支持 |
| 斜体 | \ \ | 支持 |
| 代码 | ~ ~ | 不支持 |

// 注释与脚注

<这是一段隐藏的注释，你在网页上是看不到它的，只能在源码里看到。>

这是一个带有脚注的句子[1]<这是一个悬浮显示的脚注说明>。

// 多行代码块

~python
def hello_zarkdown():
    print("Hello, ZDocs!")
    # 这里的代码会被原样保留，不会被解析
~

// ZDocs 专属：提示框 (Admonitions)

::: tip
这是一个 `tip` 提示框，通常用于展示技巧或补充说明。
:::

::: warning
这是一个 `warning` 警告框，用于提醒用户注意潜在的风险。
:::

::: danger
这是一个 `danger` 危险框，用于严重警告，比如会导致数据丢失的操作。
:::

// ZDocs 专属：折叠面板

::: details 点击展开查看更多详情
这里面可以包含很多东西，甚至包含另一个代码块。
~bash
npm install zdocs
~
:::

// ZDocs 专属：API 端点

::: api POST /api/render
接收一段 Zarkdown 文本，返回渲染后的 HTML。
:::

// ZDocs 专属：多标签代码组

::: code-group [macOS 安装]
~bash
brew install zarkdown
~
:::

::: code-group [Linux 安装]
~bash
sudo apt install zarkdown
~
:::
```
## 上手
先将 ZDocs 的源代码下载到本地。

接下来开始编写。请不要对`index.html`做任何修改。在本地中的 ZDocs 文件夹中创造一个 Docs 文件夹。在 Docs 文件夹中创造一些`.zdoc`文件。

创建完文件后，在`files.html`中对已经创建的文件注册。例如创建了`01-欢迎使用.zdoc`和`02-进阶教程.zdoc`这两个`.zdoc`文件，就需要在`files.html`中写入
```html

<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>ZDocs - 文件配置</title>
</head>
<body>
  <script>
    const myDocFiles = [
      "01-欢迎使用.zdoc",
      "02-进阶教程.zdoc"
    ];
  </script>
</body>
</html>
```
如果您要修改文档标题，只需要在`title.html`中更改标题即可。
## 许可
ZDocs 使用 ZDocs LICENSE。
