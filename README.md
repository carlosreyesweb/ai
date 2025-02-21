# AI Chatbot Environment

This project sets up an AI chatbot environment using Docker Compose, integrating various services like Open WebUI, Ollama, and LiteLLM.

## Services

- **frontend**: Web interface using Open WebUI.
- **ollama**: GPU-based computations.
- **backend**: LiteLLM service.
- **db**: PostgreSQL database.

## Setup

1. Ensure Docker and Docker Compose are installed.
2. Copy `.env.example` to `.env` and fill in the required values:

```bash
cp .env.example .env
```

3. Build and run the services:

```bash
docker compose up -d
```

4. Access the frontend at `http://localhost:7000`.

## Files

- `docker-compose.yaml`: Service definitions.
- `litellm_config.yaml`: LiteLLM configuration.
- `.env`: Environment variables.
- `.env.example`: Example environment variables.

## Notes

- It requires a Gemini API key to setup the config model, which is `gemini-2.0-flash`. It is currently free and can be obtained from the Google AI Studio website.
- `backend` depends on `db` being healthy. `frontend` depends on `ollama` being healthy.
- GPU support is configured for `ollama` and requires NVIDIA cards. Ensure you have the latest drivers, CUDA, and Docker configured for GPU support.
- `ollama` local models can be downloaded from the frontend via the Admin Settings.
- Models from external providers can be added by logging in as an admin to `http://localhost:7001/ui` and clicking on the `Models` tab, given you have the correct API key for each provider.
