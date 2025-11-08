---
sidebar_position: 5
---

# Talking with Your Files

### Linking Files to Chat Sessions

#### 1. Pinned Files (Multimodal Vectorization)

"Pinned files" is an interactive method that links files to specific conversations. Essentially, it initiates multimodal vectorization of file content, extracting text, images, and tables from knowledge files into independent knowledge fragments, and then building a knowledge index for later retrieval during conversations.

![Linking files to conversations](/img/pin_file01.png)

#### 2. Multimodal Retrieval and Answer Synthesis

Multimodal retrieval allows you to find semantically relevant text fragments, image descriptions, and table descriptions, and locate the original text context, original image, and original table. This technology maximizes the retrieval of the most relevant knowledge from the entire database.

Based on the original knowledge retrieved, it is provided to a local all-around (primarily visual) mini-model or a business model API. Combined with external data tools such as search engines, high-quality, virtually hallucinatory responses are synthesized.

![Retrieving and Retrieving Knowledge Fragments](/img/pin_file02.png)

#### 3. Removing Sensitive Information from Knowledge Fragments (todo)

Before each submission to the business model API, the local mini-model desensitizes the knowledge fragments according to the **configuration item - data preprocessing strategy**, fully protecting data privacy while leveraging the power of the business model API.

- The data observation window is located at the bottom center of the main interface, showing the recall status of the knowledge fragments.

- Manual confirmation and review of the desensitization results are required before each submission.

#### 4. Using Tools

Searching the internet before synthesizing the answer can significantly improve response quality and reduce hallucinations.

The input area of ​​the conversation can optionally configure the search tool Tavily. Register on its official website and apply for a key to configure it.

#### 5. "AI Reads PDFs with You"

Furthermore, you can chat with AI while reading PDFs for a unique, companion-style reading experience. See [Co-reading Mode](/docs/manual/co_reading) for details.