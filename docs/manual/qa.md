---
sidebar_position: 8
---

# Frequently Asked Questions

## Q&A

### Network Access Issues in China

Normal use of KF requires direct network access to `pypi.python.org` and `huggingface.co`. If you encounter issues, try the following methods:

- **macOS System Global Proxy**

Use your local proxy software (such as Clash) to "set as system proxy," allowing applications that support this protocol (including KF) to forward requests through the proxy, bypassing network restrictions.

- **Configure Proxy for KF via Environment Variables**

```sh
https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890 open /Applications/KnowledgeFocus.app
```

- **Specify Mirror Sites via Environment Variables**

```sh
UV_DEFAULT_INDEX="https://pypi.tuna.tsinghua.edu.cn/simple" HF_ENDPOINT="https://hf-mirror.com" open /Applications/KnowledgeFocus.app
```

- **Use Proxy for Commercial Model API Requests**

After entering the main interface, you can configure the proxy on the configuration page and specify that model provider requests should go through the proxy.

![set proxy](/img/qa01.png)

### Computer Overheating, Fan Running at High Speed

> File tagging is automatic. Tagging each file that passes the initial screening and is confirmed to be a personal knowledge file helps discover historical knowledge more effectively. You can see the overall progress on the interface.

### Multimodal Vectorization is Too Slow

> This process is computationally intensive, involving parsing, extraction, chunking, vectorization, and a series of database operations. With PDFs that have many pages, it averages about 10 seconds per page. We recommend using idle time to pin files you're likely to use soon. The app will process them sequentially, and then you can use them directly in any conversation.

### Poor Quality Responses from Small Models

> This is a limitation of small models. We recommend using a combination of small and large models by configuring an online commercial large model API. Specifically, configure a sufficiently capable commercial model API for the "multimodal answer synthesis" scenario—this is part of a cloud-edge integrated agent orchestration strategy.