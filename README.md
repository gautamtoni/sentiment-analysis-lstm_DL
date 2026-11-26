# Sentiment Analysis Using Bidirectional LSTM

## Project Overview

This project implements a Deep Learning-based Sentiment Analysis system using a Bidirectional Long Short-Term Memory (BiLSTM) network.

The model analyzes IMDb movie reviews and classifies them into two sentiment categories:

- Positive
- Negative

The project covers text preprocessing, tokenization, sequence padding, model training, evaluation, and sentiment prediction on new reviews.

## Dataset

- **Dataset:** IMDb Movie Reviews
- **Source:** Hugging Face
- **Total Reviews:** 50,000
- **Training Dataset:** 25,000 reviews
- **Testing Dataset:** 25,000 reviews
- **Classes:** Positive and Negative

Dataset Link: https://huggingface.co/datasets/stanfordnlp/imdb

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- Google Colab

## Data Preprocessing

The following preprocessing techniques were applied:

- Converted text into lowercase.
- Removed HTML tags.
- Removed URLs and special characters.
- Removed extra whitespace.
- Converted text into numerical sequences using Tokenizer.
- Applied padding and truncation to maintain a fixed sequence length of 250.

## Model Architecture

The project uses a Bidirectional LSTM neural network.

| Layer | Configuration |
|---|---|
| Embedding | 128 dimensions |
| Bidirectional LSTM | 64 units |
| Dropout | 0.5 |
| Dense | 64 neurons, ReLU |
| Dropout | 0.3 |
| Output | 1 neuron, Sigmoid |

- Optimizer: Adam
- Loss Function: Binary Crossentropy
- Batch Size: 64
- Maximum Epochs: 10
- Early Stopping and Model Checkpoint callbacks

## Model Evaluation

The trained model was evaluated using 25,000 unseen test reviews.

| Metric | Result |
|---|---:|
| Test Accuracy | 83.32% |
| Test Loss | 0.4158 |
| Macro Precision | 0.84 |
| Macro Recall | 0.83 |
| Macro F1-Score | 0.83 |

### Classification Report

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Negative | 0.90 | 0.75 | 0.82 |
| Positive | 0.79 | 0.91 | 0.85 |

### Confusion Matrix

![Confusion Matrix](results/confusion_matrix.png)

### Training Accuracy

![Training Accuracy](results/accuracy.png)

### Training Loss

![Training Loss](results/loss.png)

## Sentiment Prediction

The project includes a reusable prediction function that accepts a new movie review and returns:

- Predicted sentiment
- Prediction confidence

### Example Predictions

**Positive Review**

Input: "This movie was absolutely fantastic. The acting was brilliant and the story was amazing."

Prediction: Positive

Confidence: 97.67%

**Negative Review**

Input: "This movie was terrible. The acting was boring and the story was very disappointing."

Prediction: Negative

Confidence: 99.38%

## Project Structure

```text
Sentiment-Analysis-LSTM/
│
├── models/
│   ├── sentiment_lstm_model.keras
│   └── sentiment_tokenizer.pkl
│
├── results/
│   ├── accuracy.png
│   ├── loss.png
│   └── confusion_matrix.png
│
├── Sentiment_Analysis_DL.ipynb
├── requirements.txt
└── README.md
```

## How to Run

1. Clone this repository.
2. Install the required dependencies.
3. Open the Jupyter Notebook in Google Colab or Jupyter.
4. Run the notebook cells to explore preprocessing, training and evaluation.
5. Load the saved model and tokenizer to predict sentiment for new reviews.

Install dependencies:

```bash
pip install -r requirements.txt
```

## Key Learnings

- Text preprocessing and NLP fundamentals.
- Tokenization and sequence padding.
- Bidirectional LSTM architecture.
- Deep Learning model training and optimization.
- Model evaluation using precision, recall, F1-score and confusion matrix.
- Saving and loading trained models.
- Building reusable prediction functions.

## Limitations

- The model supports English-language sentiment classification.
- It was trained on IMDb movie reviews.
- Performance may vary on reviews from other domains.
- Confidence scores are model estimates and are not guarantees of correctness.

## Disclaimer

This project is developed for educational and portfolio purposes only.
