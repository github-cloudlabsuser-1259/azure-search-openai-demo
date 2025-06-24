# Backend App Documentation

## Overview

This backend is a Python web application designed to run on Azure, providing APIs and services for the overall project. It uses the Quart framework (an async variant of Flask) and integrates with various Azure services for search, storage, authentication, and monitoring.

## Key Features

- **Async API**: Built with Quart for high concurrency.
- **Azure Integration**: Uses Azure Cognitive Services, Azure Search, Azure Storage, CosmosDB, and Azure Monitor.
- **OpenAI Integration**: Supports OpenAI and Azure OpenAI for LLM-based features.
- **Observability**: Integrated with OpenTelemetry for distributed tracing and monitoring.
- **Speech and Document Intelligence**: Supports Azure Speech and Document Intelligence APIs.
- **Container Ready**: Includes a Dockerfile for containerized deployment.

## Directory Structure

- `main.py`: Entry point, sets up the app and environment.
- `app.py`: Main application logic, API routes, and service integrations.
- `requirements.txt` / `requirements.in`: Python dependencies.
- `Dockerfile`: Container build instructions.
- `chat_history/`, `core/`, `prepdocslib/`, `approaches/`: Modularized code for chat, core utilities, document processing, and retrieval approaches.

## Setup & Installation

1. **Install dependencies**:
   ```sh
   pip install -r requirements.txt
   ```
2. **Run locally**:
   ```sh
   python main.py
   ```
   Or with Gunicorn (recommended for production):
   ```sh
   gunicorn -b 0.0.0.0:8000 main:app
   ```

3. **Docker**:
   ```sh
   docker build -t backend-app .
   docker run -p 8000:8000 backend-app
   ```

## Environment

- Loads environment variables from Azure or `.env` for local development.
- Designed to run both locally and in Azure App Service/Container Apps.

## Dependencies

See `requirements.txt` and `requirements.in` for a full list. Major packages include:
- `quart`, `openai`, `azure-identity`, `azure-search-documents`, `azure-cognitiveservices-speech`, `azure-cosmos`, `opentelemetry`, `gunicorn`, etc.

## Contributing

See the root `CONTRIBUTING.md` for guidelines.
