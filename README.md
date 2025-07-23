Patent Innovation Predictor

A powerful agentic AI system for patent trend analysis and future technology prediction using Ollama, OpenSearch, and CrewAI.

Overview

This system analyzes patent data to identify trends and predict future innovations in specific technology areas (with a focus on lithium battery technology). It uses a multi-agent approach with specialized roles for research direction, patent retrieval, data analysis, and innovation forecasting.

Prerequisites
Python 3.10+
Ollama for running local LLM models
OpenSearch instance running (default: localhost:9200)
Access to patent data (pre-loaded in OpenSearch)
Installation
Clone the repository:

Create a virtual environment:

python -m venv .venv
source .venv/bin/activate
Install dependencies:

pip install -r requirements.txt
Install and start Ollama as a Docker Container:

docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
Pull required models:

docker exec -it ollama ollama run deepseek-r1:1.5b          
docker exec -it ollama ollama run nomic-embed-text # For embeddings
Start OpenSearch:

docker compose -f docker-compose.yml
Make sure your OpenSearch instance is running on localhost:9200 (or update the connection settings in the code).

Configuration
Environment variables (optional):
Create a .env file for any API keys or configuration:

# Optional API keys
SERPAPI_API_KEY=your_key_here
OpenSearch setup:
The system will automatically create necessary indices if they don't exist.

Usage
Run the main application:

python agentic_rag.py
