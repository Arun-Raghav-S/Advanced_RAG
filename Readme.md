## Overview
This documentation outlines the process and technologies used in the development of a Retriever-Augmented Generation (RAG) model. The project involved extracting data from PDFs, summarizing content, and creating custom retrievers to improve information retrieval.

## Pipeline Description
![Pipeline Flowchart](https://github.com/user-attachments/assets/6084085c-75ba-4581-b675-1224d36b894f)

### Extract Data
![image](https://github.com/user-attachments/assets/e37df02f-65ff-4eb2-bbfd-2edf52c19953)

- **Tool Used**: unstructured.io library
- **Description**: Data extraction from PDF files to formats such as text, images, and tables.
- **Challenges**: This method resulted in dependency conflicts with other installations but provided superior output quality compared to alternative methods.

### Process Tables and Text
![image](https://github.com/user-attachments/assets/7ca7db93-ffa0-4848-a180-66da9fc2577e)

- **Tools Used**: Langchain
- **Processes**:
  - Summarization of text and tables in batches.
  - Conversion of tables from HTML to JSON format.
  - Storage of processed files.

### Generate Image Summaries
![image](https://github.com/user-attachments/assets/820c69e6-d45e-47a0-9e9d-c84f8c4fd048)
![image](https://github.com/user-attachments/assets/03c876d7-608a-4bea-a649-98a451df4d06)


- **Model Used**: [💻MILVLG/imp-v1-3b](https://huggingface.co/MILVLG/imp-v1-3b)
- **Advantages**: Compared to other models, MILVLG VLM provided the best output and utilized less storage space.

### Created Retriever


- **Development**:
  1. **Langchain Multi Vector Retriever**:![image](https://github.com/user-attachments/assets/5daa4589-86c2-4ed5-bf1e-b2db28e1d303)
     - Mapped each text chunk to its corresponding chunk.
  2. **LLaMA Index**:![image](https://github.com/user-attachments/assets/14814bc1-694c-46b2-a7b2-8d9560e52b63)
     - Extended metadata to add summaries and tables as metadata to relevant nodes.
  3. **Custom Retriever**:
     -  ![image](https://github.com/user-attachments/assets/710898c8-05dc-41fb-9e44-66c7146df70c)
     - Added embeddings of the generated summaries as separate nodes using the LLaMA index relationships (`main_node.relationships[NodeRelationship.CHILD]`).![image](https://github.com/user-attachments/assets/09c76fd5-ad28-453e-a69e-307e6fc1eef7)
     - Attempted to connect the nodes and create a functional retriever.

### Challenges and Limitations
- **Incomplete Retriever**:
  - The final retriever was not completed as intended, leading to unformatted and suboptimal output.

## Conclusion
This project demonstrates the integration of various technologies to enhance data processing and retrieval capabilities. Future work will focus on resolving the existing issues with the custom retriever and optimizing the overall system for better performance.

## Kaggle Link

You can find the notebook on Kaggle [here](https://www.kaggle.com/code/arunraghavs/otsukafinal).
 - Restart the kernel and clear all outputs after installing all requirements to prevent any errors
