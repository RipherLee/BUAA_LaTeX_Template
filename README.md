# BUAA LaTeX Template

北航适用于各类大作业的 LaTeX 模板

## 项目说明

这是源自北航开源俱乐部维护的的北航毕设论文的 LaTeX 模板，我是24年下载的他们的模板，并做了简单的改动，方便简单的大作业或者实验报告的编写，省去了对完整了论文模板进行大量的修改的过程。

需要原始的北航毕业论文模板，请转到[北航毕业论文 LaTeX 模板](https://github.com/BHOSC/BUAAthesis)


## 使用方法
这里只介绍改模板的一些比较基础的内容更改方式。如果需要了解 $\LaTeX$ 的使用方法，请转到[LaTeX使用方法（中文版）](https://texdoc.org/serve/lshort-zh-cn.pdf/0)或[LaTeX使用方法（Github）](https://github.com/CTeX-org/lshort-zh-cn?tab=readme-ov-file)

`report.tex`：在这个文件里编写你的报告的主要内容，你也可以根据需求将报告的各个章节拆分，然后在导入到这里面整合。运行该程序即可生成对应的PDF文件。

`sample-bechelor.tex`：原项目的本科生论文模板，可以参考该模板的排版方式，以及模板中各个章节涉及到的该模板的使用方法。

`/data/com_info.tex`：包含了论文标题、作者姓名、导师姓名、学院名称、专业以及中英文摘要关键字等基本信息，需要更改时，改变对应位置内容即可。

`/data/bachelor/bachelor_info.tex`：原项目的本科生信息，包括班级、学号、单位代码、报告编写时间等，也可整合到`com_info.tex`中。

`/out`：项目的运行结果文件夹，可以在这里找到生成的PDF文件，如`report.tex`。想要更改生成文件的位置和内容，修改`/.vscode/settings.json`里的配置内容即可。

`/figure`：存放报告图片的文件夹，强烈推荐将报告涉及到的图片都放在该文件夹中，方便管理。



---
**以下内容为原项目的项目说明**

## 依赖

模板依赖 v2.0 及以上版本的 ctex 包，请使用较新版本的 LaTeX 发行版。

目前已经测试的 LaTeX 发行版包括：

+ TeXLive 2015、TeXLive 2016、TeXLive 2019（** 推荐 **）
+ CTeX 2.9.3

对于老版本的 LaTeX 发行版，请通过包管理器升级 ctex 的版本。



此外，对于非Windows环境，会需要额外安装两个字体：

* `Times New Roman`，该字体可以在Windows系统字体库中获取，可以从[此链接下载](https://dl.freefontsfamily.com/download/Times-New-Roman-Font/)，也可以在Ubuntu/Debian下快速安装（**推荐使用此方法以实现自动化**）

```shell
echo ttf-mscorefonts-installer msttcorefonts/accepted-mscorefonts-eula select true | sudo debconf-set-selections  # 用于非交互模式下自动安装，其他情况下非必须
sudo apt-get install -y ttf-mscorefonts-installer  # 安装微软核心字体库
```

* `STXingKai`，该字体暂无可靠的自动安装手段，可以从Windows系统字体库中获取，或从[此链接下载](https://github.com/dolbydu/font/raw/master/unicode/STXingkai.TTF)。

* `STKaiTi`，该字体暂无可靠的自动安装手段，可以从Windows系统字体库中获取，或从[此链接下载](https://github.com/dolbydu/font/raw/master/unicode/STKaiti.TTF)。

* `SimSun`，该字体暂无可靠的自动安装手段，可以从Windows系统字体库中获取，或从[此链接下载](https://github.com/dolbydu/font/raw/master/unicode/SimSun.ttc)。

* `SimHei`，该字体暂无可靠的自动安装手段，可以从Windows系统字体库中获取，或从[此链接下载](https://github.com/dolbydu/font/raw/master/unicode/SimHei.ttf)。

关于Linux环境下安装字体，可以参考此篇：[linux安装字体](https://www.cnblogs.com/wangjiming/p/12553535.html)

如需更多字体文件，可以去[此仓库查找并下载](https://github.com/dolbydu/font)。

## 参考文献相关

模板参考文献格式采用国家标准 `GB/T 7714-2005` 《信息与文献 参考文献著录规则》之中描述的格式。代码实现为 `CTeX-org / gbt7714-bibtex-style` v2.0.1[https://github.com/CTeX-org/gbt7714-bibtex-style/](https://github.com/CTeX-org/gbt7714-bibtex-style/)。参考文献详细说明请见该项目 README.md 或 [https://mirror.ctan.org/biblio/bibtex/contrib/gbt7714/gbt7714.pdf](https://mirror.ctan.org/biblio/bibtex/contrib/gbt7714/gbt7714.pdf)。

参考文献提供两种排序方式，分别为 ` 按出现顺序 `（默认）和 ` 按作者姓名和年份 `，请按需在模板 `data\reference.tex` 中做相应修改。

注意：根据 `GB/T 7714-2005` 中 `8.4 节 出版项 ` 中相关规定：

+ 无出版地的中文文献著录 “出版地不详”，外文文献著录 “S.l.”
+ 无出版者的中文文献著录 “出版者不详”，外文文献著录 “s.n.”

相应的解决方法为

+ 若编译的参考文献条目中出现 “出版地不详” 或 “S.l.”，请在相应的 bib 条目中添加 address 相关信息
+ 若编译的参考文献条目中出现 “出版者不详” 或 “s.n.”，请在相应的 bib 条目中添加 publisher 相关信息

实际使用中应避免出现 `［S.l.］:［s.n.］` 这样的著录形式。

## 文件格式相关

目前论文提交网站不再要求必须提交 docx 等格式的 Word 文件，但部分老师会要求在 Word 文件上修改和批注。
可使用如下方法将 Latex 文件（或编译后的 pdf 格式文件）转换为 Word 文件。

**注意**：将未公开的论文上传至网络有风险，推荐在本地进行转换。

### 本地转换

推荐使用 [latex2word](https://github.com/Mingzefei/latex2word) 这一项目。
该项目支持指定 Word 文件格式，并且支持公式转换、多子图导入、公式图表文献的交叉引用等功能，转换出的 Word 文件可满足修改和批注需求。

### 在线转换

如下网址效果较好：

- [ilovepdf](https://www.ilovepdf.com/)：整体效果好，包括页眉和页脚；公式支持差。
- [nitro](https://cloud.gonitro.com/)：需要注册；对超链接、目录、段落格式和字体等支持较好；公式支持差。

