# LaTeX-templates

此仓库与LaTeX-helper项目[latex-helper](https://github.com/LaTeXhelper/LaTeX-helper)配合使用，存储LaTeX模板文件（包括article、beamer等格式）。欢迎大家提供自己的LaTeX模板库！

## 目录结构

```bash
.
├── config.yaml # 设置文件
├── LaTeX-templates # 存储tex模板
│	├── article # 存储用于article格式的模板
│   │   ├── math # 存储某一类型的模板
│   │   │   ├── foo.tex
│   │   │   └── bar.tex
│   │   ├── other
│   │   ├── picture
│   │   └── table
|   ├── beamer # 存储用于beamer格式的模板
│   │ ...
├── pdf # 存储模板编译生成的pdf
|   │ 
│   │ ...
```

仓库中的`description.json`,`requirements_pdf.txt`,`requirements_ppt.txt`均为程序自动生成，用户无需编辑。将这几个文件放在仓库中是为了方便用户开箱即用。

## 模板编写指南

对于article模板：

```tex
\documentclass[UTF8]{ctexart}
\usepackage{xxx}
...
\begin{document}
	% 您的模板放在这个位置时，自动编译脚本将有能力生成pdf文档
\end{document}
```

以下是创建article模板的一个实例：

```txt
% description: a template for Maxwell equation
% requirements: \usepackage{amsmath}

% Add your templates below:
$$
\begin{array}{l}
    \nabla \cdot \mathbf{E} = \frac{\rho}{\varepsilon _0} \\
    \nabla \cdot \mathbf{B} = 0 \\
    \nabla \times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t} \\
    \nabla \times \mathbf{B} = \mu _0 \mathbf{J} + \mu _0\varepsilon_0 \frac{\partial \mathbf{E}}{\partial t}

\end{array}
$$
```

对于beamer模板：

```tex
\documentclass{beamer}
\usetheme{xxx}
\usepackage{yyy}
...
\begin{document}
	% 您的模板放在这个位置时，自动编译脚本将有能力生成beamer预览文档
\end{document}
```

以下是创建beamer模板的一个实例：

```txt
% description: using different types of enumeration types
% requirement: \usepackage{enumitem}
\begin{frame}{Enumerate}

    \begin{enumerate}[label={\alph*)}]
        \item Alphabet one
        \item Alphabet two
    \end{enumerate}
    
    \begin{enumerate}[label={\roman*.}]
        \item Roman number one
        \item Roman number two
    \end{enumerate}
    
    \begin{enumerate}[label={(\arabic*)}]
        \item Arabic number one
        \item Arabic number two
    \end{enumerate}
\end{frame}
```

无论是对于article还是beamer，您都需要在description中写入您的代码片段功能，在requirements中写入必要的宏包（如果需要的话），之后在下方插入代码片段。您无需在片段中加入`\begin{document}`,`\end{document}`,`\usepackage{xxx}`等语句，因为自动生成脚本会帮助您补充这些内容。

## 贡献方法

1. fork本项目

2. 将fork后的仓库克隆到本地

3. 向该仓库添加你的模板

4. 将本地更改push到github

5. 向主仓库提出pull request