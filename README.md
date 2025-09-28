# LangChain Person Summary Generator

This project uses LangChain to generate concise summaries and interesting facts about individuals from freeform biographical input. It supports both OpenAI models (like GPT-5) and local LLMs via Ollama.

# Prerequisites

* Python **3.12+**
* uv
* OpenAI API Key (if using OpenAI)
* [Ollama](https://ollama.com/download) installed and configured (if using local LLMs)

## Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/langchain-summary-generator.git
cd langchain-summary-generator
```

### 2. Create a `.env` File

```bash
touch .env
```

Paste your environment variables:

```env
# OpenAI
OPENAI_API_KEY=<your-openai-api-key>

# LangSmith (optional)
LANGSMITH_TRACING=true
LANGSMITH_ENDPOINT=https://api.smith.langchain.com
LANGSMITH_API_KEY=<your-langsmith-api-key>
LANGSMITH_PROJECT=<your-langsmith-project>
```

### 3. Install Dependencies Using `uv`

```bash
uv venv        
source .venv/bin/activate
uv sync
```

## Usage

### Default: Using OpenAI (e.g., GPT-5)

```bash
python main.py
```

Paste the biographical input when prompted.

### Alternative: Use Local Model via Ollama
1. Download and install ollama
```bash
https://ollama.com/download
```  

2. Start your Ollama model:

```bash
ollama run gemma3:270m
```

3. In `main.py`, comment out the OpenAI model and uncomment the Ollama model:

```python
# llm = ChatOpenAI(model="gpt-5", temperature=0)
llm = ChatOllama(model="gemma3:270m", temperature=0)
```

4. Run the script again:

```bash
python main.py
```

## License

This project is licensed under the **MIT License**.
