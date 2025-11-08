---
sidebar_position: 2
---

# 启动过程

为了给用户良好的使用体验，我们把对运行环境的复杂要求放在启动期实现。

## 启动过程分为四步

### 1. 自动创建Python运行环境

#### a) 正常情况
- 首次启动会拉取所需的运行库耗时较长，可在数据观察窗看到进度细节。
- 非首次启动则会检查和更新运行环境，时间将会大大缩短。

![创建Python运行环境](/img/app_launch01.png)


#### b) 错误应对

如果查看观察窗发现长时间无进度变化或下载失败，很可能是直接访问pypi.python.org有障碍，请尝试通过以下方法从国内镜像站下载。

打开“终端”App，依次复制以下两条命令并粘贴到其提示符后回车执行

1.
```sh
cp -f /Applications/KnowledgeFocus.app/Contents/Resources/api/pyproject.toml ~/Library/Application\ Support/knowledge-focus.huozhong.in/

```

2.
```sh
UV_DEFAULT_INDEX="https://pypi.tuna.tsinghua.edu.cn/simple" /Applications/KnowledgeFocus.app/Contents/MacOS/uv sync --index-strategy unsafe-best-match --directory ~/Library/Application\ Support/knowledge-focus.huozhong.in/

```
3.

成功后彻底退出KnowledgeFocus并重新启动。


### 2. 启动Python数据接口服务器
    - 首次启动需要编译代码成为运行缓存，耗时较长，请耐心等待。
    - 再次启动时间将会大大缩短。

![首次启动Python后端需要编译时间|20](/img/app_launch02.png)

### 3. 下载全能小模型

“全能”是指能根据文件内容打标签，能给文件内的文字、图片、表格建立知识索引，能识别图片内容进行问答，能去除知识片段中的敏感信息。它能优先利用本地算力进行**力所能及的**工作，使敏感数据不出本机。

a) 正常情况

- 首次下载耗时较长，请耐心等待。
- 再次启动将跳过此步骤。

b) 错误应对

如果查看观察窗发现长时间无进度变化或下载失败，很可能是直接访问huggingface.co有障碍，请尝试通过以下方法从国内镜像站下载。

1. 打开“终端”App，复制以下命令并粘贴到其提示符后回车执行

```sh
sh /Applications/KnowledgeFocus.app/Contents/Resources/api/download-model.sh
```

2. 成功后彻底退出KnowledgeFocus并重新启动。

### 4. 获得授权“完全磁盘访问权限”

本App获得权限后才能读取您的文件，可以通过给文件建立索引的方式帮用户搜索和发现文件及知识。请放心KF不会删除和改动您的文件文容，仅仅是读取。


- 界面提示权限不足，点击按钮打开系统设置
- 找到列表中的KnowledgeFocus，或浏览定位到`/Application/KnowledgeFocus.app`并授权
- 获得“完全磁盘访问权限”后会提示点击按钮重启应用，稍等如果观察到KF没有自动启动，则手动做。

![授予完全磁盘访问权限|20](/img/app_launch04.png)