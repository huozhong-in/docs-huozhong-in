---
sidebar_position: 8
---

# 常见问题

## Q and A

### 中国境内使用KF遇到障碍

正常使用KF需要网络能直达`pypi.python.org`和`huggingface.co`，如果遇到问题以下方法供您参考

- macOS系统全局代理服务器

通过本机的智能代理软件(如clash)“设置为系统代理”，让支持此协议的应用(包括KF)都通过智能代理软件转发请求，越过网络障碍。

- 通过环境变量单独给KF设置代理

`https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890 open /Applications/KnowledgeFocus.app`

- 通过环境变量指定国内镜像站

`UV_DEFAULT_INDEX="https://pypi.tuna.tsinghua.edu.cn/simple" HF_ENDPOINT="https://hf-mirror.com" open /Applications/KnowledgeFocus.app`

- 在请求商业模型API时使用代理

进入主界面后可在配置页配置代理，并指定模型提供商请求走代理

![set proxy](/img/qa01.png)

### 电脑发热厉害，风扇狂转

> 给文件打标签是自动的，尽量给每一个经过粗筛确认后属于个人知识文件的打上标签可以尽量好的发现历史知识。从界面可以看到有总体进度。

### 多模态向量化太慢

> 这个技术处理过程工作量大，涉及到解析、抽取、分块、向量化和一系列数据库操作，尤其是PDF页多的情况下，平均10秒一页。建议利用闲时把最近可能要用的文件依次做pin的动作，本应用会依次处理，然后可以在任意会话中直接使用。

### 小模型回复质量不好

> 这是小模型的局限性，建议大小模型结合使用，配置在线的商业大模型API。推荐在“多模态答案合成”场景配置成够聪明的商业模型API，这属于云端一体的智能体编排策略。