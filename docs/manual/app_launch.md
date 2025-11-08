---
sidebar_position: 2
---

# Startup Process

The startup process consists of four steps. To simplify the software logic, complex runtime environment requirements are implemented during startup.

- Automatically create the Python runtime environment

- The first startup will fetch the necessary runtime libraries, which takes a relatively long time. Progress details can be viewed in the data observation window.

- Subsequent startups will check and update the runtime environment, significantly reducing the time.

- Manual operation method (manual): Ensure pyproject.toml is present, uv sync --

- ​​Start the Python data interface server

- The first startup requires compiling code into a runtime cache, which takes a relatively long time.

- Subsequent startups will significantly reduce the time.

- Download the all-in-one small model

- The first download takes a relatively long time. It prioritizes utilizing local computing power for **capable** tasks, ensuring sensitive data does not leave the local machine.

- All-in-one: It can tag files based on their content, create knowledge indexes for text, images, and tables within files, recognize image content for question answering, and remove sensitive information from knowledge fragments.

- Manual operation method (manual): download-model.sh

- Request "full disk access permissions".

- This app needs permission to read your files. It can help users search and discover files and knowledge by indexing them. Rest assured, KF will not delete or modify your file content; it only reads them.

- If the interface prompts insufficient permissions, click the button to open system settings.

- Navigate to `/Application/KnowledgeFocus.app` and grant permissions.

- After obtaining "Full Disk Access," you will be prompted to click the button to restart the application. Wait a moment. If KF does not start automatically, do so manually.