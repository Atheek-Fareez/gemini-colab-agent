
# 🚀 Gemini Colab Agent

A powerful **AI agent setup** connecting **Gemini CLI** with **Google Colab** through the **Model Context Protocol (MCP)**.

This project enables Gemini to interact with a **Colab notebook as an automated workspace**, allowing the agent to:

- Create notebook cells
- Run Python code
- Install dependencies
- Generate analysis
- Automate research workflows

---

# 🧠 Architecture

```

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

```

The agent sends commands through MCP to execute code directly in **Google Colab's cloud environment**.

---

# ✨ Features

- 🔥 AI-powered notebook automation  
- ⚡ Cloud code execution with Colab  
- 🧠 Gemini CLI as intelligent agent  
- 🔧 MCP tool integration  
- 📦 Modular and extensible architecture  
- 🚀 Easy setup and lightweight environment  

---

# 📂 Project Structure

```

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

````

---

# 🛠 Requirements

Before running the project install:

- Python 3.10+
- Node.js
- npm
- Git
- uv (Python package manager)

---

# ⚙️ Installation

## 1️⃣ Clone the repository

```bash
git clone https://github.com/Atheek-Fareez/gemini-colab-agent.git
cd gemini-colab-agent
````

---

## 2️⃣ Install Gemini CLI

```bash
npm install -g @google/gemini-cli
```

Verify installation:

```bash
gemini --version
```

---

## 3️⃣ Install uv

```bash
pip install uv
```

---

## 4️⃣ Clone the Colab MCP server

```bash
git clone https://github.com/googlecolab/colab-mcp.git
```

---

## 5️⃣ Configure MCP for Gemini

Create:

```
.gemini/settings.json
```

Example configuration:

```json
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
```

This configuration allows Gemini to automatically start the **Colab MCP server**.

---

# ▶️ Running the Agent

Start the AI agent:

```bash
gemini
```

Gemini will automatically load the MCP server and connect to Colab.

---

# 💡 Example Prompt

Try asking Gemini:

```
Create a markdown cell that says "Colab MCP test".
Then create a Python cell that prints "Hello from Colab MCP".
Execute the cell.
```

Gemini will interact with the notebook through MCP.

---

# 🔥 Use Cases

This project can be used for:

* 📊 Automated data analysis
* 🧪 Machine learning experimentation
* 📚 Research notebook generation
* ⚡ Rapid prototyping
* 🤖 AI-powered development workflows

---

# 🧩 Extending the Agent

You can add additional MCP tools:

* Filesystem MCP
* Browser MCP
* Database MCP
* API MCP
* Web automation tools

This allows Gemini to become a **multi-tool AI agent system**.

---

# 🤝 Contributing

Contributions are welcome.

Steps:

1. Fork the repository
2. Create a new branch
3. Submit a pull request

---

# 📜 License

MIT License

---

# 🙌 Acknowledgements

* Google Gemini CLI
* Google Colab
* Model Context Protocol (MCP)

---

⭐ If you find this project useful, consider **starring the repository**.

```

If you want, I can also show you **how to add GitHub badges (build, stars, forks, license)** so your repo looks **like a professional open-source AI project**.
```
