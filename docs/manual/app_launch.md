---
sidebar_position: 2
---

# Startup Process

To provide a good user experience, we implement the complex requirements for the runtime environment during the startup phase.

## The startup process consists of four steps

### 1. Automatic Creation of the Python Runtime Environment

#### a) Normal Situation

- The first startup will fetch the required runtime libraries, which takes a relatively long time. Progress details can be viewed in the data observation window.

- For subsequent startups, the runtime environment will be checked and updated, significantly reducing the time.

![Creating the Python Runtime Environment](/img/app_launch01.png)

#### b) Error Handling

If you find no progress change or download failure in the observation window for a long time, it is likely that there is an obstacle to directly accessing pypi.python.org. Please try downloading from a domestic mirror site using the following methods.

Open the Terminal app, copy the following two commands one by one, paste them into the prompt, and press Enter to execute:

1. 

```sh
 cp -f /Applications/KnowledgeFocus.app/Contents/Resources/api/pyproject.toml ~/Library/Application\ Support/knowledge-focus.huozhong.in/
```

2.
```sh
UV_DEFAULT_INDEX="https://pypi.tuna.tsinghua.edu.cn/simple" /Applications/KnowledgeFocus.app/Contents/MacOS/uv sync --index-strategy unsafe-best-match --directory ~/Library/Application\ Support/knowledge-focus.huozhong.in/
```

You can replace with other `pypi` mirror site.

3.
After successful execution, completely exit KnowledgeFocus and restart it.

### 2. Start the Python Data Interface Server

- The first startup requires compiling code into a runtime cache, which takes a long time. Please be patient.

- Subsequent startups will significantly reduce the time.

![First startup of the Python backend requires compilation time|20](/img/app_launch02.png)

### 3. Download the All-in-One Mini-Model

"All-in-one" means it can tag files based on their content, create knowledge indexes for text, images, and tables within files, recognize image content for question answering, and remove sensitive information from knowledge fragments. It prioritizes utilizing local computing power for **capable** tasks, ensuring sensitive data does not leave the local machine.

a) Normal Situation

- The first download takes a long time. Please be patient.

- Subsequent startups will skip this step.

b) Error Handling

If you observe no progress or download failure in the monitoring window for an extended period, it is likely due to obstacles accessing huggingface.co directly. Please try downloading from a domestic mirror site using the following methods.

1. Open the Terminal app, copy the following command, paste it into the prompt, and press Enter to execute:

```sh
sh /Applications/KnowledgeFocus.app/Contents/Resources/api/download-model.sh
```

2. After successful execution, completely exit KnowledgeFocus and restart it.

### 4. Obtain "Full Disk Access"

This app can only read your files after obtaining permission. It can help users search and discover files and knowledge by indexing them. Rest assured, KF will not delete or modify your file content; it only reads them.

- If the interface prompts insufficient permissions, click the button to open system settings.

- Find KnowledgeFocus in the list, or browse to `/Application/KnowledgeFocus.app` and grant permissions.

- After obtaining "Full Disk Access," you will be prompted to click the button to restart the application. Wait a moment. If you observe that KF does not start automatically, do so manually.

![Grant full disk access | 20](/img/app_launch04.png)