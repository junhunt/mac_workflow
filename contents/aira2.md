# Aria2 - The next generation download utility

> aria2 是一个轻量级的多协议和多源的命令行下载工具。支持 **HTTP/HTTPS**, **FTP**, **SFTP**, **BitTorrent**, **Metalink**. 可以通过内建的 **JSON-RPC** 和 **XML-RPC**(interfaces?) 来使用

### install

```
brew isntall aria2
```

### 命令行模式

```
# Synopsis
aria2c [<OPTIONS>] [<URI>|<MAGNET>|<TORRENT_FILE>|<METALINK_FILE>]  ...

#Download from WEB:
$ aria2c http://example.org/mylinux.iso

#Download from 2 sources:
$ aria2c http://a/f.iso ftp://b/f.iso

#Download using 2 connections per host:
$ aria2c -x2 http://a/f.iso

#BitTorrent:
$ aria2c http://example.org/mylinux.torrent

#BitTorrent Magnet URI:
$ aria2c 'magnet:?xt=urn:btih:248D0A1CD08284299DE78D5C1ED359BB46717D8C'

#Metalink:
$ aria2c http://example.org/mylinux.metalink

#Download URIs found in text file:
$ aria2c -i uris.txt
```

### RPC Server 模式

aria 启动之后只会安静的等待下载请求，下载完成后也只会安静的驻留后台不会自动退出。

#### 配置文件：

- 在当前用户根目录下创建 **.aria2** 文件夹，并在里面创建 **aria2.conf**

  ```
  $ cd
  $ mkdir .aria2
  $ touch .aria2/aria2.conf

  # 注意：aria2.conf 不是必须创建在这里的，可以随便放在哪里，只要后面开启服务的时候指向它的位置就 OK 了。
  ```

- 将下面配置参数写入 aria2.conf, 其中 **/User/xxx/Downloads** 是下载保存的路径，可以修改为任意你喜欢的位置，如果没有该文件夹将自动创建。

  ```
  #用户名
  #rpc-user=user
  #密码
  #rpc-passwd=passwd
  #上面的认证方式不建议使用,建议使用下面的token方式
  #设置加密的密钥
  #rpc-secret=token
  #允许rpc
  enable-rpc=true
  #允许所有来源, web界面跨域权限需要
  rpc-allow-origin-all=true
  #允许外部访问，false的话只监听本地端口
  rpc-listen-all=true
  #RPC端口, 仅当默认端口被占用时修改
  #rpc-listen-port=6800
  #最大同时下载数(任务数), 路由建议值: 3
  max-concurrent-downloads=5
  #断点续传
  continue=true
  #同服务器连接数
  max-connection-per-server=5
  #最小文件分片大小, 下载线程数上限取决于能分出多少片, 对于小文件重要
  min-split-size=10M
  #单文件最大线程数, 路由建议值: 5
  split=10
  #下载速度限制
  max-overall-download-limit=0
  #单文件速度限制
  max-download-limit=0
  #上传速度限制
  max-overall-upload-limit=0
  #单文件速度限制
  max-upload-limit=0
  #断开速度过慢的连接
  #lowest-speed-limit=0
  #验证用，需要1.16.1之后的release版本
  #referer=*
  #文件保存路径, 默认为当前启动位置
  dir=/User/xxx/Downloads
  #文件缓存, 使用内置的文件缓存, 如果你不相信Linux内核文件缓存和磁盘内置缓存时使用, 需要1.16及以上版本
  #disk-cache=0
  #另一种Linux文件缓存方式, 使用前确保您使用的内核支持此选项, 需要1.15及以上版本(?)
  #enable-mmap=true
  #文件预分配, 能有效降低文件碎片, 提高磁盘性能. 缺点是预分配时间较长
  #所需时间 none < falloc ? trunc << prealloc, falloc和trunc需要文件系统和内核支持
  file-allocation=prealloc
  ```

#### 开启服务

```
aria2c --conf-path=<PATH>

#PATH 是 aria2.conf 的绝对路径，如："/Users/xxx/.aria2/aria2.conf"
#使用 -D 参数使 Aria2 在后台运行，即使关闭终端也不会停止运行
#aria2c --conf-path="/Users/Jun/.aria2/aria2.conf" -D
```

#### [网盘助手安装](https://github.com/acgotaku/BaiduExporter)

### MORE

[aria2](https://aria2.github.io/)

[aria2 Manual](https://aria2.github.io/manual/en/html/)

[**BaiduExporter**](https://github.com/acgotaku/BaiduExporter)

[[使用Aria2下载百度网盘和115的资源](https://blog.icehoney.me/posts/2015-01-31-Aria2-download)](https://blog.icehoney.me/posts/2015-01-31-Aria2-download)

[Aria2 & YAAW 使用说明](http://aria2c.com/usage.html)

[aria2gui](https://github.com/yangshun1029/aria2gui)

[metalinker](http://www.metalinker.org/)