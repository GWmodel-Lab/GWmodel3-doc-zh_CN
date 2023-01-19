---
title: GWmodel3
---

**GWmodel3** 是新一代地理加权算法的 R 语言包，采用 C++ 内核与 R 语言接口结合的方式开发。
该包目前仍处在开发阶段。

# 编译安装

该包目前支持在 Linux 和 Windows 上进行编译安装，请下载源码包 [GWmodel3_3.0-0.tar.gz](http://gwmodel.whu.edu.cn/download/GWmodel3/GWmodel3_3.0-0.tar.gz)，
安装前需要安装依赖库 Armadillo 和 GSL 库，以及 **sf** 包。
根据系统的不同，安装方式也有所不同。

## Windows 系统

要安装依赖库 Armadillo，需要在 R 中安装 **RcppArmadillo** 包，可与 **sf** 包同时安装。

```r
install.packages(c("RcppArmadillo", "sf"))
```

安装 GSL 库的方法根据 RTools 的版本不同而略有不同。
请检查 RTools 安装路径下这些文件夹是否存在目录 `include/gsl/`
以及库文件 `lib/libgsl.a` 和 `lib/libgslcblas.a`：

- `usr`
- `mingw32` 或 `mingw64`
- `clang32` 或 `clang64`
- `x86_64-w64-mingw32.static.posix`

如果存在，则可直接进行编译；
如果不存在，则需要使用 Professor Ripley 提供的库文件
[local323.zip](https://www.stats.ox.ac.uk/pub/Rtools/goodies/multilib/local323.zip)。
下载后解压到 R 的安装目录 `R_HOME` 中，确保压缩包中的 include 文件夹与 `R_HOME/include` 合并，
并将压缩包中 `lib` 文件夹整体放置在 `R_HOME` 下，即 `R_HOME/lib` 文件夹。

依赖库安装好之后，使用如下命令安装源码包：

```powershell
R.exe CMD INSTALL GWmodel3_3.0-0.tar.gz
```

## Linux 系统

在 Linux 系统上依赖库的安装会比较简单。首先还是安装 **RcppArmadillo** 包，可与 **sf** 包同时安装。

```r
install.packages(c("RcppArmadillo", "sf"))
```

然后通过包管理器安装 GSL 库，以 Ubuntu 发行版为例，即使用如下命令。

```sh
sudo apt-get install libgsl-dev
```

其他发行版使用各自的包管理器安装即可。
依赖库安装好之后，使用如下命令安装源码包：

```sh
R CMD INSTALL GWmodel3_3.0-0.tar.gz
```

# 使用

**GWmodel3** 为地理加权建模核心库 [libgwmodel](https://github.com/GWmodel-Lab/libgwmodel) 提供了一套 R 语言接口。
与 GWmodel 相比，由于底层逻辑发生了很大的变化，因此在用法上也有较大改动。
当前在开发过程中，为了避免环境冲突，使用如下方式导入包。

```{r}
library(GWmodel3)
```

各函数的具体使用方法请参考教程，或者函数文档。

# 问题反馈

如遇到问题，请前往 [Issues](https://github.com/GWmodel-Lab/GWmodel3/issues) 页面提交问题。

