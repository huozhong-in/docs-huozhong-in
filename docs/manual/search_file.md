---
sidebar_position: 3
---

# Search for Files by Keyword

The file list area is located at the top center of the main interface. You can search by keyword using the full path, which can be either the filename or the folder name containing the file. Note that searching by file content is not supported.

:::tip The file type extensions that can be searched are configured in [File Recognition Rules](/docs/manual/configuration)

:::

![Active File Search](/img/search_file01.png)

1. Press cmd+k to quickly locate the search bar, enter the path keyword, and press Enter to search.

2. Once the file appears in the list, you can directly open Finder and locate the file.

## File List Floating Menu

Different floating menus are available for different file types in the file list.

- Image Q&A, supporting `["png", "jpg", "jpeg", "gif", "webp"]` formats

- Pinned Files, supporting `['pdf', 'docx', 'pptx', 'txt', 'md', 'markdown']` document formats

> The purpose of the pin operation is to associate the file with the current conversation/session and simultaneously begin analyzing the file content to build a knowledge index. See [Multimodal Retrieval](/docs/manual/pin_file) for details.

- Co-reading mode, currently only available for PDFs. See [Co-reading Mode](/docs/manual/co_reading) for details.
