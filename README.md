# Professional News Analytics Platform  
*A Universal Company & Market Intelligence Dashboard*

## Overview  
The Professional News Analytics Platform is a Streamlit-based dashboard that converts any text query—company name (with or without typos) or industry topic—into a structured intelligence report. It combines:

1. **Universal entity recognition** (public, private, fictional, or misspelled companies).  
2. **Topic detection** for sectors, technologies, and market themes.  
3. **Configurable analysis frameworks** (market intelligence, competitive analysis, trend assessment, corporate performance).  
4. **Real-time collection of news and data sources** (financial filings, market research, media articles, regulatory documents).  
5. **Natural-language summarisation** to produce executive-level insights in multiple report styles.  

All functionality is presented in a formal, minimalist UI with serif typography and a blue-gray colour palette.

## Key Features

| Category                    | Details                                                                                           |
|-----------------------------|----------------------------------------------------------------------------------------------------|
| Entity Handling             | Recognises any company name (typos included) via spaCy NER, rule-based patterns, and fuzzy logic. |
| Topic Recognition           | AI, EVs, fintech, renewable energy, and custom sector keywords.                                   |
| Analysis Frameworks         | Comprehensive Market Analysis, Competitive Intelligence Report, Industry Trend Assessment, Corporate Performance Review. |
| Report Depth                | Executive Summary, Detailed Analysis, Comprehensive Review.                                       |
| Data Sources (pluggable)    | Financial databases, market research APIs, news scraping, regulatory filings.                     |
| Professional UI             | No icons or emojis; responsive layout; accessible colour contrasts; zero animations.              |
| Session Metrics             | Real-time counters for reports generated and entities analysed.                                   |

## Folder Structure

```
project_root/
│
├── universal_company_handler.py     # Fuzzy company/entity extraction
├── universal_validator.py           # Validates and routes user input
├── premium_formal_theme.css         # Global stylesheet
├── professional_news_analyzer.py    # Main Streamlit application
├── requirements.txt                 # Python dependencies
└── README.md                        # This document
```

## Installation

```bash
# Clone the repository
git clone https://github.com/your-org/professional-news-analytics.git
cd professional-news-analytics

# Create virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\\Scripts\\activate

# Install dependencies
pip install -r requirements.txt

# Download spaCy model
python -m spacy download en_core_web_sm
```

## Running the Application

```bash
# Activate virtual environment (if not already active)
source venv/bin/activate

# Launch Streamlit
streamlit run professional_news_analyzer.py
```

The dashboard starts locally on `http://localhost:8501`.  
For remote access (e.g., Colab) use a tunnelling service such as **ngrok** or **localtunnel**:

```python
from pyngrok import ngrok, conf
conf.get_default().auth_token = "YOUR_NGROK_TOKEN"
public_url = ngrok.connect(8501)
print("Public URL:", public_url)
```

## Configuration Options

| File                          | Parameter               | Description                                     |
|-------------------------------|-------------------------|-------------------------------------------------|
| `universal_validator.py`      | `topics` dictionary     | Add or adjust sector keywords.                  |
| `premium_formal_theme.css`    | Color variables         | Brand the UI to corporate guidelines.           |
| `professional_news_analyzer.py` | `analysis_type` list  | Customise available analysis frameworks.        |
| Any module                    | `DATA_API_KEYS`         | Insert credentials for premium data sources.    |

## Extending the Platform

1. **Additional NLP Models**  
   Swap or augment `spaCy` with transformer models for finer entity extraction.

2. **Custom Data Pipelines**  
   Implement new scrapers or API connectors and plug them into the analysis workflow.

3. **Automated Scheduling**  
   Use `streamlit-schedule` or a separate cron job to run periodic intelligence updates.

4. **Deployment**  
   Containerise the app with Docker for easier cloud or on-prem deployments.

## Known Limitations

* The free spaCy model occasionally misclassifies niche entities; consider training a custom model for domain-specific accuracy.  
* Real-time scraping is best-effort; some paywalled or rate-limited sources may require separate licences.  
* Large-scale concurrent users may exceed the default Streamlit server capacity—scale with gunicorn or Streamlit Community Cloud.

## License  
Distributed under the MIT License.
