# Smart-Desk
Smart Desk: NLP system that classifies IT support tickets, routes them to the right team, predicts resolution time, and detects anomalous days, with an interactive Streamlit dashboard.
# Smart Desk 🎫
An intelligent system for automated IT support ticket analysis: NLP classification, team routing, resolution time prediction, and anomaly detection.

🔗 **Live dashboard:** [PASTE_STREAMLIT_LINK_HERE](PASTE_STREAMLIT_LINK_HERE)

## Business Problem
IT tickets are sorted and routed by hand, so they sit in the wrong queue and break SLAs.
**Question:** How can NLP classify issues, route tickets to the right team, predict resolution times, and detect unusual ticket surges early?

## Dataset
- 100,000 synthetic IT support tickets (Jan 2022 to Dec 2025)
- 19 columns, 96 unique message templates
- Targets: `issue_type` (8 classes), `product_area` (7 teams), `resolution_time_hours`

## Approach
1. Data cleaning and EDA
2. Feature engineering (time, message, customer features)
3. Text processing with NLTK and TF-IDF (unigrams + bigrams)
4. Model comparison with grouped splits and leakage checks
5. Streamlit dashboard

## Results
| Task | Model | Result |
| Issue classification | TF-IDF + Random Forest | Macro F1 0.605 ± 0.107 on unseen messages |
| Team routing | TF-IDF + Logistic Regression | 57.4% accuracy, 71.6% top-3 accuracy |
| Text representation | TF-IDF vs Sentence-BERT | No clear winner; TF-IDF chosen |
| Resolution time | Gradient Boosting (MAE loss) | MAE 15.2 h, equal to median baseline |
| Anomaly detection | Isolation Forest + LOF | 45 high-confidence days, 10/10 injected surges detected |

## Dashboard Pages
- **Overview:** KPIs and ticket distributions
- **Ticket Classifier:** type a message to get the issue type and top-3 teams
- **Anomaly Monitor:** flagged days and spiking issue types
- **Model Performance:** model comparisons and key findings

## Run Locally
```bash
pip install -r requirements.txt
streamlit run app.py
```

## Limitations & Next Steps
- Synthetic data with only 96 unique messages
- Next: test on real ticket data, fine-tune BERT, add workload and agent features
Alhanouf Abdullah Alobaid · Sara Mohammed Alshahrani · Raghad Suliman Albalawi · Wojood Turki Almalki

Saudi Digital Academy · WeCloudData Data Science Bootcamp · 2026
