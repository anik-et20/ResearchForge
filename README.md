# 🔎 Multi-Agent Research Assistant

A multi-agent AI research assistant that automates web research by searching for relevant information, reading online sources, generating a structured report, and critically evaluating the result.

The system divides the research process among specialised agents instead of relying on a single AI response.

---

## 🚀 Features

* 🔍 **Search Agent** — Finds relevant and recent information using Tavily.
* 📖 **Reader Agent** — Extracts useful content from selected webpages.
* ✍️ **Writer Agent** — Generates a structured research report.
* 🧐 **Critic Agent** — Evaluates the generated report and identifies areas for improvement.
* 🌐 **Web-based Research** — Uses current online sources.
* 🔗 **Source Collection** — Includes URLs used during the research process.
* 🖥️ **Streamlit Interface** — Provides an interactive user interface.
* 🔐 **Secure Configuration** — API keys are managed through environment variables.

---

## 🏗️ Architecture & Workflow

```text
                         User Query
                             │
                             ▼
                    ┌─────────────────┐
                    │    Streamlit    │
                    │       UI        │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   Search Agent  │
                    │      Tavily     │
                    └────────┬────────┘
                             │
                       Search Results
                             │
                             ▼
                    ┌─────────────────┐
                    │   Reader Agent  │
                    │ BeautifulSoup   │
                    └────────┬────────┘
                             │
                       Source Content
                             │
                             ▼
                    ┌─────────────────┐
                    │   Writer Agent  │
                    │       LLM       │
                    └────────┬────────┘
                             │
                       Research Report
                             │
                             ▼
                    ┌─────────────────┐
                    │   Critic Agent  │
                    │       LLM       │
                    └────────┬────────┘
                             │
                             ▼
                       Final Report
```

The workflow follows:

**Search → Read → Write → Critique**

---

## 🛠️ Technology Stack

| Technology    | Purpose                         |
| ------------- | ------------------------------- |
| Python        | Core programming language       |
| LangChain     | LLM and agent framework         |
| LangGraph     | Agent workflow orchestration    |
| Groq          | LLM inference                   |
| Tavily        | Web search                      |
| BeautifulSoup | Webpage content extraction      |
| Requests      | HTTP requests                   |
| Streamlit     | Frontend and user interface     |
| Pydantic      | Data validation                 |
| python-dotenv | Environment variable management |

---

## 📂 Project Structure

```text
multi-agent-research/
│
├── agents.py
├── tools.py
├── main.py
├── app.py
│
├── requirements.txt
├── .env
├── .env.example
├── .gitignore
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

### 2. Create a virtual environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key
```

You can use `.env.example` as a template.

**Never commit your `.env` file to GitHub.**

---

## 🖥️ Running the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will open in your browser.

Enter a research topic, and the system will perform the research process and display the resulting report.

---

## 🧪 Example

### Input

```text
Research the impact of generative AI on software engineering jobs.
```

### Output

The system generates a structured report containing:

* Introduction
* Key Findings
* Conclusion
* Sources
* Critic evaluation

---

## 🔐 Security

Sensitive credentials are excluded from version control using `.gitignore`.

Files such as:

```text
.env
credentials.json
secrets.json
*.pem
*.key
```

should never be committed to the repository.

Use `.env.example` to show the required environment variables without exposing actual credentials.

---

## 🔮 Future Improvements

* [ ] Parallel source processing
* [ ] Source credibility scoring
* [ ] Automatic citation generation
* [ ] Source deduplication
* [ ] Hallucination detection
* [ ] Research history
* [ ] PDF and Markdown export
* [ ] Human-in-the-loop review
* [ ] Persistent research memory

---

## 🎯 Project Objective

The goal of this project is to demonstrate how multiple specialised AI agents can collaborate to perform an end-to-end research task.

Instead of assigning every responsibility to a single agent, the system separates the process into specialised roles:

```text
Search → Read → Write → Critique
```

This approach makes the research workflow more structured, modular, and easier to evaluate and extend.

---

AI/ML & Multi-Agent Systems Project
