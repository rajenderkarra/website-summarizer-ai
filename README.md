# Website Summarizer AI 🌐

An intelligent web scraper and summarizer that extracts website content and generates concise summaries using AI. This project demonstrates a practical data pipeline with web scraping, text processing, and LLM integration.

## 🎯 Features

- **Web Scraping**: Fetch and clean website content automatically
- **AI-Powered Summarization**: Generate intelligent summaries using Groq LLMs
- **Gradio Web UI**: Beautiful, shareable web interface
- **Error Handling**: Robust error management for network and parsing issues
- **Fast Processing**: Leverages Groq's ultra-fast inference

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup4-Parser-green)
![Requests](https://img.shields.io/badge/Requests-HTTP-lightblue)
![Gradio](https://img.shields.io/badge/Gradio-WebUI-orange)
![Groq](https://img.shields.io/badge/Groq-API-orange)

## 📋 Prerequisites

- Python 3.8 or higher
- Groq API Key (get it from [console.groq.com](https://console.groq.com/keys))
- Internet connection for web scraping
- pip package manager

## 🚀 Quick Start

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/website-summarizer-ai.git
cd website-summarizer-ai
```

### 2. Create virtual environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Setup environment variables
```bash
cp .env.example .env
# Edit .env and add your Groq API Key
```

### 5. Run the application
```bash
python src/app.py
```

The app will launch with a web interface (with `share=True`, you get a public link!)

## 📁 Project Structure

```
website-summarizer-ai/
├── README.md                # Project documentation
├── requirements.txt         # Python dependencies
├── .env.example             # Environment variables template
├── .gitignore               # Git ignore rules
└── src/
    ├── __init__.py
    ├── app.py               # Gradio web interface
    ├── scraper.py           # Web content extraction
    └── summarizer.py        # AI summarization logic
```

## 🔄 How It Works

### 1. Web Scraping (`scraper.py`)
- Accepts website URLs
- Handles missing URL schemes (http/https)
- Extracts main content using BeautifulSoup
- Removes navigation, footers, scripts, styles
- Returns cleaned text and page title

### 2. Summarization (`summarizer.py`)
- Takes cleaned website content
- Sends to Groq LLM with a system prompt
- Generates friendly, markdown-formatted summary
- Returns structured summary

### 3. Web Interface (`app.py`)
- Built with Gradio for easy interaction
- Text input for website URLs
- Markdown output for formatted summaries
- Shareable public link for demos

## 📚 What This Teaches

- **Web Scraping**: Using BeautifulSoup for HTML parsing
- **HTTP Requests**: Handling web requests with proper headers
- **Data Pipeline**: Multi-stage data processing
- **API Integration**: LLM API integration
- **Web UI Development**: Building quick interfaces with Gradio
- **Error Handling**: Graceful error management
- **System Design**: Separation of concerns (scraper, summarizer, UI)

## 🧪 Example Usage

```python
from scraper import fetch_website_contents
from summarizer import summarize

# Summarize a website
url = "https://example.com"
summary = summarize(url)
print(summary)
```

### Using the Web UI
Simply open the Gradio interface and:
1. Enter a website URL
2. Click "Submit"
3. Get AI-powered summary instantly

## 🎓 Learning Outcomes

After working through this project, you'll understand:
- Web scraping techniques and best practices
- Multi-stage data processing pipelines
- Integration with LLM APIs
- Building and sharing web interfaces
- Error handling in production scenarios
- HTML parsing and text extraction

## 🚀 Future Enhancements

- [ ] Support for PDF summarization
- [ ] Multi-language support
- [ ] Caching for repeated URLs
- [ ] Summary length customization
- [ ] History tracking
- [ ] Export summaries (PDF, JSON)
- [ ] Batch processing
- [ ] Performance metrics

## 🛠️ Configuration

### Adjusting Summary Prompt

Edit `summarizer.py` to modify the system prompt:
```python
system_prompt = """You analyze the contents of a website and
give a short, friendly summary. Ignore navigation menus.
Respond in markdown."""
```

### Changing LLM Models

Modify the model selection in `summarizer.py`:
```python
response = client.chat.completions.create(
    model="openai/gpt-oss-20b",  # Change this to other Groq models
    ...
)
```

## 📝 License

This project is licensed under the MIT License - see LICENSE file for details.

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest improvements
- Submit pull requests
- Share use cases

## ⚠️ Important Notes

- Respect website robots.txt and terms of service
- Use appropriate User-Agent headers
- Don't spam requests to websites
- Some websites may block scraping - handle gracefully

## 📧 Contact

Have questions or feedback? Open an issue or reach out!

---

**Made with ❤️ for learning AI systems & data pipelines**
