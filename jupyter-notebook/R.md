# Jupyter NotebookでRを使えるようにする

## 前提条件
- R、Anacondaはインストール済みとする

## 環境
- OS：Windows 10 Home
- Anaconda Navigator：1.9.6
- R：3.5.2

## インストール手順

### 1. パッケージのインストール

```R
> install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))
> devtools::install_github('IRkernel/IRkernel')
```

### 2. コマンドの実行

```R
> IRkernel::installspec()
```

なお、上記を実施した場合、下記のエラーが発生する場合がある。

```
Error in installspec() :
  jupyter-client has to be installed but “jupyter kernelspec --version” exited with code 127.
In addition: Warning message:
In system2("jupyter", c("kernelspec", "--version"), FALSE, FALSE) :
  '"jupyter"' not found
```

その場合は、Anaconda Navigatorからターミナルを起動し、R.exeを実行し、その中で`IRkernel::installspec()`を実行する。
実行に成功すると、Rのノートブックが選択できるようになる。

<img src=".\img\R_installed.JPG" width="400">

### 3. 実行確認

<img src=".\img\R_notebook.JPG">