# Named Entity Relation Extraction Using Deep Learning

## Project Overview

### Problem Statement
The objective of this project is to develop a state-of-the-art Named Entity Relation (NER) extraction model using deep learning techniques. NER plays a vital role in information extraction tasks by identifying and classifying entities mentioned in text, along with their relationships.

### Motivation
Named Entity Recognition (NER) is crucial in various natural language processing (NLP) applications, including information retrieval, question answering, and sentiment analysis. Accurate entity extraction enhances the effectiveness of these applications, making NER an essential component of many AI systems. In domains such as finance, legal, and healthcare, precise entity recognition is vital for compliance, risk assessment, and decision-making. Refining NER models improves performance and contributes to the reliability of AI-powered solutions.

### Literature Review
The literature review provides an in-depth understanding of NER models and architectures such as BERT and GPT, as well as LSTM-CRF. Legacy datasets like CoNLL-2003 provide labeled data. Deep learning addresses challenges like contextual understanding and forming relations between words and entities, creating knowledge graphs to maximize the utility of textual data.

## Methods

### Dataset Loading and Preprocessing
- **Dataset**: CoNLL-2003, a benchmark dataset for NER problems, was used. It contains sentences with named entities like persons, organizations, locations, and miscellaneous entities.
- **Preprocessing**: 
  - Tokenization: Breaking sentences into individual tokens/words.
  - Alignment: Mapping tokens to corresponding labels (e.g., "Apple" mapped to "B-ORG", "Inc." to "I-ORG").
  - Example: For the sentence "Apple Inc. is a tech company," "Apple" and "Inc." are tokenized and labeled accordingly.

### Mapping Functions and Data Preparation
- **Tokenization and Alignment**: The function `tokenize_and_align_labels` was applied to ensure each token is aligned with its respective label.
- **Training Arguments**: Defined batch size, learning rate, and the number of epochs.
- **Data Collator**: Created batches from dataset elements for efficient evaluation metrics.

### Model Training Setup
- **Trainer Object**: Utilized the `Trainer` object from the Hugging Face library to facilitate model training. This interface allows defining and modifying parameters for training.
- **Model Adjustments**: Adapted the model to recognize specific datasets and predict entity labels.

### NER Pipeline Implementation
- **Implementation**: Configured and tested the NER pipeline. The model achieved 97% accuracy and can be further optimized for automation tasks.
- **Use Cases**: Entity recognition, classification, and information extraction in various NLP applications.

## Evaluation Metrics
- **Precision**: Measures the accuracy of predicted named entities (true positives / (true positives + false positives)).
- **Recall**: Quantifies the ability to capture all relevant named entities (true positives / (true positives + false negatives)).
- **F1-Score**: Harmonic mean of precision and recall (2 * (precision * recall) / (precision + recall)).
- **Accuracy**: Overall correctness of predictions (true positives + true negatives / total instances).

### Example Sentences
- **Example 1**: "Tom works at Apple"
  ```json
  [{'entity': 'B-PER', 'score': 0.954, 'index': 1, 'word': 'tom', 'start': 0, 'end': 3}, 
   {'entity': 'B-ORG', 'score': 0.884, 'index': 4, 'word': 'apple', 'start': 13, 'end': 18}]
