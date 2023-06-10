# LaTeX4SSDUT

这是一个基于赵小棠等人的软院毕业论文LaTeX模板的修改版，改正了一些原项目的格式问题，并提供了最精简的样例示范

你可以选择：

* 下载到本地，使用你自己的编辑器编写并渲染
* 使用 Overleaf 打开模板并克隆到自己的项目列表中（推荐）
  * [克隆模板](https://www.overleaf.com/read/nbfqqztpdwbd)，点击直接打开 Overleaf

## 模板文件介绍

```
.
├── GBT7714.bst // 引用格式文件
├── *.TTF       // 字体文件
├── body
│   ├── archive
│   │   ├── appendix1.tex // 附录
│   │   ├── author.tex    // 项目作者信息，从 maintest.tex 中删除
│   │   ├── chap00.tex
│   │   ├── grant.tex     // 关于使用授权的声明
│   │   ├── modify.tex    // 修改记录
│   │   ├── original.tex  // 原创性声明
│   │   └── thank.tex     // 致谢
│   ├── chap01.tex      // 论文第 n 章，由 maintest.tex 管理
│   ├── chap02.tex
│   ├── chap03.tex
│   ├── chap04.tex
│   ├── chap05.tex
│   ├── conclusion.tex
│   └── reference.tex   // 参考文献，如使用 bibtex 则无需修改
├── figures   // 图片文件存放路径
│   └── system.png
├── maintest.tex  // 主文件，管理
├── preface
│   └── cover.tex // 论文封面
├── reference.bib // 参考文献 bibtex
└── setup
    ├── fonts.tex     // 字体设置
    ├── format.tex    // 格式设置
    └── packages.tex  // 包设置

```

## 使用 Overleaf 的注意事项

* 在 Menu 中修改 `Compiler -> XeLaTeX`，`Main document -> maintest.tex`
* 如果遇到编译慢、超时等问题，建议刷新后重新编译，以及查看字体等基础设置是否有问题
* 一定程度上可以忽略警告 ⚠️
* 若有需要，可以 `clear cached files` 试试
* 使用项目中提供的 `TTF/TTC` 字体文件和 `Times New Roman`，不建议使用 Overleaf 官方提供的中文字体

## 样例示范

### 引用

* bibtex

```LaTeX
文字\cite{label}

\bibliography{reference}
```

* bibitem

```LaTeX
文字\cite{label}

\begin{thebibliography}{99}
\bibitem{label}GB7714 reference
\end{thebibliography}
```

### 列表

```LaTeX
\begin{asparaenum}[（1）]
\item 列表内容一
\end{asparaenum}
```

### 公式

```LaTeX
\begin{equation}
\setlength{\abovedisplayskip}{3pt}
\setlength{\belowdisplayskip}{3pt}
E = mc^2
\end{equation}
```

### 图片

```LaTeX
\begin{figure}[htbp]
	\centering
	\includegraphics[scale = 0.165]{path/to/image}
	\caption{\song\wuhao title}
	\label{label}
\end{figure}
```

### 伪代码

```LaTeX
\begin{algorithm}
\caption{caption}
\label{label}
\begin{algorithmic}[1]
\REQUIRE{输入}
\ENSURE{输出}

\FOR{each $i \in list$}
    \STATE $y \gets i$
    \IF{if condition}
        \STATE if state
    \ELIF{else if condition}
        \STATE else if state
    \ELSE
        \STATE else state
    \ENDIF
\ENDFOR
\end{algorithmic}
\end{algorithm}
```

### 表格

```LaTeX
\begin{table}[htbp]
\setlength{\abovecaptionskip}{0cm}
% \setlength{\belowcaptionskip}{-0.2cm}
  \centering
  \song\wuhao
  \caption{caption}
  \setlength{\tabcolsep}{3mm}{
    \begin{tabular}{ccccc}
    \hline
    \multirow{2}[4]{*}{col1} & \multirow{2}[4]{*}{col2} & \multicolumn{3}{c}{multicol} \\
\cmidrule{3-5}         & & col3 & col4 & col5 \\
    % \midrule
    \hline
          & 视觉   & 37.3 & 33.0 & 4.3 \\
    item1 & Wi-Fi  & 31.7 & 30.4 & 1.3 \\
          & 多模态 & 37.9 & 33.1 & 4.8 \\
    \hline
          & 视觉   & 37.3 & 33.0 & 4.3 \\
    item2 & Wi-Fi  & 32.5 & 30.5 & 2.0 \\
          & 多模态 & 38.8 & 33.5 & 5.3 \\ \hline
    \end{tabular}}
  \label{io_train_time_tab}
\end{table}
```

## 参考文献注意事项

* 参考文献推荐使用 `bibtex` 或 `bibitem`（推荐）生成，如有需要可自行补充填写
* 如果引用了硕士/博士毕业论文，需要添加城市信息，可参考 `reference.bib`
* 注意国标7714的区分，`GB/T` 为推荐样式，泥工不接受国标推荐
* 如果使用 Google 学术（推荐）引用参考文献，请选择香港地区版本（搜索url前缀为`https://scholar.google.com.hk/scholar?hl=zh-CN`），可以直接复制 `GB/T 7714` 到 `bibitem`，但需要再次检查格式
* 所有英文人名应大写，中文人名使用“等”省略超过三人的作者

---

感谢可以从软国的 LaTeX 模板白嫖国标 bst 文件，建议阅读和对有问题的地方进行修改
