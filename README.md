# Agentic AI Inbox

A powerful email assistant built with LangGraph that can autonomously manage your email inbox with human-in-the-loop capabilities and memory.

## 🚀 Features

- **Autonomous Email Processing**: AI-powered email triage and response generation
- **Human-in-the-Loop**: Review and approve AI decisions before execution
- **Memory System**: Learn from user feedback and adapt to preferences over time
- **Gmail Integration**: Full Gmail API integration for real email management
- **LangGraph Workflows**: Built on LangGraph for robust, scalable email processing
- **Evaluation Framework**: Comprehensive testing and evaluation using LangSmith

## 🏗️ Architecture

This project is based on the [LangChain Agents from Scratch](https://github.com/langchain-ai/agents-from-scratch) repository and extends it with:

- **Email Triage Agent**: Classifies and prioritizes incoming emails
- **Response Generation**: Creates contextually appropriate email responses
- **Tool Integration**: Calendar scheduling, email composition, and more
- **Memory Persistence**: Long-term learning and preference storage
- **Human Oversight**: Approval workflows for critical actions

## 📋 Prerequisites

- Python 3.11 or later
- OpenAI API key
- LangSmith API key (for monitoring and evaluation)
- Gmail API credentials (for production use)

## 🛠️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/git-bonda108/agentic-ai-inbox.git
cd agentic-ai-inbox
```

### 2. Set Up Virtual Environment

This project uses `uv` for fast dependency management:

```bash
# Install uv if you haven't already
pip install uv

# Install the package with development dependencies
uv sync --extra dev

# Activate the virtual environment
source .venv/bin/activate
```

### 3. Environment Configuration

Create a `.env` file in the root directory:

```bash
cp .env.example .env
```

Edit the `.env` file with your API keys:

```env
LANGSMITH_API_KEY=your_langsmith_api_key
LANGSMITH_TRACING=true
LANGSMITH_PROJECT="agentic-ai-inbox"
OPENAI_API_KEY=your_openai_api_key
```

## 🚀 Quick Start

### Basic Email Assistant

```python
from email_assistant.email_assistant import EmailAssistant

# Initialize the assistant
assistant = EmailAssistant()

# Process an email
result = assistant.process_email(email_content)
```

### Human-in-the-Loop Version

```python
from email_assistant.email_assistant_hitl import EmailAssistantHITL

# Initialize with human oversight
assistant = EmailAssistantHITL()

# Process with human approval workflow
result = assistant.process_email_with_approval(email_content)
```

### Memory-Enabled Version

```python
from email_assistant.email_assistant_hitl_memory import EmailAssistantHITLMemory

# Initialize with memory and human oversight
assistant = EmailAssistantHITLMemory()

# Process with memory and learning
result = assistant.process_email_with_memory(email_content)
```

## 📚 Notebooks

The project includes comprehensive Jupyter notebooks:

- **`notebooks/agent.ipynb`**: Building the basic email assistant
- **`notebooks/evaluation.ipynb`**: Testing and evaluation framework
- **`notebooks/hitl.ipynb`**: Human-in-the-loop implementation
- **`notebooks/memory.ipynb`**: Memory and learning capabilities

## 🧪 Testing

Run the comprehensive test suite:

```bash
# Run all tests
python tests/run_all_tests.py

# Run specific test categories
pytest tests/ -v

# Test notebook execution
python tests/test_notebooks.py
```

## 🔧 Configuration

### Email Rules

Configure email processing rules in `src/email_assistant/config/email_rules.py`:

```python
EMAIL_RULES = {
    "urgent_keywords": ["urgent", "asap", "emergency"],
    "priority_patterns": [...],
    "auto_response_templates": {...}
}
```

### LangSmith Monitoring

Enable detailed monitoring and tracing:

```python
from langsmith import Client

client = Client()
# All operations are automatically traced
```

## 🚀 Deployment

### LangGraph Platform

Deploy to LangGraph Platform for production use:

```bash
# Deploy the graph
langgraph deploy --config langgraph.json
```

### Local Development

Run locally for development and testing:

```bash
# Start the development server
uv run python -m email_assistant.server
```

## 📁 Project Structure

```
agentic-ai-inbox/
├── src/email_assistant/
│   ├── agents/           # Agent implementations
│   ├── config/           # Configuration files
│   ├── gmail/            # Gmail API integration
│   ├── monitoring/       # Observability and monitoring
│   ├── workflows/        # LangGraph workflow definitions
│   └── tools/            # Email and calendar tools
├── notebooks/            # Jupyter notebooks
├── tests/                # Test suite
├── .venv/                # Virtual environment
└── pyproject.toml        # Project configuration
```

## 🔐 Security

- API keys are stored in environment variables
- Gmail OAuth2 authentication
- Secure credential management
- No hardcoded secrets in the codebase

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## 📄 License

This project is based on the LangChain Agents from Scratch repository and follows the same licensing terms.

## 🆘 Support

For issues and questions:
- Check the [LangChain documentation](https://python.langchain.com/)
- Review the [LangGraph documentation](https://langchain-ai.github.io/langgraph/)
- Open an issue in this repository

## 🔮 Roadmap

- [ ] Enhanced memory management with LangMem
- [ ] Multi-language support
- [ ] Advanced email analytics
- [ ] Integration with other email providers
- [ ] Mobile app interface
- [ ] Team collaboration features

---

**Built with ❤️ using LangChain, LangGraph, and OpenAI**
