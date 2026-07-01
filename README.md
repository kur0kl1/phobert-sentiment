Vietnamese Sentiment Classification with PhoBERT

Fine-tuned PhoBERT (vinai/phobert-base), a pretrained Vietnamese language model, for 3-class sentiment classification on student feedback text.

Dataset

UIT-VSFC — Vietnamese Students' Feedback Corpus.
Labels: negative, neutral, positive.

SplitExamplesTrain11,426Validation1,583Test3,166

Results

MetricScoreTest AccuracyTODOTest Macro F1TODO

EpochTrain LossVal AccuracyVal F11TODOTODOTODO2TODOTODOTODO3TODOTODOTODO

(fill in from your training run output)

How it works

PhoBERT is RoBERTa pretrained specifically on Vietnamese text, using a Vietnamese-specific word-segmenter and tokenizer, which gives it a meaningful edge over general multilingual models (like mBERT or XLM-R) on Vietnamese NLP tasks. This project fine-tunes it by adding a classification head on top of the [CLS] token representation and training end-to-end on the labeled sentiment data.

Usage

bashpip install -r requirements.txt
python phobert_finetune.py --epochs 3 --batch_size 16

The script downloads the dataset automatically from HuggingFace, fine-tunes PhoBERT, prints per-epoch validation metrics, and saves the final model to ./phobert_sentiment_model.

Note: training is significantly faster on GPU (~10-15 min on a free Colab GPU vs 1-2 hrs on CPU).

Project structure

.
├── phobert_finetune.py     # training & evaluation script
├── requirements.txt
└── README.md

References


Nguyen, D. Q., & Nguyen, A. T. (2020). PhoBERT: Pre-trained language models for Vietnamese
UIT-VSFC dataset
