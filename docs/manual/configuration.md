---
sidebar_position: 6
---

# Preferences

## 1. Authorized Folders

To reduce noise and focus on files containing "user-perceptible knowledge," KF uses a combination of whitelists and blacklists for folder management.

### Whitelists and Blacklists

- **Whitelist entries** are folders that need to be scanned and monitored. The default whitelist includes six common macOS folders: Desktop, Documents, Downloads, Pictures, Music, and Videos. You can also create new whitelist entries to specify any folder on your disk.

- **Blacklist entries** are folders within whitelist directories that should be excluded—folders you don't want KF to scan or monitor. Files and content within these folders won't be discovered or processed, and won't appear in any KF features.

### Operating Mechanism

- On startup, KF performs a full scan of every folder in the whitelist. Using rules for extension filtering, excluded folders, bundle filtering, and blacklist subfolders, files that meet the criteria are saved to a "coarse-screened file results table" for further use.

- KF monitors folder changes. Whenever files within a folder are modified (added, modified, or deleted), it uses four types of rules—extension filtering, excluded folders, bundle filtering, and blacklisting—to evaluate the changes and synchronize them to the data table accordingly.

## 2. File Scanning Rules

### a) File Extensions

Configure which file extensions contain knowledge and should be searchable and explicitly usable.

### b) File Categories

Used to help organize and manage file extensions.

### c) Filtering Rules

Filter out "unnecessary" folder names, such as the `.git` folder in open-source projects or the `node_modules` runtime library folder in front-end projects. These folders don't contain user-generated knowledge files.

### d) Bundle Files

macOS has a special type of file that appears as a single file but is actually a folder (bundle). These should be treated as a whole—the files inside don't need to be scanned, and changes to internal files shouldn't be monitored. Only changes to the bundle's metadata are tracked.

## 3. Model Configuration

### a) Associate Scenarios

Configure which model provides each capability:

- **Automatic file tagging** depends on the model's structured data output capability.
- **Multimodal vectorization** depends on visual and vectorization capabilities.
- **Multimodal retrieval** depends on text and visual capabilities.

### b) Provider Parameters

Configure connection parameters for local third-party software or online commercial model APIs.

Note: When using certain providers from within China, you may need to enable the "Use proxy to forward requests" option and ensure your proxy server is functioning correctly.

### c) Fetch Model List

Retrieve a list of currently available models from the provider API, including capabilities, context windows, and other preset parameters.

### d) Test Model Capabilities

Test to confirm whether the models have the required capabilities: text Q&A, structured data output, visual processing, and vectorization.

Model names will only appear in the "Associate Scenarios" candidate list after successful testing.