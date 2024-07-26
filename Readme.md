## Overview
This documentation outlines the process and technologies used in the development of a Retriever-Augmented Generation (RAG) model. The project involved extracting data from PDFs, summarizing content, and creating custom retrievers to improve information retrieval.

## Pipeline Description
![Pipeline Flowchart](path_to_image.png)

### Extract Data
- **Tool Used**: unstructured.io library
- **Description**: Data extraction from PDF files to formats such as text, images, and tables.
- **Challenges**: This method resulted in dependency conflicts with other installations but provided superior output quality compared to alternative methods.

### Process Tables and Text
- **Tools Used**: Langchain
- **Processes**:
  - Summarization of text and tables in batches.
  - Conversion of tables from HTML to JSON format.
  - Storage of processed files.

### Generate Image Summaries
- **Model Used**: MILVLG VLM
- **Advantages**: Compared to other models, MILVLG VLM provided the best output and utilized less storage space.

### Created Retriever
- **Development**:
  1. **Langchain Multi Vector Retriever**:
     - Mapped each text chunk to its corresponding chunk.
  2. **LLaMA Index**:
     - Extended metadata to add summaries and tables as metadata to relevant nodes.
  3. **Custom Retriever**:
     - Added embeddings of the generated summaries as separate nodes using the LLaMA index relationships (`main_node.relationships[NodeRelationship.CHILD]`).
     - Attempted to connect the nodes and create a functional retriever.

### Challenges and Limitations
- **Incomplete Retriever**:
  - The final retriever was not completed as intended, leading to unformatted and suboptimal output.

## Conclusion
This project demonstrates the integration of various technologies to enhance data processing and retrieval capabilities. Future work will focus on resolving the existing issues with the custom retriever and optimizing the overall system for better performance.

## Kaggle Link

You can find the notebook on Kaggle [here](https://www.kaggle.com/code/arunraghavs/otsukafinal).
 - Restart the kernel and clear all outputs after installing all requirements to prevent any errors
