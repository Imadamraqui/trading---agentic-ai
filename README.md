# 📈 AI Stock Analysis Agent

A beginner-friendly stock analysis application built with **Streamlit**, **Ollama**, **LangChain**, and **LangGraph**. This app fetches real-time stock data and uses AI to provide financial analysis and investment recommendations. The entire app is under 300 lines of clean, well-commented code perfect for learning!


## ✨ Features

- 📊 **Real-time Stock Data**: Current prices, market cap, volume, and daily changes
- 💰 **Financial Statements**: Balance sheets, income statements, and cash flow (yearly/quarterly)
- 🤖 **AI-Powered Analysis**: Uses local LLM (Ollama) for intelligent financial analysis
- 💡 **Investment Recommendations**: Get AI-generated buy/hold/sell recommendations
- 🔄 **LangGraph Workflow**: Orchestrated agent workflow with clear data processing pipeline
- 🎨 **Beautiful UI**: Clean Streamlit interface with tabs and metrics
- 🎯 **Beginner-Friendly**: Under 300 lines of clean, well-commented code

## 🛠️ Tech Stack

- **Frontend**: Streamlit
- **LLM**: Ollama (llama3.2)
- **Agent Framework**: LangChain + LangGraph
- **Data Source**: Yahoo Finance (yfinance)
- **Language**: Python 3.10+
- **Total Lines**: 276 lines

## 📋 Prerequisites

Before you begin, ensure you have:

1. **Python 3.10+** installed
2. **Ollama** installed and running locally
   - Download from: https://ollama.ai
   - Install llama3.2 model: `ollama pull llama3.2`

## 🚀 Installation

### Step 1: Clone the Repository

```bash
cd 01-LangGraph_Stock_Agent
```

### Step 2: Create Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Verify Ollama Installation

```bash
# Check if Ollama is running
ollama list

# Pull llama3.2 model if not already installed
ollama pull llama3.2
```

## 🎯 Usage

### Run the Application

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`

### Using the App

1. **Enter Stock Ticker**: Type any valid stock symbol (e.g., AAPL, MSFT, GOOGL, TSLA)
2. **Select Period**: Choose between yearly or quarterly financial data
3. **Click Analyze**: The AI agent will:
   - Fetch real-time stock prices
   - Retrieve financial statements
   - Analyze financial health
   - Generate investment recommendations

### Example Tickers to Try

- **AAPL** - Apple Inc.
- **MSFT** - Microsoft Corporation
- **GOOGL** - Alphabet Inc.
- **TSLA** - Tesla Inc.
- **NVDA** - NVIDIA Corporation
- **AMZN** - Amazon.com Inc.

## 🔧 Code Structure (Tutorial Sections)

The code is organized into 5 clear sections for easy learning:

### Section 1: Imports and Configuration
- All necessary imports
- Basic setup

### Section 2: Data Fetching Functions
- `fetch_stock_price()`: Gets current price and basic info
- `fetch_financial_statements()`: Retrieves balance sheet, income statement, cash flow

### Section 3: LangGraph State and Nodes
- `AgentState`: Defines the state structure
- `fetch_data_node()`: Node for fetching stock data
- `analyze_financials_node()`: Node for AI analysis
- `generate_recommendation_node()`: Node for generating recommendations

### Section 4: LangGraph Workflow
- `create_stock_analysis_graph()`: Builds and compiles the agent workflow

### Section 5: Streamlit UI
- `main()`: Complete Streamlit interface with tabs and visualizations

## 🎓 Learning Path

## ⚙️ Configuration

### Change LLM Model

To use a different Ollama model, modify the `llm` initialization in `app.py`:

```python
llm = Ollama(model="mistral", temperature=0.3)  # Use mistral instead of llama3.2
```

Available models:
- `llama3.2` (default)
- `llama3.1`
- `mistral`
- `phi`

### Adjust Analysis Temperature

Higher temperature = more creative, Lower = more focused:

```python
llm = Ollama(model="llama3.2", temperature=0.7)  # More creative
```

## 🐛 Troubleshooting

### "Connection Error" when running app

**Solution**: Make sure Ollama is running:
```bash
ollama serve
```

### "Model not found" error

**Solution**: Pull the required model:
```bash
ollama pull llama3.2
```


## 📊 Sample Output

The app provides:

1. **Price Data Tab**
   - Current price, change %, day high/low, market cap

2. **Financials Tab**
   - Balance sheet: Assets, liabilities, equity
   - Income statement: Revenue, net income, EBITDA
   - Cash flow: Operating, investing, financing cash flows

3. **Analysis Tab**
   - AI-generated financial health assessment
   - Key trends and observations
   - Strengths and weaknesses

4. **Recommendation Tab**
   - Overall sentiment (Bullish/Bearish/Neutral)
   - Risk level
   - Buy/Hold/Sell recommendation


