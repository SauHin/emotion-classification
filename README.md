# A Comparative Study of NLP Models for Emotion Classification on Indonesian-Language Twitter Text

---

## Abstract

Emotion classification in Indonesian-language
social media text faces two fundamental challenges, the noisy
linguistic profile of Twitter text and severe class imbalance. To
address these, this study compares three machine learning
categoris on the EmoT dataset from IndoNLU, comprising 4,401
samples across five emotion classes: Classical Machine Learning
(Complement Naive Bayes/CNB, SVM, Random Forest), a
sequential Bidirectional Long Short-Term Memory (BiLSTM)
model with FastText embeddings, and Pre-trained
Transformers from both the general domain (IndoBERT) and
the Twitter-specific domain (IndoBERTweet). Based on Macro
Average F1-Score, IndoBERTweet achieves the best result at
0.76, ahead of IndoBERT (0.70), CNB (0.69), SVM (0.67),
Random Forest (0.64), and BiLSTM (0.63). Three findings stand
out. First, the proximity between the pre-training data domain
and the downstream task's data distribution has a greater
deterministic effect than model parameter size. Second, CNB
proves to be a stronger baseline than BiLSTM under limited,
imbalanced dataset conditions. Third, the superiority of
IndoBERTweet over CNB is statistically significant, confirmed
by McNemar's Test with p-value = 0.0066.


---

## Demo

Youtube link: [Presentation & App Demo Video](https://www.youtube.com/watch?v=1jC9Udfpm98)


---

## Dataset

Source: [EmoT dataset from IndoNLU](https://github.com/IndoNLP/indonlu/tree/master/dataset/emot_emotion-twitter)

---

## Project Structure

```
emotion-classification
├── Datasets
│   ├── preprocessed
│   │   ├── test_cleaned_checkpoint.csv     
│   │   ├── train_cleaned_checkpoint.csv
│   │   └── valid_cleaned_checkpoint.csv
│   └── raw
│       ├── colloquial-indonesian-lexicon.csv   # For slang normalization ([Source](https://github.com/nasalsabila/kamus-alay/blob/master/colloquial-indonesian-lexicon.csv))
│       ├── test_preprocessed.csv
│       ├── train_preprocessed.csv
│       └── valid_preprocessed.csv
├── notebooks
│   ├── 01_EDA_Preprocess.ipynb # Dataset EDA + Preprocess
│   ├── 02_Classical.ipynb      # CNB, RF SVM
│   ├── 03_BiLSTM.ipynb         # BiLSTM + FastText
│   ├── 04_Transformer.ipynb    # IndoBERT, IndoBERTweet
│   ├── 05_Evaluation.ipynb     # Evaluation on all model
│   └── 06_App.ipynb            # Simple app using Gradio
├── results
│   ├── y_pred_bcnb.npy         # CNB tuned
│   ├── y_pred_bert.npy         # IndoBERT
│   ├── y_pred_bilstm_ft.npy    # BiLSTM
│   ├── y_pred_brf.npy          # RF tuned
│   ├── y_pred_bsvm.npy         # SVM tuned
│   ├── y_pred_tweet.npy        # IndoBERTweet
│   └── y_test.npy              # y_test for evaluation
└── README.md
```