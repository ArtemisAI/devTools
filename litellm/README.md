# LiteLLM

LiteLLM is a lightweight Python-based HTTP proxy that provides an OpenAI-compatible API for local or remote large language models (LLMs). It enables you to use tools and services designed for the OpenAI API without modification.

## Supported Services

Any service or application that integrates with the OpenAI API can use LiteLLM as a drop-in replacement. Examples include:

- **Codex CLI**: Interact with code generation models from the command line.
- **OpenwebUI**: Web-based interface for interacting with local LLMs.
- **n8n**: Workflow automation platform using OpenAI nodes.
- **Node-RED**: Flow-based programming for APIs and IoT.
- **LangChain**: Framework for building LLM-enabled applications.
- **Jupyter Notebooks**: Run prompts and experiments directly in notebooks.
- **Custom integrations**: Any HTTP client configured for the OpenAI API.

## How It Works

1. Configure your environment:
   - Copy `.env.example` to `.env` and set your `MASTER_KEY` and other variables.
   - Update `config.yaml` with your model backend settings.
2. Start the proxy:
   ```bash
   docker-compose up
   ```
   or
   ```bash
   python -m litellm
   ```
3. Point your OpenAI client to the endpoint:
   ```bash
   export OPENAI_API_BASE_URL="http://localhost:8000/v1"
   export OPENAI_API_KEY=<your_master_key>
   ```
4. Use your service as usual; LiteLLM will handle request forwarding and response formatting.

## Configuration Files

- `.env`: Environment variables (ignored by git).
- `config.yaml`: Proxy configuration (ignored by git).
- `docker-compose.yml`: Service definitions.
- `prometheus.yml`: Monitoring configuration (optional).