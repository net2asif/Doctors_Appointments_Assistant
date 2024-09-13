---

# Doctors Appointments Assistant Chatbot

This repository contains the code for a highly specialized AI chatbot that assists users in finding and booking appointments with healthcare professionals, including but not limited to dermatologists, surgeons, dentists, and cardiologists. The chatbot uses LangChain, OpenAI, and Qdrant to provide relevant healthcare professional recommendations based on user queries.

## Features

- **Medical Expert Assistance**: Leverages GPT-based language models and retrieval-based query processing to provide expert-level assistance in finding healthcare professionals.
- **Contextual Search**: Uses a vector database (Qdrant) to retrieve and match the most relevant healthcare professional information based on the user's query.
- **Rich Details**: Provides detailed information about the healthcare professionals, including qualifications, years of experience, patient satisfaction rates, consultation fees, and clinic/hospital addresses.
- **Interactive UI**: Implemented with Gradio to offer a simple, user-friendly interface for users to interact with the chatbot.

## How It Works

1. **Data Loading and Processing**: The chatbot loads a CSV file containing healthcare professionals' details. The data is split into smaller chunks using LangChain's `RecursiveCharacterTextSplitter`.
  
2. **Embeddings**: The data is embedded using OpenAI's embedding model (`text-embedding-3-small`) to create vector representations of the documents.
  
3. **Vector Database (Qdrant)**: The vector embeddings are stored and queried using Qdrant, a high-performance vector search database with support for similarity searches.
  
4. **Prompt Engineering**: The chatbot uses a custom prompt template to carefully generate comprehensive answers to user queries based on retrieved information.
  
5. **LLM (GPT-4)**: The chatbot uses OpenAI's GPT-4 language model to generate accurate, context-aware responses.

## Installation

To set up the chatbot locally, follow these steps:

1. **Clone the Repository**:

    ```bash
    git clone https://github.com/yourusername/doctor-appointments-assistant.git
    cd doctor-appointments-assistant
    ```

2. **Install Required Dependencies**:

    Install the necessary Python packages by running the following command:

    ```bash
    pip install langchain openai qdrant-client gradio pandas tiktoken -U langchain-community
    ```

3. **Set up API Keys**:

    You'll need to set up your OpenAI API key and Qdrant API key for the chatbot to function correctly. Store these in environment variables or replace them in the script:
    
    - `openai_api_key`: Your OpenAI API Key
    - `qdrant_api_key`: Your Qdrant API Key
    - `qdrant_url`: Qdrant instance URL

4. **Prepare Your Data**:

    Add your healthcare professional dataset in CSV format (e.g., `data.csv`) to the project directory. The data should include details like the doctor's name, city, specialization, qualifications, etc.

## Usage

Run the chatbot locally by executing:

```bash
python app.py
```

Once the chatbot is running, you can access it at `http://localhost:7860/` in your browser. You’ll be greeted with an interface that allows you to enter your medical queries, such as:

- "Show me the best dermatologist in Peshawar."
- "Who is a top-rated surgeon in Karachi?"

The chatbot will retrieve the most relevant information and provide a comprehensive response.

## Gradio Interface

The chatbot uses **Gradio** for its interactive interface. You can interact with the chatbot through the Gradio interface, which makes the conversation user-friendly and straightforward.

## Technologies Used

- **LangChain**: For chain-based processing and document retrieval.
- **OpenAI**: GPT-based LLMs for generating responses.
- **Qdrant**: Vector search database to store and retrieve document embeddings.
- **Gradio**: Provides an interactive web interface for the chatbot.
- **Pandas**: Used to load and manage CSV data files.

## Project Structure

```bash
.
├── data.csv                # Dataset of healthcare professionals
├── app.py                  # Main Python script to run the chatbot
├── requirements.txt        # Required Python packages
└── README.md               # Project documentation
```

## Example Query

Here’s an example of a query and the chatbot's response:

**User**: "Show me the best dermatology doctor in Peshawar."

**Chatbot Response**:
```
Dr. Sarah Ahmed
City: Peshawar
Specialization: Dermatologist
Qualification: MBBS, FCPS Dermatology
Years of Experience: 10 years
Patient Satisfaction Rate: 95%
Consultation Fee: PKR 1,500
Clinic Address: XYZ Clinic, Main Road, Peshawar
Profile Link: www.example.com/sarah-ahmed
```

## Contributing

If you'd like to contribute to this project, feel free to open an issue or submit a pull request. Contributions are welcome, whether it's bug fixes, new features, or improving the documentation.
