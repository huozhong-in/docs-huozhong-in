---
sidebar_position: 8
---

# Q and A

## Frequently Asked Questions

### Obstacles to using KF within China

Normal use of KF requires a direct network connection to `pypi.python.org` and `huggingface.co`. If you encounter problems, the following methods are for your reference:

- macOS System Global Proxy Server

Use your local smart proxy software (such as Clash) to "set it as the system proxy," allowing applications that support this protocol (including KF) to forward requests through the smart proxy software, thus overcoming network obstacles.

- Configure a proxy for KF separately via environment variables

`https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890 open /Applications/KnowledgeFocus.app`

- Specify a domestic mirror site via environment variables

`UV_DEFAULT_INDEX="https://pypi.tuna.tsinghua.edu.cn/simple" HF_ENDPOINT="https://hf-mirror.com" open /Applications/KnowledgeFocus.app`

- Use a proxy when requesting business model APIs

After entering the main interface, you can configure the proxy on the configuration page and specify that model provider requests should go through the proxy

![set proxy](/img/qa01.png)

### Computer overheating, fan spinning wildly

> Document tagging is automatic. Tagging each document that has passed the initial screening and is confirmed to belong to personal knowledge can help discover historical knowledge more effectively. The overall progress is displayed on the interface.

### Multimodal Vectorization is Too Slow

> This technology is labor-intensive, involving parsing, extraction, segmentation, vectorization, and a series of database operations, especially with many PDF pages, averaging 10 seconds per page. It is recommended to use idle time to pin the most recently used files sequentially. The application will process them sequentially, and then they can be used directly in any session.

### Poor Quality of Small Model Responses

> This is a limitation of small models. It is recommended to use a combination of large and small models and configure an online commercial large model API. It is recommended to configure a sufficiently intelligent commercial model API in the "multimodal answer synthesis" scenario, which is part of a cloud-integrated intelligent agent orchestration strategy.