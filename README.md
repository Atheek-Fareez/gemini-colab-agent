# gemini-colab-agent
AI agent system using Gemini CLI, MCP protocol, and Google Colab runtime.
Gemini Colab Agent

AI agent setup that connects Gemini CLI with Google Colab using the Model Context Protocol (MCP).

This project allows Gemini to interact with a Colab notebook as a programmable workspace, enabling the agent to create cells, run Python code, and automate notebook workflows directly from the terminal.

Architecture
User (Terminal)
      │
      ▼
Gemini CLI (AI Agent)
      │
      ▼
Model Context Protocol (MCP)
      │
      ▼
Colab MCP Server
      │
      ▼
Google Colab Runtime

The agent sends commands through MCP to the Colab runtime where Python code is executed in the cloud.

Features

Gemini CLI as the AI agent

MCP server integration

Google Colab runtime execution

Cloud-based code execution

No local environment pollution

Easy to extend with additional MCP tools

Project Structure
gemini-colab-agent/
│
├── .gemini/
│   └── settings.json        # MCP configuration for Gemini CLI
│
├── colab-mcp/               # Colab MCP server (cloned repo)
│
├── scripts/
│   └── start-agent.ps1      # optional helper script
│
├── README.md
└── .gitignore
Requirements

Install the following tools before running the agent.

Python 3.10+

Node.js

npm

Git

uv (Python package manager)

Installation
1. Clone the repository
git clone https://github.com/YOUR_USERNAME/gemini-colab-agent.git
cd gemini-colab-agent
2. Install Gemini CLI
npm install -g @google/gemini-cli

Verify installation:

gemini --version
3. Install uv
pip install uv
4. Clone the Colab MCP server

Inside the project directory:

git clone https://github.com/googlecolab/colab-mcp.git
5. Configure MCP for Gemini

Create the file:

.gemini/settings.json

Example configuration:

{
  "mcpServers": {
    "colab-mcp": {
      "command": "uv",
      "args": ["run", "colab-mcp"],
      "cwd": "./colab-mcp",
      "timeout": 30000
    }
  }
}

This tells Gemini CLI to launch the Colab MCP server automatically.

Running the Agent

Start Gemini CLI from the project root:

gemini

Gemini will load the MCP configuration and connect to the Colab MCP server.

Example Prompt

Once Gemini starts, try a simple command:

Create a markdown cell that says "Colab MCP test".
Then create a Python cell that prints "Hello from Colab MCP".
Execute the cell.

The agent will control the notebook through MCP.

Use Cases

Possible applications include:

automated data analysis

notebook generation

machine learning experimentation

rapid prototyping

AI-driven research workflows

Extending the Agent

You can extend the system by adding additional MCP tools such as:

filesystem MCP

browser MCP

database MCP

API integrations

This turns Gemini CLI into a multi-tool AI agent environment.
