# 全球文种的字体与布局

## 介绍

本书是 Simon Cozens 编写的《[Fonts and Layout for Global Scripts](https://simoncozens.github.io/fonts-and-layout/)》的中文翻译版，是一本关于字体设计、Unicode和计算机中复杂文本处理的免费书籍。

因为本书的主题是字体，为了保证显示效果和想表达的内容一致和满足我个人打印出来阅读的需求，故选择 PDF 作为发布格式。

编译出的PDF文件可从以下两处下载：

1. [GitHub Release](https://github.com/7sDream/fonts-and-layout-zhCN/releases/latest)
2. [CI](https://github.com/7sDream/fonts-and-layout-zhCN/actions/workflows/ci.yaml) 中的 Artifacts

其中 Release 中的不一定是最新版，但永久有效。
CI 中会有最新版但可能失效，如果过期可开 Issue 告知。

## 反馈与共建

本项目使用 [Typst](https://github.com/typst/typst) 作为排版工具。

各章节内容在 `chapters` 文件夹中，正文内容（除各类图示外）基本均为类似 Markdown 的纯文本，即使没有使用过 Typst 也非常容易看懂。

所以如果发现明显翻译问题或笔误，鼓励直接提交 PR，并通过 CI 生成的文件检查修复结果。

版式调整与字体更换（涉及`/template`）、术语翻译（涉及`/lib/glossary.typ`）等影响较大的修改等请在 PR 前先开 Issue 讨论。

原文更新导致翻译需要更新时，请同时修改 `/template/consts.typ` 中的 `upstream-version`。

## 本地编译

安装 Typst 0.11.1。

下载[字体包](https://github.com/7sDream/fonts-and-layout-zhCN/releases/tag/extra-fonts%2F20240601)并解压，将 `extra` 文件夹放置在项目的 `fonts` 文件夹中。

使用下列命令进行编译：

```bash
typst --font-path fonts book.typ
```

详细流程参考 [CI workflow 文件](https://github.com/7sDream/fonts-and-layout-zhCN/blob/master/.github/workflows/action-build.yaml)。

如果想所见即所得的编辑，推荐使用 VSCode 配合 [Tinymist](https://github.com/Myriad-Dreamin/tinymist) 和 [Typst Preview](https://github.com/Enter-tainer/typst-preview) 插件，并添加如下项目配置：

```json
{
    "typst-preview.fontPaths": [
        "${workspaceFolder}\\fonts",
    ],
    "tinymist.systemFonts": false,
    "tinymist.fontPaths": [
        "${workspaceFolder}\\fonts",
    ]
}
```

## 参考资料

- 《FontForge 与字体设计》一书中的[词汇表](http://designwithfontforge.com/zh-CN/Glossary.html)
- 知乎专栏文章《[Unicode®标准英文术语翻译对照表及部分术语汇释](https://zhuanlan.zhihu.com/p/79246427)》
- [Unicode 术语英中对照表](https://www.unicode.org/terminology/term_en_zh_Hans_CN.html)
- <https://symbl.cc/>
- Adobe OpenType 特性语言的语法高亮文件是从 [language-fontforge](https://github.com/Alhadis/language-fontforge) 项目转换而来，经过少量修改。

## LICENSE

许可证原书一致，为 [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.zh-hans)。

细节请参考 LICENSE 文件（或原项目 README），其中有原作者对演绎版本的一些要求。
