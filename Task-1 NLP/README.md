# NLP Text Preprocessing Pipeline

## Overview
This task builds a **complete NLP text preprocessing pipeline** using Python and NLTK.  
The goal is to clean noisy text, tokenize it, analyze tokens, and create a reusable pipeline that can process real-world messy text inputs.

Real-world text data often contains:
- URLs
- Emails
- Numbers
- Emojis
- Repeated characters
- Extra spaces
- Special characters

This project removes such noise and prepares text for NLP tasks.

---

# Project Tasks

## Task 1: Conceptual Understanding

### 1. Difference between "Love" and "love" in NLP
NLP models are case-sensitive.  
"Love" and "love" are treated as different tokens.  

Example:
```
Love → may appear at the beginning of a sentence
love → commonly used as a verb or noun
```

To avoid duplication, we apply **text normalization** by converting everything to lowercase.

---

### 2. What happens if stopwords are not removed?
If stopwords are not removed, the dataset becomes filled with common but uninformative words like:

```
the, is, and, a
```

This creates noise and can reduce model accuracy because important words become diluted.

---

### 3. When removing stopwords can be harmful

#### Sentiment Analysis
Removing words like **"not"** can completely change the meaning.

Example:
```
not good → good
```

#### Question Answering / Search
Words like **who, where, when** contain important intent.

Removing them may produce incorrect search results.

---

### 4. Stemming vs Lemmatization

**Stemming**
- Removes suffixes
- Faster
- May produce non-dictionary words

Example:
```
running → run
playing → play
```

**Lemmatization**
- Uses linguistic rules
- Returns dictionary base form
- More accurate but slower

Example:
```
better → good
running → run
```

---

# Task 2: Advanced Preprocessing Function

The main preprocessing function cleans the text using several steps.

Steps performed:

1. Convert text to lowercase
2. Remove URLs
3. Remove email addresses
4. Remove numbers
5. Reduce repeated characters
6. Remove special characters
7. Remove extra spaces
8. Tokenize words

Example transformation:

```
Input:
"I absolutely looooved this product 😍😍"

Output:
['i', 'absolutely', 'loved', 'this', 'product']
```

---

# Task 3: Stress Testing

The function was tested with noisy sentences including:

```
Get 100% FREE access now!!!
I absolutely looooved this product 😍😍
Worst service ever... 0/10
Call me at 9876543210
Visit https://openai.com now!
Nooooo this is baaad!!!
OK OK OK I got it
Win $$$ now!!! Limited offer!!!
I am not happy with this
```



The preprocessing pipeline successfully cleaned them.

---

# Task 4: Token Analytics

For each sentence we computed:

- Total token count
- Unique token count
- Average token length

Example:

Sentence:
```
OK OK OK I got it
```

Results:

```
Token Count: 6
Unique Tokens: 4
Average Token Length: 2.0
```

This helps understand text complexity and redundancy.

---

# Analysis

### Most Noisy Sentence
```
Win $$$ now!!! Limited offer!!!
```

Reason:
- Contains heavy symbols
- Requires major cleanup

Other noisy sentences:
```
Get 100% FREE access now!!!
Call me at 9876543210
```

---

### Sentence with Most Meaningful Tokens

```
I absolutely looooved this product 😍😍
```

Reason:
- Contains descriptive words
- Meaning remains intact even after cleaning

---

# Task 5: Frequency Analysis

We used Python's **Counter** to analyze word frequencies.

### Top Frequent Words

Example:

```
this: 4
now: 3
i: 3
ok: 3
is: 2
```



# Observations

### Data Sparsity
Most words appear only once.  
This happens when the dataset is small.

### Common Words Dominate
Words like:

```
this
now
is
```

appear frequently but carry little meaning.

---

# Task 6: Full NLP Pipeline

A reusable pipeline was created:

```
def full_pipeline(text_list)
```

This pipeline:

1. Processes multiple sentences
2. Collects all tokens
3. Returns cleaned sentences

Example output:

```
{
  "tokens": [...],
  "clean_sentences": [...]
}
```

---

# Task 7: Error Handling

The function also handles edge cases safely.

Test cases:

```
""
"😍😍😍"
"1234567890"
None
```

Output:

```
tokens = []
cleaned_sentence = ""
```

This prevents runtime errors and ensures robustness.

---

# Technologies Used

- Python
- NLTK
- Regular Expressions (re)
- Collections Counter
- Google Colab / Jupyter Notebook

---

# Learning Outcomes

From this project I learned:

- How real-world text contains heavy noise
- Importance of text preprocessing
- Token analysis techniques
- Word frequency analysis
- Building reusable NLP pipelines

---

# Possible Improvements

Future upgrades could include:

- Stopword removal
- Stemming
- Lemmatization
- TF-IDF vectorization
- Sentiment analysis
- Named Entity Recognition

---
