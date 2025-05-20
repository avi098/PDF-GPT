# PDF GPT

## About the Project
PDF GPT is a web application built with Flask that allows users to upload PDF documents and ask questions about their content. The application processes the PDF, extracts text, and uses OpenAI's embeddings and language models to provide answers based on the document's content. It leverages FAISS for efficient similarity search and LangChain for question-answering capabilities.

The project consists of:
- A front-end interface (`index.html`) for uploading PDFs and submitting questions.
- A back-end Flask application (`app.py`) that handles PDF processing, text extraction, and question answering using AI models.

## Prerequisites
To set up and run the project, ensure you have the following installed:
- Python 3.8 or higher
- pip (Python package manager)
- A valid OpenAI API key
- A web browser (e.g., Chrome, Firefox)

## Setup Instructions
1. **Clone or Download the Project**
   - Download the project files (`index.html` and `app.py`) to a local directory.
   - Alternatively, clone the repository if hosted on a version control platform.

2. **Set Up a Virtual Environment (Optional but Recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Required Python Packages**
   Install the necessary dependencies by running:
   ```bash
   pip install flask PyPDF2 langchain openai faiss-cpu
   ```

4. **Configure the OpenAI API Key**
   - Obtain an API key from OpenAI (https://platform.openai.com/account/api-keys).
   - Replace the placeholder API key in `app.py` with your actual OpenAI API key:
     ```python
     os.environ["OPENAI_API_KEY"] = "your-actual-api-key-here"
     ```

5. **Directory Structure**
   Ensure the following structure in your project directory:
   ```
   project_directory/
   ├── templates/
   │   └── index.html
   ├── uploads/
   └── app.py
   ```
   - The `templates/` folder should contain `index.html`.
   - The `uploads/` folder will be automatically created when a PDF is uploaded.

## Running the Project
1. **Start the Flask Application**
   Navigate to the project directory and run:
   ```bash
   python app.py
   ```
   This starts the Flask development server in debug mode. You should see output indicating the server is running, typically at `http://127.0.0.1:5000`.

2. **Access the Application**
   Open a web browser and go to `http://127.0.0.1:5000`. You should see the PDF GPT interface.

3. **Using the Application**
   - Upload a PDF file using the file input field.
   - Enter a question related to the PDF content in the text area.
   - Click the "Get Answer" button to receive an AI-generated response based on the PDF's content.

## Notes
- The application requires an active internet connection to communicate with the OpenAI API.
- Ensure the `uploads` directory has write permissions, as uploaded PDFs are saved there temporarily.
- The application uses FAISS for vector storage and similarity search, which is CPU-based (`faiss-cpu`). For large PDFs, ensure sufficient system resources.
- The OpenAI API key in `app.py` is hardcoded for simplicity. In a production environment, consider using environment variables or a configuration file for security.

## Troubleshooting
- **Module Not Found Error**: Ensure all dependencies are installed using `pip install`.
- **API Key Issues**: Verify that your OpenAI API key is valid and has sufficient quota.
- **File Upload Errors**: Check that the `uploads` directory is writable and that the PDF file is not corrupted.
- **Server Not Starting**: Ensure port 5000 is not in use by another application.

## License
This project is for educational purposes and does not include a specific license. Modify and use it as needed for personal or academic projects.
