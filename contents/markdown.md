# Markdown

### 相对路径跳转项目內其他文件

```
[查看常用软件](usual_software.md)
[查看README](../README.md)
```

[查看常用软件](usual_software.md)

[查看README](../README.md)

### 相对路径插入图片

```
![](images/demo.png)
```

![](../images/demo.png)

### 锚点

```
点击[[锚点名]](#footnode)会跳到下面我的示例的位置。

[锚点名]<a name="footnode"></a>我的示例。

# 注意，如果标题锚点字母全部为小写？，标题锚点支撑中文
[回到顶部](#markdown)
[转到相对路径插入图片](#相对路径插入图片)
```

点击[[锚点名]](#footnode)会跳到下面**我的示例**的位置。

$

$

$

$

$

[我的示例]<a name="footnode"></a>

[回到顶部](#markdown)

[转到**相对路径插入图片**](#相对路径插入图片)

### 可以将 URL 和描述标题分离

```
[查看常用软件](usual_software.md)
分离为
[查看常用软件][check_software]
[check_software]:usual_software.md

这样就可以使用 [查看常用软件][check_software] 多次使用这个链接了，可以将链接放在一个地方，方便管理
```
[常用软件][check_software] 和 [查看常用软件][check_software] 使用同一个标识符，可以方便管理地址。

## MORE
[check_software]:usual_software.md
[README文件语法解读](https://github.com/guodongxiaren/README)
