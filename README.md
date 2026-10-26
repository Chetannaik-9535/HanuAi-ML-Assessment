# HanuAi Machine Learning Assessment

Enterprise ML Engineering Quality Suite featuring:
1. **Task 1: E-Commerce Web Scraping & Aspect-Based Sentiment Analysis (ABSA)**
2. **Task 2: Automotive Warranty Mining & Root Cause Telemetry Analysis**
3. **Interactive Web Application:** Production-grade Streamlit portal for live evaluation

---

## Repository Structure

```text
HanuAi-ML-Assessment/
│
├── app.py                                         # Streamlit Interactive Quality & Analytics Portal
├── requirements.txt                               # Pinned dependencies for Streamlit Community Cloud
├── .gitignore                                     # Python and IDE exclusions
│
├── task_1/                                        # Task 1: BestBuy Canada Scraping & ABSA
│   ├── Task1_WebScraping_Sentiment.ipynb          # Fully annotated Jupyter Notebook
│   └── BestBuy_Scraped_Reviews_Sentiment.csv      # 184 scraped reviews (7 mandatory fields & HanuAi ABSA tags)
│
├── task_2/                                        # Task 2: Automotive Warranty Mining & Root Cause
│   ├── raw_warranty_data.tsv                      # 154 claims (rows 1-5 tagged, rows 6+ blank)
│   ├── Task2_Advanced_EDA_TextMining.ipynb        # EDA, TTF engineering, NLP regex extraction, K-Means (K=5)
│   └── Automotive_Warranty_Mined_Dataset.csv      # 100% complete dataset (0 blank entity tags)
│
└── reports/                                       # Publication-Grade Engineering Reports
    ├── Task1_Anti_Scraping_and_Insights_Report.md # Anti-scraping technical strategies & Sony XM5 insights
    └── Task2_Stakeholder_Engineering_Report.md    # Executive Quality Committee warranty audit & ROI
```

---

## Key Highlights

### Task 1: Web Scraping & Aspect-Based Sentiment Analysis
- **Target:** Sony WH-1000XM5 Wireless Headphones (SKU: `16162187` / `16013054`).
- **Resilient Multi-Filter Scraping:** Traversed 5 sort filters (*Most Helpful*, *Newest*, *Highest Rating*, *Lowest Rating*, *Most Relevant*) with exponential backoff and jitter.
- **Dataset:** 184 reviews extracted with all 7 mandatory fields (`Primary Key`, `Title`, `Review Text`, `Date`, `Rating`, `Source Platform`, `Reviewer Name`).
- **HanuAi ABSA Tags:** Categorized reviews into standardized aspect tags:
  - `['Good Sound & ANC (Pos)']` / `['Poor Sound & ANC (Neg)']`
  - `['Good Design & Quality (Pos)']` / `['Poor Design & Quality (Neg)']`
  - `['Reliable Battery & Connectivity (Pos)']` / `['Battery or Connection Issues (Neg)']`
  - `['Great Value & Pricing (Pos)']` / `['Overpriced / Poor Value (Neg)']`
  - `['Satisfactory & Recommended (Pos)']` / `['Dissatisfied & Not Recommended (Neg)']`

### Task 2: Automotive Warranty EDA & NLP Text Mining
- **Benchmark Data:** 154 claims across 6 GM assembly plants (Flint 29.9%, Silao 24.7%).
- **Feature Engineering:** Calculated Time-to-Failure (`TTF_DAYS`) with an exact median of **124.0 days** and identified a $<90$-day infant mortality spike.
- **Rule-Based NLP Entity Mining:** 100% extracted entities across `Trigger`, `Failure Component`, `Failure Condition`, `Additional Context`, `Fix Component`, `Fix Condition`, and 6 `Issue Categories` with **zero blank tags remaining**.
- **Unsupervised Root Cause Clustering:** Applied TF-IDF vectorization and K-Means ($K=5$) to map physical failure modes (FAKRA coax crimp resistance, SiriusXM buffer ring overflow, CAN/Ethernet transceiver latch-up, SDIO ground offsets, and solder fatigue).
- **False Replacement Syndrome Discovery:** Identified that **28.6% of replaced radio head units were functionally intact**, having failed due to wiring harness and connector issues.

---

## Live Interactive Web UI (`app.py`)

### Run Locally
```bash
# Clone the repository
git clone https://github.com/Chetannaik-9535/HanuAi-ML-Assessment.git
cd HanuAi-ML-Assessment

# Create and activate virtual environment
python -m venv .venv
# On Windows:
.\.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Launch Streamlit app
streamlit run app.py
```

### Streamlit Community Cloud Deployment
1. Connect this GitHub repo to [share.streamlit.io](https://share.streamlit.io).
2. Set the main file path to `app.py`.
3. Click **Deploy** to access the live web application.
