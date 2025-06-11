# Vijayi_WFH_task1

# 📌 Objective
This project is part of an internship assignment by Vijayi WFH Technologies Pvt Ltd (May–June 2025). The task involves developing a machine learning pipeline that:

1. **Classifies** customer support tickets by:
   issue_type (multi-class)
   urgency_level (Low, Medium, High)

3. **Extracts key entities** from ticket text:
   Product names
   Dates
   Complaint-related keywords

# 📂 Dataset
File: ai_dev_assignment_tickets_complex_1000.xls

Columns:

ticket_id

ticket_text

issue_type (Label)

urgency_level (Label)

product (Used for entity validation)

# ✅ Task Breakdown
🔹 1. **Data Preprocessing**
Converted text to lowercase
Removed special characters and digits
Tokenized, removed stopwords
Lemmatized words using NLTK
Extracted basic text features:
  Ticket length
  Sentiment score (TextBlob)

🔹 2. **Feature Engineering**
Used **TF-IDF** vectorization (max 1000 features)
Combined with:
  Sentiment polarity
  Text length

**Feature Justification:**
**TF-IDF** captures important words based on frequency
**Sentiment polarity** adds emotional context
**Text length** reflects issue detail complexity

🔹 3. **Multi-Task Classification**
**Models:** Random Forest Classifier
**Tasks:**
  issue_type: multi-class
  urgency_level: Low, Medium, High

📊 **Evaluation:**
Both models were evaluated using:
  Accuracy
  Precision
  Recall
  F1-score
  Confusion Matrix

🔹 4. **Entity Extraction**
Used rule-based methods to extract:
**Product names** from known list
**Dates** using regex pattern
**Complaint keywords** (e.g., "broken", "error", "late", "missing")

**Output format:**
{
  "product": "Smart TV",
  "dates": ["15 June 2025"],
  "keywords": ["broken", "late"]
}
🔹 5. **Integrated Inference Function**

def analyze_ticket(ticket_text):
    return {
        "issue_type": "...",
        "urgency_level": "...",
        "entities": {
            "product": "...",
            "dates": [...],
            "keywords": [...]
        }
    }
🔹 6. **Gradio App (Optional)**
An interactive Gradio interface allows real-time predictions for new tickets.

# 🧪 Results
Example results for test data:
  Accuracy: ~87% for issue_type, ~81% for urgency_level
  Model performance was stable across random seeds
  Confusion matrices included in the notebook

# 💡 Limitations
Product names are matched via string rules — could miss misspellings
Limited generalization if vocabulary differs in new ticket types
Only classical ML was used (no deep learning/transformers)

# ▶️ Demo Video
🔗 Google Drive Video Link (replace with your actual video link)

# 🗂️ Files Submitted

task1_ticket_classifier_preprocessing_fixed.ipynb – full code notebook
README.md – this file
demo_video.mp4 – short walkthrough video

# 🔧 Setup Instructions
1. Install required packages:
   pip install pandas nltk textblob scikit-learn gradio

2. Download NLTK assets:
   import nltk
   nltk.download('stopwords')
   nltk.download('punkt')
   nltk.download('wordnet')

3. Run notebook or launch the app:
   python gradio_app.py

# 🙋 Author
Parmeet Kaur
Internship Assignment – Vijayi WFH Technologies Pvt Ltd (May–June 2025)

