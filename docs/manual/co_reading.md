---
sidebar_position: 7
---

# Co-reading Mode (alpha)

:::tip
Co-reading mode currently only supports PDF files, opened using the pre-installed "Preview.app".

:::

Co-reading mode offers a deeper "interaction with the same file". After activating co-reading mode, the window will split horizontally, with the PDF reader on the right. Whenever you ask the AI ​​a question, it will first take a screenshot of the current PDF reader interface, sharing its view with you. This ensures that even images and tables are included, helping it to better synthesize answers.

![AI Co-reading PDF with You](/img/co_reading01.png)

- After entering co-reading mode, the system will continuously check the PDF reader window. If it is obscured or minimized, appropriate handling logic will be implemented to ensure a smooth co-reading experience.

- If the PDF reader window is minimized during the mode's operation, a prompt will appear reminding the user whether to exit co-reading mode.

- If the PDF reader window is obscured by other windows during the mode's operation, those windows will be automatically brought to the forefront when taking screenshots of the question and answer.

:::warning

- Sharing your reading progress and view requires "screen recording" permission

:::