# Any-Document RAG with GROQ & ChromaDB

A Retrieval-Augmented Generation (RAG) application that allows users to upload various document types and ask questions about their content. The system processes documents, stores their content in a vector database, and uses a hybrid retrieval mechanism to find relevant information for answering user queries.

![RAG Architecture](https://raw.githubusercontent.com/SakibAhmedShuva/Any-Document-RAG-with-GROQ-Chroma-DB/main/templates/static/images/rag-architecture.png)

## Features

- **Multi-format Document Support**: Process PDF, DOCX, TXT, XLSX, XLS, and CSV files
- **Hybrid Retrieval System**: Combines TF-IDF and embedding-based similarity for better results
- **Web Interface**: User-friendly interface for document upload and querying
- **Document Statistics**: Visualize document distribution by source and file type
- **Conversation History**: Maintains conversation context for more coherent responses
- **User Feedback Collection**: Collect and store user ratings and comments on responses

## Technologies Used

- **Backend**: Flask (Python)
- **Vector Database**: ChromaDB
- **Embeddings**: Sentence Transformers (all-MiniLM-L6-v2)
- **LLM Integration**: GROQ API with various models support (Gemma 2, Mixtral, Llama 3)
- **Document Processing**: PyPDF, python-docx, openpyxl, csv
- **Visualization**: Matplotlib
- **Frontend**: HTML, CSS, JavaScript

## Project Structure

```
.
├── app.py                  # Main Flask application
├── app.log                 # Application logs
├── requirements.txt        # Python dependencies
├── feedback.json           # Stored user feedback
├── templates/              # HTML templates and static assets
├── uploads/                # Directory for temporary file uploads
└── chroma_db/              # Vector database storage
```

## Setup Instructions

1. **Clone the repository**:
   ```
   git clone https://github.com/SakibAhmedShuva/Any-Document-RAG-with-GROQ-Chroma-DB.git
   cd Any-Document-RAG-with-GROQ-Chroma-DB
   ```

2. **Create and activate a virtual environment** (optional but recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install the dependencies**:
   ```
   pip install -r requirements.txt
   ```

4. **Create a `.env` file** with your GROQ API key:
   ```
   GROQ_API_KEY=your_groq_api_key_here
   ```

5. **Run the application**:
   ```
   python app.py
   ```

6. **Access the application** at http://localhost:5000

## Usage

### Document Upload

1. Navigate to the upload page at `/admin/upload`
2. Click "Choose File" and select a document (PDF, DOCX, TXT, XLSX, XLS, CSV)
3. Click "Upload" to process and store the document
4. View document statistics on the upload page

### Asking Questions

1. Go to the main page at `/`
2. Type your question in the input field
3. Press "Send" or hit Enter
4. View the response and source documents
5. Provide feedback on the response quality (optional)

## Configuration Options

The application can be configured by modifying the following variables in `app.py`:

- `app.config['UPLOAD_FOLDER']`: Location for uploaded files
- `app.config['MAX_CONTENT_LENGTH']`: Maximum file size (default: 512MB)
- LLM model selection: Change the model parameter in the `generate_response()` function

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- [GROQ](https://groq.com/) for providing the LLM API
- [ChromaDB](https://www.trychroma.com/) for the vector database
- [Sentence Transformers](https://www.sbert.net/) for the embedding model
