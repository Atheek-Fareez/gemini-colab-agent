# GEMINI.md - Colab MCP Server

This project is an **MCP (Model Context Protocol) server** that enables AI agents to interact with **Google Colab**. It allows for code execution, session management, and direct interaction with Colab runtimes.

## 🏗️ Architecture Overview

The project is built using Python 3.13+ and the `FastMCP` framework.

### Core Components (`src/colab_mcp/`)

- **`__init__.py`**: The entry point. It sets up the CLI, configures logging, and mounts the different MCP tools (Runtime and Proxy).
- **`auth.py`**: Handles OAuth2 authentication for Google services. It expects a client configuration JSON (default: `colab-mcp-oauth-config.json`).
- **`runtime.py`**: Provides tools for direct interaction with a Colab Jupyter runtime. This is disabled by default and can be enabled via `--enable-runtime`.
- **`session.py` & `websocket_server.py`**: Implements a `ColabSessionProxy`. This sets up a local WebSocket server that proxies requests to the Colab backend, allowing the agent to manage and interact with notebooks.
- **`client.py`**: Handles the underlying communication with Colab's internal APIs.

## 🛠️ Development & Tooling

- **Package Manager**: `uv` is used for dependency management and running the project.
- **Linting & Formatting**: `ruff` is used for both linting and formatting.
- **Testing**: `pytest` with `pytest-asyncio` for asynchronous tests. Coverage is tracked via `pytest-cov`.
- **Git Hooks**: Pre-commit hooks are configured in `.githooks/pre-commit`. Ensure you run `git config core.hooksPath .githooks` to enable them.

## 🚀 Key Commands

- **Run Server**: `uv run colab-mcp`
- **Run Tests**: `uv run pytest`
- **Lint/Format**: `uv run ruff check .` and `uv run ruff format .`
- **Build**: Uses `hatchling` via `uv build`.

## 🤖 Guidance for AI Agents

### When modifying tools:
1.  **Check `FastMCP` usage**: The server uses `FastMCP` decorators and classes. Refer to `src/colab_mcp/__init__.py` to see how tools are mounted and how middleware is used.
2.  **Authentication**: If adding features that require Google API access, ensure you utilize the helper methods in `auth.py`.
3.  **Async First**: Most operations (especially proxy and runtime interactions) are asynchronous. Use `async/await` and ensure tests are marked with `@pytest.mark.asyncio`.
4.  **Logging**: Use the project's logging setup. Logs are stored in a temporary directory by default (e.g., `%TEMP%/colab-mcp-logs-*`).

### Testing Strategy:
- Always check `tests/` for existing patterns.
- Mocking is heavily used for OAuth and WebSocket interactions.
- If you add a new tool, add a corresponding test file in `tests/`.

## ⚠️ Important Notes
- **Issues**: Do NOT open issues directly on GitHub. Use the "Discussions" tab as per `README.md`.
- **Runtime Proxy**: The proxy server is a critical part of the session management. Be careful when modifying `websocket_server.py` as it handles the bridge between the agent and Colab.
