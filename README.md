🚀 Gemini Colab Agent

A powerful AI agent setup connecting Gemini CLI with Google Colab through the Model Context Protocol (MCP).

This project enables Gemini to interact with a Colab notebook as an automated workspace, allowing the agent to:

create notebook cells

run Python code

install dependencies

generate analysis

automate research workflows

🧠 Architecture
User (Terminal)
      │
      ▼
🤖 Gemini CLI (AI Agent)
      │
      ▼
🔗 Model Context Protocol (MCP)
      │
      ▼
⚙️ Colab MCP Server
      │
      ▼
☁️ Google Colab Runtime

The agent sends commands through MCP to execute code directly in Google Colab's cloud environment.

✨ Features

🔥 AI-powered notebook automation
⚡ Cloud code execution with Colab
🧠 Gemini CLI as intelligent agent
🔧 MCP tool integration
📦 Modular and extensible architecture
🚀 Easy setup and lightweight environment

📂 Project Structure
gemini-colab-agent
│
├── .gemini/
│   └── settings.json        # MCP configuration
│
├── colab-mcp/               # Colab MCP server
│
├── scripts/
│   └── start-agent.ps1      # optional helper script
│
├── README.md
└── .gitignore
🛠 Requirements

Before running the project install:

Python 3.10+

Node.js

npm

Git

uv (Python package manager)

⚙️ Installation
1️⃣ Clone the repository
git clone https://github.com/Atheek-Fareez/gemini-colab-agent.git
cd gemini-colab-agent
2️⃣ Install Gemini CLI
npm install -g @google/gemini-cli

Verify installation:

gemini --version
3️⃣ Install uv
pip install uv
4️⃣ Clone the Colab MCP server
git clone https://github.com/googlecolab/colab-mcp.git
5️⃣ Configure MCP for Gemini

Create:

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

This configuration allows Gemini to automatically start the Colab MCP server.

▶️ Running the Agent

Start the AI agent:

gemini

Gemini will automatically load the MCP server and connect to Colab.

💡 Example Prompt

Try asking Gemini:

Create a markdown cell that says "Colab MCP test".
Then create a Python cell that prints "Hello from Colab MCP".
Execute the cell.

Gemini will interact with the notebook through MCP.

🔥 Use Cases

This project can be used for:

📊 automated data analysis
🧪 machine learning experimentation
📚 research notebook generation
⚡ rapid prototyping
🤖 AI-powered development workflows

🧩 Extending the Agent

You can add additional MCP tools:

filesystem MCP

browser MCP

database MCP

API MCP

web automation tools

This allows Gemini to become a multi-tool AI agent system.

🤝 Contributing

Contributions are welcome.

Steps:

Fork the repository

Create a new branch

Submit a pull request

📜 License

MIT License

🙌 Acknowledgements

Google Gemini CLI

Google Colab

Model Context Protocol (MCP)

⭐ If you find this project useful, consider starring the repository.
