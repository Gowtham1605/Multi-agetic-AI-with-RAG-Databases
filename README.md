This project integrates Phidata, GROQ, and Google Generative AI to build an intelligent PDF assistant capable of processing and querying content from a PDF file.

Project Overview:
The PDF Assistant is designed to:
Load and embed knowledge from a PDF file into a PostgreSQL database.
Use Google's Gemini API for embedding and processing natural language queries.
Interact with the database and respond based on the knowledge stored from the PDF document.
The assistant can answer questions about the content of the PDF using natural language processing, powered by GROQ and Phidata.

Requirements:

Dependencies

phidata: For building and managing the knowledge base.
python-dotenv: For managing environment variables (API keys).
yfinance: For financial data retrieval.
packaging: For packaging and versioning utilities.
duckduckgo-search: For web search functionality using DuckDuckGo.
fastapi: For building the web server.
uvicorn: For serving FastAPI applications.
groq: For leveraging Groq models.
openai: For integration with OpenAI's GPT models.
sqlalchemy: For interacting with the PostgreSQL database.
pgvector: For storing and querying vector embeddings in PostgreSQL.
psycopg[binary]: PostgreSQL database adapter for Python.
pypdf: For reading and processing PDF files.

🚀 Installation & Setup
Step 1: Clone the repository
Clone this repository to your local machine.
Step 2: Install dependencies
Install the required dependencies using pip.
Step 3: Set up environment variables
Create a .env file in the project directory and add your API keys for GROQ and Google Generative AI.
Step 4: Set up PostgreSQL
Ensure you have PostgreSQL running locally or on a server. Update the database connection URL in the project with your PostgreSQL connection details.
Step 5: Run the assistant
Once everything is set up, you can start the PDF assistant by running the main script.

🤖 How the Assistant Works?
PDF Knowledge Base
The PDFUrlKnowledgeBase class is used to load a PDF, process it, and store its contents in a vector database (PostgreSQL with pgvector). The PDF content is embedded using Google Gemini embeddings.

Generative AI Interaction
The assistant uses a GROQ model for natural language processing, making it capable of understanding and responding to queries. Google's Gemini Embedder helps convert the content of the PDF into embeddings for search and retrieval.

PostgreSQL Database Integration
The assistant interacts with the PostgreSQL database, which stores the knowledge and any relevant interactions. This enables persistent storage of the assistant’s knowledge and chat history.

CLI Interaction
The assistant provides a CLI for user interaction, where users can query the content of the PDF.

Project Structure:
main.py: The main script to run the PDF assistant.
requirements.txt: A list of dependencies required to run the project.
.env: The environment file for securely storing API keys.
pdf_assistant.py: Contains the logic for initializing and running the assistant.
knowledge_base.py: Contains logic for creating the knowledge base using the PDF and embeddings.
db.py: Handles database connections and queries to PostgreSQL.
