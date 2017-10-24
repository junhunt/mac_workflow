# Terminal

## 常用操作
- 查看当前目录下所有文件（夹）的大小  

```
du -sh *
```

- 命令生成一个 128bit UUID  

```
uuidgen
```

- 访问hosts  

```
sudo vi /etc/hosts
```

- 刷新本地DNS缓存  

```
sudo killall -HUP mDNSResponder
```

- 是否显示隐藏文件  
需要重新运行 Finder：[cmd-option-Esc --> Finder --> 重新启动]  

```
// 显示
defaults write com.apple.finder AppleShowAllFiles -bool true
// 隐藏
defaults write com.apple.finder AppleShowAllFiles -bool false
```

- 计算源码行数

```
http://www.jianshu.com/p/e5063e5f4fd7
find . "(" -name "*.m" -or -name "*.mm" -or -name "*.cpp" -or -name "*.h" -or -name "*.rss" ")" -print | xargs wc -l
s
```
