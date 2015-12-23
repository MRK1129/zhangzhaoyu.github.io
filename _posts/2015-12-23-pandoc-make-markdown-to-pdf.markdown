---
layout:		post
title:		Pandoc导出markdown文件为PDF
description:	Ubuntu下Pandoc结合Latex导出markdown 文件为PDF...
categories:
- typesetting
tags:       markdown
---

# What is Markdown?
**[Markdown](https://en.wikipedia.org/wiki/Markdown)** is a lightweight markup language with plain text formatting [syntax](http://wowubuntu.com/markdown/) designed so that it can be converted to HTML and many 

other formats using a tool by the same name.We also can use **[pandoc](http://pandoc.org/)** to convert markdown file to PDF format. Next, I will introduce 

the way to do so.

# Install Software(Ubuntu Linux)
- Install pandoc : sudo apt-get install pandoc
- Install texlive : sudo apt-get install texlive texlive-latex-extra texlive-latex-recommanded(主要是为了生成中文的转换)
- Install fonts : 要支持中文还需要安装中文字体，比如[文泉驿微黑](http://www.bkjia.com/xtzh/760729.html)，可使用fc-list :lang=zh-cn 查看安装的所有中文字体

# 支持中文的操作

## Generate Template
终端输入：
`pandoc -D latex > ~/Templates/pandoc.template.tex
`

## 添加中文支持，
编辑 pandoc.template.tex

![template](/images/2015-12-23-001.png)

## Add to .bashrc
 - alias pandoc="pandoc --template=$HOME/Templates/pandoc.template.tex --latex-engine=xelatex" 
 - source .bashrc

## Generate PDF document
`pandoc source.md -o destination.pdf
`

# 参考
1. [如何把 Markdown 文件转化为 PDF？](http://www.zhihu.com/question/20849824)
2. [Markdown 语法说明](http://wowubuntu.com/markdown/)
3. [中文markdown转pdf](http://jiangfeng.org/notes/2013/04/19/markdown-with-pdf.html)
4. [Github Markdown Syntax](https://guides.github.com/features/mastering-markdown/#examples)






