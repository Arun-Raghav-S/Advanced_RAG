# Advanced RAG Techniques 🛠️
An in-depth look at advanced methods for implementing Retriever-Augmented Generation (RAG) models.

## Overview 📜
This documentation details the processes and technologies used to develop a RAG model. The project focuses on extracting data from PDFs, summarizing content, and creating custom retrievers to enhance information retrieval capabilities.

## Pipeline Description 🚀
![Pipeline Flowchart](https://github.com/user-attachments/assets/6084085c-75ba-4581-b675-1224d36b894f)

### Extract Data 📂
![Data Extraction Process](https://github.com/user-attachments/assets/e37df02f-65ff-4eb2-bbfd-2edf52c19953)
- **Tool Used**: unstructured.io library
- **Description**: Extraction of data from PDF files to text, images, and tables.
- **Challenges**: Dependency conflicts were encountered with other installations, although this method provided the best output quality.

### Process Tables and Text 📊
![Text Processing](https://github.com/user-attachments/assets/7ca7db93-ffa0-4848-a180-66da9fc2577e)
- **Tools Used**: Langchain
- **Processes**:
  - Batch summarization of text and tables.
  - Conversion of tables from HTML to JSON.
  - Storage of processed files.

### Generate Image Summaries 🖼️
![Summary Generation](https://github.com/user-attachments/assets/820c69e6-d45e-47a0-9e9d-c84f8c4fd048)
![Additional Image Summary](https://github.com/user-attachments/assets/03c876d7-608a-4bea-a649-98a451df4d06)
- **Model Used**: [MILVLG/imp-v1-3b](https://huggingface.co/MILVLG/imp-v1-3b)
- **Advantages**: Superior performance and reduced storage space compared to other models.

### Created Retriever 🗂️
- **Development**:
  1. **Langchain Multi Vector Retriever**:
     ![Multi Vector Retriever](https://github.com/user-attachments/assets/5daa4589-86c2-4ed5-bf1e-b2db28e1d303)
     - Each text chunk is mapped to its corresponding chunk.
  2. **LLaMA Index**:
     ![LLaMA Index](https://github.com/user-attachments/assets/14814bc1-694c-46b2-a7b2-8d9560e52b63)
     - Summaries and tables added as metadata to relevant nodes.
  3. **Custom Retriever**:
     ![Custom Retriever](https://github.com/user-attachments/assets/710898c8-05dc-41fb-9e44-66c7146df70c)
     - Embeddings of the generated summaries added as separate nodes.
     ![Retriever Nodes](https://github.com/user-attachments/assets/09c76fd5-ad28-453e-a69e-307e6fc1eef7)
     - Connection of nodes attempted to create a functional retriever.

### Challenges and Limitations ⚠️
- **Incomplete Retriever**: The final retriever was not completed as intended, which led to unformatted and suboptimal output.

## Conclusion 🎯
This project integrates various advanced technologies to improve data processing and retrieval. Future efforts will aim to resolve the issues with the custom retriever and optimize the system for enhanced performance.

## Explore More on Kaggle 📊
You can explore the Kaggle notebook for this project [here](https://www.kaggle.com/code/arunraghavs/otsukafinal).
- **Note**: Restart the kernel and clear all outputs after installing all requirements to prevent any errors.

