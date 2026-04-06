#  Fine-Tuning BERT for POS Tagging & Chunking

##  Project Overview
This project demonstrates how to fine-tune a transformer model (**BERT**) for token classification tasks, specifically Part-of-Speech (POS) Tagging and Chunking (Phrase Detection). It follows a complete NLP pipeline including preprocessing, training, evaluation, and inference using Hugging Face Transformers.

---

##  Objective
- Build a token classification model using BERT  
- Perform POS tagging and chunking  
- Handle tokenization challenges such as subwords and label alignment  
- Evaluate model performance using Precision, Recall, and F1-score  

---

##  Tech Stack
- Python  
- Hugging Face Transformers  
- Datasets  
- PyTorch  
- SeqEval  
- Jupyter Notebook  

---

##  Dataset Used
**CoNLL-2003 Dataset**

### Features:
- Tokens  
- POS Tags  
- Chunk Tags  
- Named Entity Tags  

### Label Types:
- POS Tags → Grammar-based labels (e.g., NOUN, VERB)  
- Chunk Tags → Phrase-based labels (e.g., NP, VP)  

---

##  Pipeline Flow
Raw Data → Tokenization → Label Alignment → Model Training → Evaluation → Inference → Comparison  

---

##  Implementation Steps

### 1. Data Preprocessing
- Tokenization using BERT tokenizer  
- Alignment of labels with tokens  
- Handling:
  - Subwords  
  - Special tokens (`[CLS]`, `[SEP]`)  
  - Ignored labels (`-100`)  

---

### 2. Model Setup
- Model: `bert-base-uncased`  
- Used `AutoModelForTokenClassification`  

Configured:
- `num_labels`  
- `id2label`  
- `label2id`  

---

### 3. Training
Used Hugging Face Trainer API  

**Key Parameters:**
- Learning Rate: `2e-5`  
- Epochs: `3`  
- Batch Size: `16`  

---

### 4. Evaluation
Used SeqEval metrics:
- Precision  
- Recall  
- F1 Score  

---

### 5. Inference

**Example Input:** John works at Google in California

**Output:**

John → PROPN
works → VERB
at → ADP
Google → PROPN
in → ADP
California → PROPN

---


##  Results
The model achieves strong performance due to the contextual understanding of BERT:
- High accuracy on POS tagging  
- Good performance on chunking  

---

##  Comparison: POS Tagging vs Chunking

| Feature     | POS Tagging | Chunking |
|------------|------------|----------|
| Level      | Word-level | Phrase-level |
| Difficulty | Easy       | Medium |
| Purpose    | Grammar    | Structure |

---

##  Challenges Faced
- Handling subword tokenization  
- Aligning labels correctly  
- Managing special tokens  
- Device mismatch issues (CPU vs GPU)  

---

##  Observations
- BERT performs well due to contextual embeddings  
- POS tagging is simpler compared to chunking  
- Proper preprocessing significantly impacts performance  

---

##  Key Learnings
- Token classification using transformers  
- Importance of label alignment  
- Efficient use of Trainer API  
- Sequence evaluation using SeqEval  

---

