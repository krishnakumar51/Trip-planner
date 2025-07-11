# 🌍 Agentic Travel Planner Application

An AI-powered Travel Planning Assistant using **LangGraph**, **Groq LLMs**, **FastAPI**, and **Streamlit**. This app provides personalized trip itineraries, cost breakdowns, weather info, hotel and restaurant recommendations, and more — powered by agentic workflows and real-time tool integrations.

---

## 🧠 Features

- ✅ Agentic multi-step reasoning with [LangGraph](https://docs.langchain.com/langgraph/)
- 📦 Integrated tools:
  - Real-time **Weather Info**
  - Smart **Place Search**
  - Travel **Expense Calculator**
  - Live **Currency Conversion**
- 📜 Detailed travel itinerary & cost breakdown
- 🌍 Tourist + Offbeat suggestions
- 🧾 Markdown-formatted responses
- 🖼️ Mermaid-based graph visualization of agent flows
- 🔥 Powered by **Groq LLMs** via API
- ⚡ Built with FastAPI & Streamlit frontend

---

## 🚀 Quickstart

### 1. Clone the Repository

```bash
git clone https://github.com/krishnakumar51/Trip-planner.git
cd Trip-planner
````

### 2. Setup Virtual Environment

Make sure you have **Python 3.10** installed.

```bash
uv venv --python=python3.10
source .venv/bin/activate  # or .venv\Scripts\activate on Windows
```

### 3. Install Dependencies

```bash
uv pip install -r requirements.txt
```

### 4. Set Environment Variables

Create a `.env` file:

```env
GROQ_API_KEY=your_groq_api_key
```

### 5. Run Backend (FastAPI)

```bash
uvicorn main:app --reload
```

It will be available at: `http://localhost:8000`

### 6. Run Frontend (Streamlit)

```bash
streamlit run app.py
```

Streamlit will open a browser window for interaction.

---

## 📦 Project Structure

```
Trip-planner/
├── agent/
│   └── agentic_workflow.py         # LangGraph builder with agent + tools
├── tools/
│   ├── weather_info_tool.py
│   ├── place_search_tool.py
│   ├── expense_calculator_tool.py
│   └── currency_conversion_tool.py
├── prompt_library/
│   └── prompt.py                   # System prompt template
├── utils/
│   └── model_loader.py
│   └── save_to_document.py
├── app.py                          # Streamlit frontend
├── main.py                         # FastAPI backend
├── requirements.txt
└── .env                            # Environment variables (not committed)
```

---

## 📷 Graph Visualization

Agent flow is saved as `my_graph.png` after each query using **Mermaid** graph generated from LangGraph's compiled state machine.

---

## 🧠 How It Works

1. User inputs a query (e.g., *"Plan a 5-day trip to Goa"*).
2. The system prompt sets the assistant as a **travel expert**.
3. LangGraph orchestrates agent and tool nodes.
4. Tools are invoked conditionally:

   * Weather → WeatherInfoTool
   * Currency → CurrencyConverterTool
   * Cost → CalculatorTool
   * Places → PlaceSearchTool
5. Final result is returned in detailed Markdown format.

---

## 🔐 Secret Management

This project uses `.env` to store secrets like API keys.
To avoid pushing secrets:

```bash
echo ".env*" >> .gitignore
```

To clean Git history after accidental secret commit:

```bash
git filter-repo --path .env --invert-paths
```

---

## 🛠️ Todo

* Add voice-based interaction
* Export trip plans to PDF
* User session management
* Add more travel APIs (flights, buses, etc.)

---

## 🙏 Acknowledgements

* [LangGraph](https://github.com/langchain-ai/langgraph)
* [Groq](https://groq.com/)
* [LangChain](https://www.langchain.com/)
* [Streamlit](https://streamlit.io/)
* [FastAPI](https://fastapi.tiangolo.com/)

---

## 📄 License

This project is licensed under the MIT License.

```

---

Let me know if you want the `README.md` saved to a file or want badges (e.g., for license, Python version, or deployment).
```
