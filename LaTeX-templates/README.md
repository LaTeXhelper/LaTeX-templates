# LaTeX-templates

用于存放LaTeX模板。

## 离线使用方法

你需要将你比较心仪的模板/tex代码片段写入一个.tex文件中，并最好在开头加入一段注释，描述其功能特点。类似这样：

```latex
% A template for pictures(using captionof)

\usepackage{captionof}

\begin{center}
    \includegraphics[width=0.8\textwidth,height=0.4\textheight]{1.png}
    \captionof{figure}{picture_name}
\end{center}

```

## 贡献方法

1. fork 本项目

2. 将fork后的仓库克隆到本地

3. 向该仓库添加你的模板

4. 将本地更改push到github

5. 向主仓库提出pull request

