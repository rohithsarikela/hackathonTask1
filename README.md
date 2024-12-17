Chat with PDF using RAG Pipeline
Overview
This project implements a Retrieval-Augmented Generation (RAG) Pipeline to interact with semi-structured data in PDF files. It allows users to query PDF content, compare values across data points, and extract tables seamlessly. The system leverages Natural Language Processing (NLP) techniques, embedding models, and vector search for efficient retrieval and accurate answers.

Features
Data Ingestion

Accepts PDF files with semi-structured data.
Extracts text and chunks it for better granularity.
Converts chunks into embeddings using a pre-trained model (all-MiniLM-L6-v2).
Stores embeddings in a FAISS vector database for efficient similarity search.
Query Handling

Accepts natural language questions from the user.
Performs similarity search to retrieve relevant chunks.
Uses a Large Language Model (LLM) (e.g., t5-small) to generate detailed answers.
Comparison Queries

Allows users to compare specific values or terms across multiple queries.
Outputs structured responses in bullet points or tabular format.
Extract Tabular Data

Extracts and displays tables from a specific page in the PDF.
Technologies Used
PyPDF2: Extract text and data from PDF files.
FAISS: Vector database for similarity-based retrieval.
sentence-transformers: Pre-trained models for generating embeddings.
transformers: LLM-based text generation pipeline (e.g., t5-small).
requests: Downloads PDF files from a given URL.
Python: Core programming language.
Setup Instructions
Step 1: Clone the Repository
bash
Copy code
git clone https://github.com/<your-username>/pdf-chat-rag.git
cd pdf-chat-rag
Step 2: Install Dependencies
Install the required libraries using pip:

bash
Copy code
pip install PyPDF2 faiss-cpu sentence-transformers transformers requests
Usage
Run the script:

bash
Copy code
python main.py
Follow the interactive menu to perform tasks:

mathematica
Copy code
Menu Options:
1. Ask a question
2. Perform a comparison query
3. Extract tabular data from a page
4. Exit
Examples
1. Ask a Question
Input: How much money does the family spend on food if their yearly income is $31,000?
Output:
ruby
Copy code
**Question:** How much money does the family spend on food if their yearly income is $31,000?  
**Answer:** The family spends $7750 on food annually.
2. Perform a Comparison Query
Input:
graphql
Copy code
How many queries for comparison? 2  
Query 1: Spending on Food  
Query 2: Spending on Housing  
Output:
markdown
Copy code
**Comparison:**
- Food: $7750  
- Housing: $8060  
3. Extract Tabular Data
Input: Page number 6
Output:
yaml
Copy code
Extracted Table Data:
Year       2010       2011       2012       2013       2014       2015  
Manufacturing   4992521    5581942    5841608    5953299    6047477    5829554  
Finance         4522451    4618678    4797313    5031881    5339678    5597018  
...

How It Works

PDF Processing

Extracts text from the PDF and splits it into manageable chunks (default size: 500 characters).
Embedding Creation

Converts text chunks into vector embeddings using the sentence-transformers library.
Vector Storage

Stores the embeddings in a FAISS vector database for fast similarity-based retrieval.
Question Answering

User queries are converted into embeddings and compared with stored chunks.
The most relevant chunks are passed to a summarization model (t5-small) for generating answers.
Comparison Queries

Handles multiple queries, extracts relevant data, and formats the response for easy comparison.
Tabular Data Extraction

Extracts tables or structured text from specified pages using PyPDF2.
Limitations
The LLM has a 512-token input limit, which may truncate lengthy chunks.
Complex tables with inconsistent formatting might require additional preprocessing.
Future Enhancements
Support for multiple PDF files simultaneously.
Use larger models (e.g., GPT-4) for improved response quality.
Improved table extraction with tools like camelot or tabula.
License
This project is licensed under the MIT License.

Contributing
Contributions are welcome! If you'd like to improve this project, submit a pull request or open an issue.

Author
Developed by SARIKELA ROHITH.
Feel free to connect with me on GitHub! 🚀

Enjoy chatting with PDFs! 
