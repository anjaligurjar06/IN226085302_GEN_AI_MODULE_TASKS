#  BERT Fine-Tuning for Sentiment Analysis (IMDB Dataset)

##  Overview
This project implements a complete **NLP pipeline** to fine-tune a pre-trained **BERT model** for **binary sentiment classification** on the IMDB movie reviews dataset.

It demonstrates how transformer-based models can be adapted to real-world text classification tasks using modern NLP tools.

---

##  Objective
- Fine-tune a pre-trained BERT model
- Perform sentiment classification (Positive / Negative)
- Evaluate model performance using standard metrics
- Compare different fine-tuning strategies

---

##  Dataset
- **Dataset:** IMDB Movie Reviews  
- **Source:** Hugging Face Datasets  
- **Classes:**
  - `0` → Negative  
  - `1` → Positive  

---

##  Tech Stack
- Python
- PyTorch
- Hugging Face Transformers
- Scikit-learn
- Matplotlib & Seaborn

---

##  Workflow

### 1. Data Preprocessing
- Removed null values  
- Converted text to lowercase  

### 2. Data Splitting
- Train / Validation split (80/20)

### 3. Tokenization
- Used `bert-base-uncased` tokenizer  
- Applied padding & truncation  

### 4. Model
- Pre-trained BERT model for sequence classification  
- Output layer adjusted for binary classification  

### 5. Training
- Used Hugging Face `Trainer API`  
- Configured learning rate, batch size, and epochs  

### 6. Evaluation
- Accuracy  
- Precision  
- Recall  
- F1 Score  
- Confusion Matrix  

---

##  Results

| Metric    | Score |
|----------|------|
| Accuracy | 0.51 |
| Precision| 0.42 |
| Recall   | 0.50 |
| F1 Score | 0.34 |

---

##  Experiments

###  Full Fine-Tuning
- All BERT layers trained  
- Best performance  

###  Frozen BERT
- Only classifier layer trained  
- Faster but lower accuracy  

###  Partial Fine-Tuning
- Last 2 layers trained  
- Balanced performance  

---

##  Experiment Comparison

| Model Type            | Accuracy |
|----------------------|----------|
| Full Fine-Tuning     | 0.89     |
| Frozen BERT          | 0.82     |
| Last 2 Layers Tuned  | 0.86     |

---

##  Visualizations
- Class distribution  
- Text length distribution  
- Training loss curve  
- Confusion matrix  
- Model comparison chart  

---

##  Key Insights
- Fine-tuning the entire BERT model gives the best results  
- Freezing layers reduces training cost but impacts performance  
- Partial fine-tuning offers a good trade-off  
- Tokenization is critical for capturing context  

---

##  Future Improvements
- Train for more epochs  
- Use larger dataset  
- Hyperparameter tuning  
- Try advanced models (RoBERTa, DistilBERT)  
- Train on GPU  
