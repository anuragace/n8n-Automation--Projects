# n8n-Automation--Projects
# n8n Local AI Chatbot Workflow

## Overview

This n8n workflow provides a simple yet powerful chatbot interface that connects to a locally hosted Large Language Model (LLM) through Ollama. It's designed to be a starting point for creating more complex AI-driven automations without relying on external cloud APIs.

This project demonstrates the ability to integrate modern, self-hosted AI tools into a practical automation pipeline.

---

## Key Features

* **Local LLM Integration:** Connects directly to an Ollama server running on the host machine.
* **Self-Hosted Focus:** Operates without external API keys or costs, ensuring data privacy.
* **Flexible Model Support:** Can be easily configured to use any model downloaded in Ollama (e.g., Gemma, Llama 3, Mistral).
* **Docker Networking Solution:** The setup is configured to work correctly even when n8n is running in a Docker container, using `host.docker.internal` to communicate with the host machine.

---

## Setup & Requirements

To run this workflow, you will need:

1.  **n8n (Self-Hosted):** An n8n instance, preferably running in Docker.
2.  **Ollama:** The Ollama server must be installed and running on the host machine.
3.  **A Downloaded Model:** At least one model must be pulled via Ollama (e.g., `ollama pull gemma:2b`).
4.  **Ollama Host Configuration:** To allow the n8n container to connect, Ollama must be started with the host variable set (e.g., `OLLAMA_HOST="0.0.0.0" ollama serve`).

---

## How to Use

1.  **Import Workflow:** Import the `workflow.json` file into your n8n canvas.
2.  **Verify Model Name:** Click on the **"Ollama Chat Model"** node. Ensure the **Model** field (in "Fixed" mode) matches the name of a model you have downloaded in Ollama (e.g., `gemma:2b`).
3.  **Activate Workflow:** Enable the workflow.
4.  **Run:** Manually run the "When chat message received" node and enter your message in the `chatInput` field to test it.
