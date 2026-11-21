# LLM Monitoring System with MongoDB

## Project Description

This project is a Python-based LLM Monitoring System that integrates Ollama with MongoDB to monitor and record Large Language Model usage.

It generates responses using the Ollama `llama3.2` model, tracks token usage and request latency, and stores usage details in MongoDB.

## Features

- Generates AI responses using Ollama.
- Tracks input and output tokens.
- Calculates total token usage.
- Measures API response latency.
- Logs usage details into MongoDB.
- Implements automatic retry mechanisms for failed requests.
- Includes unit testing using Python unittest.

## Technologies Used

- Python
- Ollama
- Llama 3.2
- MongoDB Atlas
- PyMongo
- Requests
- Python-dotenv
- Unittest

## Project Structure

```text
LLM-Monitoring/
│
├── .env
├── .gitignore
├── main.py
├── llm_client.py
├── usage_logger.py
├── test_client.py
├── requirements.txt
└── README.md
```

## Installation and Setup

### Step 1: Create a Virtual Environment

```bash
python -m venv Lab
```

### Step 2: Activate Virtual Environment

Windows:

```bash
Lab\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Configure MongoDB

Create a `.env` file in the project directory.

Add your MongoDB connection string:

```env
MONGODB_URI=your_mongodb_connection_string
```

### Step 5: Install Ollama Model

Download the Llama 3.2 model:

```bash
ollama pull llama3.2
```

Ensure Ollama is running locally.

### Step 6: Execute the Project

```bash
python main.py
```

Enter your question when prompted.

The application generates an AI response and records usage information in MongoDB.

## Unit Testing

Run the following command:

```bash
python -m unittest test_client.py
```

The test verifies response generation and token usage logging using a fake provider and logger.

## MongoDB Database Details

**Database Name:** `llm_monitoring`

**Collection Name:** `api_usage`

The following details are stored:

- Provider Name
- Model Name
- Input Tokens
- Output Tokens
- Total Tokens
- Latency (milliseconds)
- Estimated Cost
- Request Status
- Number of Attempts
- Timestamp

## Working Process

1. The user enters a prompt.
2. The LLM Client sends the prompt to Ollama.
3. Ollama generates the response using Llama 3.2.
4. Token usage and response latency are calculated.
5. Usage details are sent to the Usage Logger.
6. MongoDB stores the usage information.
7. The generated response is displayed to the user.

## Expected Output

- Successful MongoDB connection.
- AI-generated response.
- Input token count.
- Output token count.
- Response latency.

