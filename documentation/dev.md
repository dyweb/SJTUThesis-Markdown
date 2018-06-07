# 开发者指南

本模板使用 bookdown 实现了由 R Markdown -> LaTeX -> PDF 的一系列转换，其中用到的依赖有：

- bookdown
- pandoc
- Tex Live

## 实现原理

在 `template` 目录下定义了一个模板文件 `template.tex`，其利用 pandoc 的模板功能对 SJTUThesis 的 `thesis.tex` 文件进行了模板化的定义。在编译的过程中，bookdown 会将 `index.Rmd`中的配置注入到模板中并且在 `_book` 目录下生成真正的 tex 文件，随后对其进行编译。最后在 `_book` 中产生 PDF 文件

## 设计上的权衡

由于 bookdown 对 abstract 标签不支持，因此采取了一个 workaround，针对 abstract 一节保留了 tex 的编辑方式。
