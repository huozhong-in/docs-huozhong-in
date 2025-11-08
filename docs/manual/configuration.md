---
sidebar_position: 6
---

# Configuration

## 1. Authorized Folders

To reduce noise interference and display only files containing "user-perceptible knowledge," KF's folder management design uses a combination of whitelists and blacklists.

### Whitelists and Blacklists

- Whitelist entries are folders that need to be scanned and monitored. The default whitelist consists of six common macOS folders: Desktop, Documents, Downloads, Pictures, Music, and Videos. You can also create new whitelist entries to specify any folder on the disk.

- The blacklist consists of folders that need to be excluded from the whitelist—folders you don't want KF to scan or monitor. This prevents files and content within these folders from being discovered and processed, and they won't be reflected in subsequent KF functions.

### Operating Mechanism

- Upon startup, a full scan of every folder in the whitelist is performed. Combining rules for extension filtering, excluded folders, bundle filtering, and blacklist subfolders, files that meet the criteria are saved to a "coarse-screened file results table" for further use.

- Monitor folder changes. Whenever files within a folder are modified (added, modified, deleted), use four types of rules—extension filtering, excluded folders, bundle filtering, and blacklisting—to determine the changes and appropriately synchronize them to the aforementioned data table for further utilization.

## 2. File Scanning Rules

### a) File Extensions

Which extensions carry knowledge and need to be searchable and explicitly usable?

### b) File Categories

Used to help manage file extensions.

### c) Filtering Rules

Filter "useless" folder names, such as the `.git` folder in open-source projects or the `node_modules` runtime library folder in front-end projects. These folders do not contain user-generated knowledge files.

### d) Bundle-like Files

macOS has a special type of file that appears to be a file but is actually a folder. It should be treated as a whole—the files inside do not need to be scanned, and changes to those files should not be monitored; only changes to the "shell" metadata are needed.

## 3. Configuring Model Parameters

### a) Associating Scenarios

This requires configuring which model provides each capability.

- Automatic file tagging depends on the model's structured data output capability.

- Multimodal vectorization depends on visual and vectorization capabilities.

- Multimodal retrieval depends on text and visual capabilities.

### b) Provider Parameters

Configure the connection parameters for your local third-party software or online commercial model API.

Note that when using certain providers within China, you need to enable the "Use proxy to forward requests" option and ensure that the proxy server itself is functioning correctly.

### c) Retrieving the Model List

Retrieve a list of currently available models from the provider API, including capabilities, context windows, and other preset parameters.

### d) Testing Model Capabilities

Test to confirm whether the above models have text question answering capabilities, structured data output capabilities, visual capabilities, and vectorization capabilities.

The model name will only appear in the "Associated Scenarios" candidate entries after a successful test.