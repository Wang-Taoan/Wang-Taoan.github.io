# Homebrew使用

核心概念：

- `Casks` :安装 macOS native 应用的扩展，你也可以理解为有图形化界面的应用。
- `Formulae`: 安装包的描述文件，formulae 为复数
- `tap`: 下载源，可以类比于 Linux 下的包管理器 repository



安装软件：`brew install`

搜索软件：

- 命令行：`brew seach [关键词]`
- 网页搜索：<https://formulae.brew.sh/>

更新软件：`brew update [指定]`

卸载: `brew uninstall [软件名]`

清理系统中所有软件的历史版本:`brew cleanup`

检查 Hombrew 环境:`brew doctor`

---

添加一个新的tap:`brew tap [user/repo]`

常用的tap：Caskroom、homebrew-cask-fonts（字体用的）

> Caskroom allows you to install large binary files via a command-line tool. You can for example install applications like Google Chrome，我们就可以安装一些有图形化界面的软件了，比如 VSCode、Typora 等软件。

使用起来也非常简单，最新版 Homebrew 中，你可以直接使用 `brew <install> --cask` 来安装特定的软件，homebrew 会自动安装 Caskroom。

使用网页搜索 Caskroom 的软件:<https://formulae.brew.sh/cask/>

