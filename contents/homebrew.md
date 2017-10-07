# Homebrew - The missing package manager for macOS

Homebrew 是 Mac 下的应用管理工具（？），通过命令行安装和管理软件。需要安装 Xcode。

极客学院是中国最大的 IT 职业在线教育平台。[[锚点名]](#footnode)

### 安装和卸载

```
# 安装
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# 卸载
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
```

### 常用操作

```
# 帮助：https://docs.brew.sh
brew help

# 更新 brew
brew update

# 查看过期 packages
brew outdated

# 更新所有 packages
brew upgrade

# 更新指定 package
brew upgrade <formula>

# 固定 package 版本，不让其更新
brew pin <formula>

# 解除固定 package 版本
brew unpin <formula>

# 卸载 package
brew uninstall <formula> --force

# 清除旧版 package，**更新版本默认不会卸载旧版本**
# 查看那些会被清除
brew cleanup -n
# 清除所有
brew cleanup
# 清除指定 package
brew cleanup <formula>

# 查看 packages 下载到哪里了，通常是：~/Library/Caches/Homebrew
brew --cache
```

### Homebrew-Cask

> “To install, drag this icon…” no more!

Homebrew-Cask 拓展自(extend) Homebrew, 用于安装 macOS GUI 软件，使用方式也和Homebrew 基本相同， **brew** 后加一个 **cask**， 比如安装命令如下：

```
brew cask install <formula>
```

### 常用 packages

```
# Homebrew-Cask
- aria2
- carthage
- tree
- python3
- cocoapods
- git
- wget
- shadowsocks-libev

# Homebrew-Cask
- iina
- atom
- google-chrome
- iterm2
- sourcetree
- shadowsocksx-ng
- lantern
- licecap
- flux
```

[锚点名]<a name="footnode"></a>我的示例。

### MORE

[Homebrew官网](https://brew.sh/)

[Homebrew's Github](https://github.com/Homebrew/brew)

[FAQ](https://docs.brew.sh/FAQ.html)

[Homebrew-Cask](https://caskroom.github.io/)

[替换及重置Homebrew默认源](https://lug.ustc.edu.cn/wiki/mirrors/help/brew.git)

[Homebrew Bottles源](https://lug.ustc.edu.cn/wiki/mirrors/help/homebrew-bottles)
