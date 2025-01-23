# How to Locally run LLMs using Docker and Ollama

In this tutorial, we'll guide you through setting up a Large Language Model (LLM) locally using Docker and Ollama, and accessing it via Open WebUI. This setup allows you to run powerful language models on your machine with a user-friendly interface.

## Required Links

1. [Download Docker Desktop](https://www.docker.com/)
2. [Quick start on Ollama](https://ollama.com/blog/ollama-is-now-available-as-an-official-docker-image)
3. [Quick start on Open WebUI](https://docs.openwebui.com/getting-started/quick-start)

## Required commands

1. `ipconfig` - to get the WSL IP address (Windows only).
2. `docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama` - to install Ollama CPU version in Docker.
3. `docker exec -it ollama ollama pull llama3.2:1b` - to directly download the llama3.2:1b model.
4. `docker exec -it ollama ollama run llama3.2:1b` - to directly run the llama3.2:1b model.
5. `docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main` - to startup the Open WebUI instance. makesure to find the ollama base url and add it to the command.
