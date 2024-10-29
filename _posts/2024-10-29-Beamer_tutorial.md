---
title: 'OneDrive'
date: 2024-10-29
permalink: /posts/2024/blog-7
tags:
  - LaTeX
  - Tutorials
---

# Beamer 常用代码
> Reference: https://wzbtech.com/tech/beamer.html

> Cheat Sheet: https://www.cpt.univ-mrs.fr/~masson/latex/Beamer-appearance-cheat-sheet.pdf
## 最常用

### frame
```latex
\begin{frame}
    \frametitle{FrameTitle}
    
\end{frame}
```

### block
```latex
\begin{block}{BlockTitle}

\end{block}
```

### 公式(equation)
```latex
\begin{align*}
    f(z)&=b\\
    &=c+d
\end{align*}
```
### 无序列表
```latex
\begin{itemize}
  \item $9+8=17$
  \item $2+1=3$
\end{itemize}
```

### 图片
```latex
% 设置默认图片路径
\graphicspath{{images/}}

\begin{figure}[h]
    \centering
    \includegraphics[width=0.8\textwidth]{image.png}
\end{figure}
```

### 最后感谢页
```latex
\begin{frame}
    \frametitle{}
    \Huge
    \begin{center}
        Thank You!
    \end{center}
\end{frame}

% 文字可选：The End | Thank You for Your Attention! | Thank You for Listening!
% 文字可选：谢谢！| 感谢聆听！
```

## 代码片段

### 零碎
```latex
% 强调文本
\alert{Kernel trick}
{\color{red} text}

% frame中调整行间距
\addvspace{-0.6cm}

% block中调整行间距
\vspace*{-\baselineskip}\setlength\belowdisplayshortskip{0.6pt}

% 文本内容加框
\usepackage{tcolorbox}
\begin{tcolorbox}
    text
\end{tcolorbox}

% 封面页
\frame{\titlepage}

% 章节
\part{PartName}
\section{SectionName}
\subsection{SubsectionName}
\section[ShortName]{LongName}

% 介绍
\title[ShortVersion]{YourTitle}
\author[short]{YourName}
\date{November 26th, 2018}
\subtitle{Your Subtitle Here}
\institute[short]{institute}
\titlegraphic{\includegraphics[width=2cm]{logo.png}} % 在页面中间位置加图片
\logo{\includegraphics[width=1.3cm,height=1.3cm]{logo.jpg}} % 封面上没有图片，这会加到之后每一页右下角

% author中换行，一种是名字足够长它会自动换行；另一种如加指导教师，则在author中使用\\换行，但这会有warning

% 多作者机构对应
\author[shortname]{author1 \inst{1} \and author2 \inst{2}}
\institute[shortinst]{\inst{1} institute for author1 \and 
                      \inst{2} institute for author2}

% 机构字体放大
\setbeamerfont{institute}{size=\normalsize}

% 插入直线
\noindent\rule{\textwidth}{1pt}

% 页脚只留页码
\setbeamertemplate{footline}[frame number]
```

## 更多环境
```latex
% remark环境
\begin{alertblock}{Remark}

\end{alertblock}

% 其他环境
theorem
examples
```

## 目录
```latex
% 加目录页
\begin{frame}\frametitle{Outline}
    \tableofcontents
\end{frame}

% 每个section自动添加目录页
\AtBeginSection[]{
    \frame{\frametitle{Outline}\tableofcontents[
        sectionstyle=show/shaded,
        subsectionstyle=show/show/shaded]}
}

% section自动目录，不在handout中生成
\AtBeginSection[]{
    \begin{frame}<beamer>
        \frametitle{Outline}\tableofcontents[
        sectionstyle=show/shaded,
        subsectionstyle=show/show/shaded]
    \end{frame}
}
```
## 分栏
```latex
\begin{columns}

    \column{0.5\textwidth}
    This is a text in first column.
    $$E=mc^2$$
    
    \column{0.5\textwidth}
    This is a text in second column.

\end{columns}


% 2个 0.5\linewidth 可以左右分，两个 \linewidth 可以上下分
\begin{minipage}{0.5\linewidth}
    \begin{figure}[h]
        \includegraphics[width=\textwidth]{minipage.jpg}
    \end{figure}
\end{minipage}
```

## 三线表格
```latex
\usepackage{booktabs}

\begin{center}
    \begin{table}[!t]  
        % \caption{Three line}
        % \label{table_time}
        \begin{tabular}{ccc}  
            \toprule   
            first&second&third\\ 
            \midrule       
            1 & 2 & 3 \\ 
            4 & 5 & 6 \\ 
            7 & 8 & 9 \\
            \bottomrule  
        \end{tabular}
    \end{table}
\end{center}
```

## 首行缩进
```latex
\usepackage{indentfirst} 
\setlength{\parindent}{2em}
```

## 将内容置于页面任意位置
```latex
\usepackage{tikz}

\begin{tikzpicture}[remember picture,overlay]
    \node[xshift=5cm,yshift=6cm] at (current page.south west) {long sentence long sentence};
    \node[xshift=5cm,yshift=4cm] at (current page.south west) {\includegraphics[width=0.1\textwidth]{image.png}};
\end{tikzpicture}
```

## 更多操作
## 动态效果(overlay)
动态列表
```latex
\begin{itemize}
\item 2 is prime (two divisors: 1 and 2).
\pause
\item 3 is prime (two divisors: 1 and 3).
\pause
\item 4 is not prime (\alert{three} divisors: 1, 2, and 4).
\end{itemize}
```
（动态文本也是用\pause即可）

更灵活地控制
```latex
\begin{itemize}
 \item<1-> Text visible on slide 1
 \item<2-3> Text visible on slide 2
 \item<3-> Text visible on slide 3
 \item<4-> Text visible on slide 4
\end{itemize}
```

细节控制
```latex
\definecolor{mygray}{gray}{0.6}
{\color<1>{mygray} \alpha} \beta

\onslide<2->{\alpha} \beta
```

## 缩小字体
frame整体缩小
```latex
\begin{frame}{framtitle}
    \scriptsize
    small text\\
    small text
\end{frame}
```

frame部分缩小
```latex
\begin{frame}{framtitle}
    \begingroup
        \scriptsize
        small text\\
        small text
    \endgroup
    big text
    big text
\end{frame}
```
这样也可以用于多个frame缩小

## 插入代码
涉及代码的frame都需要设置[fragile]。

同时，\end{frame}必须另起一行并顶格（不允许有缩进）
```latex
\begin{frame}[fragile]

\end{frame}
```

### 代码块

1. 使用verbatim环境
```latex
\begin{verbatim}
    int main (void)
    {
        std::vector<bool> is_prime (100, true);
    }
\end{verbatim}
```
2. 实测verbatim遇到latex代码会出现问题，需要新建 一个环境
```latex
\documentclass{beamer}
\newenvironment{fragileframe}%
  {\begin{frame}[fragile,environment=fragileframe]}%
  {\end{frame}}

\begin{document}
\begin{fragileframe}
  \begin{verbatim}
    \end{frame}
  \end{verbatim}
\end{fragileframe}
\end{document}
```

3. 使用listings宏包
```latex
\usepackage{listings}

\begin{lstlisting}[language=R]
    a <- c(1, 2)
    b <- a + 1
\end{lstlisting}
```

### 行内代码

在uncoverenv环境中使用\verb
```latex
\begin{uncoverenv}
    Note the use of \verb|\std::|.
\end{uncoverenv}
```

\verb
Note the use of \texttt{\textbackslash alert}.

## 脚注引用
将参考文献放在当前页脚注，正文用\footnotemark标注即可，脚注如下
```latex
\footnotetext[1]{\scriptsize Lei N, Luo Z, Yau S T, et al. Geometric understanding of deep learning[J]. arXiv preprint arXiv:1805.10451, 2018.}
```
注意：同一个beamer下如果有多个\footnotetext，\footnotemark会自动按数字顺序排下去，因此\footnotetext[n]中n也要随之变化。

## BibTex引用
正常设置bib文件，也正常在正文中用\cite引用，最后放参考文献列表，支持换页
```latex
\begin{frame}[allowframebreaks]
    \frametitle{References}
    \scriptsize
    \bibliographystyle{plain}
    \bibliography{bibfile}
\end{frame}
```
此外，还可以在前面进行一些样式
```latex
% 修改标号
\setbeamertemplate{bibliography item}{\insertbiblabel} 

% % 三部分不换行
% \setbeamertemplate{bibliography entry title}{}
% \setbeamertemplate{bibliography entry location}{}
% \setbeamertemplate{bibliography entry note}{}

% % 三部分使用相同颜色
% \setbeamercolor{bibliography entry author}{fg=black}
% \setbeamercolor{bibliography entry title}{fg=black} 
% \setbeamercolor{bibliography entry location}{fg=black} 
% \setbeamercolor{bibliography entry note}{fg=black}  
% \setbeamercolor{bibliography item}{fg=black}
```

## 支持中文
## 编译
### xelatex编译
```latex
\documentclass{beamer}
    \usepackage{ctex}  % 会引起一些公式排版问题，如\hat U 所以加下面的字体主题
    \usefonttheme{professionalfonts}
    \author{作者}
    \title{演讲主题}
    \date{2018年11月29日}
    \begin{document} 
        \frame{\titlepage}
        \begin{frame}
            中文
        \end{frame}
    \end{document}

```
### pdfLatex编译
```latex
\usepackage{CJKutf8}

\author{名字}
\title{Presentation Title}
\date{January 1, 2018}

\begin{document}
    \begin{CJK}{UTF8}{song}   

    \begin{frame}
        中文
    \end{frame}

    \end{CJK}
\end{document}
```
下面小节若未做说明就都是基于xelatex+ctex

## 首行缩进问题
中文首行会自动缩进，中文后加无序列表会使列表看起来没有缩进，所以需要下面命令使列表缩进更多。
```latex
\settowidth{\leftmargini}{\usebeamertemplate{itemize item}}
\addtolength{\leftmargini}{8\labelsep}
```
如果取消首行缩进，文字可能会太靠近边缘，因此这里选择了缩进列表。如果想要让某一行取消缩进，可以在前面加上\noindent。

## 字体
```latex
\setCJKmainfont{宋体}
\setCJKmainfont{黑体}
\setCJKmainfont{楷体}
\setCJKmainfont{微软雅黑}
\setCJKmainfont{SimHei}  % 黑体
\setCJKmainfont{MicrosoftYaHei}  % 微软雅黑，编译起来有点慢
```
更详细可以参考latex文章。

## 主题套用
```latex
% 套用主题
\usetheme
\usecolortheme
\usefonttheme
\useinnertheme
\useoutertheme
```

寻找主题

内置 [Beamer Matrix](https://hartwork.org/beamer-theme-matrix/)
第三方 [overleaf](https://www.overleaf.com/gallery/tagged/presentation)

## 模板套用
```latex
\documentclass{beamer}
    \usepackage[english]{babel}
    \usetheme{warsaw}
          
    \author{Your Name}
    \title{Your title}
    \date{November 29th, 2018}

    \begin{document}
        \frame[plain]{\titlepage}
        \section{Introduction}
        \begin{frame}
            \frametitle{Latex and Beamer}
            LaTeX is a high-quality typesetting system; 
            it includes features designed for the production of 
            technical and scientific documentation.
        \end{frame}
    \end{document}
```
在这基础上变化

加载包
换主题: Simple, Madrid, CambridgeUS
加outertheme: infolines, tree, split
## 我的主题(simple)
下载主题，使用beamerthemeSimple.sty文件，使用方法与上面相比只需要换主题名称
```latex
% 基本用法
\usetheme{Simple}
\useoutertheme{tree} 

% 可选颜色配置
\usetheme[RGB={12 72 66}]{Simple}
\usetheme[HTML=A30000]{Simple}

HTML=096148      % green
RGB={12 72 66}   % bluegreen
HTML=8D742A      % brown
RGB={163 0 0}    % red

% 推荐导航配置
\useoutertheme{split}
\useoutertheme{tree}
\useoutertheme{infolines}

\documentclass[compress]{beamer}
    \useoutertheme[subsection=false]{miniframes}
sidebar版，使用beamerthemeBar169.sty文件

\documentclass[aspectratio=169]{beamer}
    \usepackage[english]{babel}
    \usetheme[RGB={12 72 66}]{Bar169}

    \author{Your Name}
    \title{Your Title}
    \date{November 29th, 2018}

    \begin{document}
        \frame[plain]{\titlepage}
        \section{Introduction}
        
        \begin{frame}
            \frametitle{Latex and Beamer}
            LaTeX is a high-quality typesetting system; 
            it includes features designed for the production of 
            technical and scientific documentation.
        \end{frame}
    \end{document}
```

## 加载包
```latex
\usepackage{amsmath,amssymb,amstext} 
\usepackage{float}
\usepackage{array}           
\usepackage[english]{babel}
\usepackage{fancyhdr}        % header footer
\usepackage{graphicx}        % figure
\usepackage{algorithm2e}
\usepackage{booktabs}        % three line table
\usepackage{bookmark}        
\usepackage{xcolor}
\usepackage{color}
\usepackage{lmodern}         % include more fontsize, e.g. 15pt
```
## 其他技巧
## 提高编译速度|draft
在不生成最终文件时，可以先不生成目录、导航、图片等东西，每一步只关注内容。
```latex
\documentclass[draft]{beamer}
提高编译速度|加载指定页
给frame指定标签
```latex
\begin{frame}[label=example1]{FrameTitle1}
    content1
\end{frame}

\begin{frame}[label=example2]{FrameTitle2}
    content2
\end{frame}
```

在导言区指定加载的标签
```latex
\includeonlyframes{example1, example2}
```

## 生成打印版本|handout
slides的打印版本不希望有动态效果和章节封面
```latex
\documentclass[handout]{beamer}

% 生成handout时重新定义这个颜色
\mode<handout>{%
    \definecolor{mygray}{RGB}{0,0,0}
}
```


# 在 Beamer 中添加计时器和 Logo
> Reference: https://blog.amito.me/2019/04/Adding-Timer-and-Logo-in-Beamer/

在 PPT 中有一个演讲计时功能，能够帮助报告人掌握演讲时间。 其实 pdf 中也有这一功能，在 beamer 中添加计时器比较方便。 此外，在 beamer 标题中加上特定的 Logo 也是比较简单的。

## 添加 timer 计时器

LaTeX 中 `tdclock` 包可以提供定时功能。添加一个计时器也很简单。

1. 在导言区加入 `tdclock` 包。可以设置一次提醒，二次提醒时间，更新时间间隔等等。

    ```latex
    \usepackage[timeinterval=2.0, timeduration=2.0, timedeath=0,
    fillcolorwarningsecond=white!60!yellow,timewarningfirst=900,timewarningsecond=1080]{tdclock}
    ```

2. `\initclock` 初始化。在适当的位置，如 titlepage 中加入这一命令。

    ```latex
    \begin{frame}
    \titlepage
    \initclock
    \end{frame}
    ```

3. 在要显示的地方加入`\crono`命令，比如在 footer 中。如果使用的三段式 footer 结构，可以在 footer 中显示时间，则可以这样做：

    ```latex
    \begin{frame}
    \titlepage
    \initclock
    \end{frame}
    \date{\today \crono}
    ```

这样会显示日期和从 00:00:00 开始的计时器

## 在 frame 中加入 logo

### 在标题中加入 logo

通过简单地修改 frametitle 就能加入 logo， 而不用 textopt 等包。

1. 在 \begin{document} 之前重新定义 frametitle，这会在 frametitle 最右端显示一个 logo:

    ```latex
    \setbeamertemplate{frametitle}
    {
        \begin{beamercolorbox}[wd=\paperwidth]{frametitle}
        \strut\hspace{0.5em}\insertframetitle\strut
        \hfill
        \raisebox{-2mm}{\includegraphics[width=1cm]{$logo$}}
        \end{beamercolorbox}
    }
    ```

2. 只为 titlepage 页面，定义新的 logo，而不是在 title 中添加 logo。

    ```latex
    \setbeamertemplate{logo}{}
    \titlegraphic{\includegraphics[height=1.8cm]{images/logo.jpg}\hspace{1em}\includegraphics[height=1.8cm]{images/lhaaso.png}}
    \begin{frame}
    \titlepage
    \initclock
    \end{frame}
    ```

### 在页面右下角加入 logo

1. 有时我们会想在其它地方加上 logo， 比如 页面右下角， 这时一般直接使用 `\logo` 命令即可。

    ```latex
    \logo{\includegraphics[height=1cm]{my_logo.png}}
    ```

2. 如果想要调整位置，可以使用 pgf 命令， 但坐标位置需要仔细调整。

    ```latex
    \logo{\pgfputat{\pgfxy(-9,9)}{\pgfbox[center,base]{\includegraphics[width=1.5cm]{$logo$}}}}
    ```

# 页脚设置
1. 去除右下角导航栏
    ```latex
    \setbeamertemplate{navigation symbols}{}
    ```
2. 添加右下角页码
    ```latex
    \setbeamertemplate{footline}[frame number]
    ```