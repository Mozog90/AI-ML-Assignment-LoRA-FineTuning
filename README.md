Author: Mateusz Ozog
Course: AI/ML – Fine-Tuning Assignment

Project Overview

This project fine-tunes a pre-trained DistilBERT model using LoRA (Low-Rank Adaptation) for a sentiment classification task. The goal is to train efficiently on a local machine by updating only a small number of parameters.

Dataset

I used the IMDb dataset from Hugging Face Datasets.
Labels:

0 = Negative

1 = Positive

A smaller subset of the data was used to keep training time manageable.

Model

Base model: distilbert-base-uncased
Task: Binary sentiment classification
The model includes a classification head with two labels.

LoRA Configuration

r = 8

lora_alpha = 32

lora_dropout = 0.1

target_modules = ["q_lin", "v_lin"]

Task type: Sequence Classification

Only the LoRA parameters and the classifier head were trained. All other model weights stayed frozen.

Training

Training was done with the Hugging Face Trainer.
Settings included:

Batch size: 16 for training, 32 for evaluation

Learning rate: 3e-4

1 or 2 epochs

Evaluation at each epoch

Results

Replace these with your numbers after running evaluation:

Test Accuracy:

Test F1 Score:

The fine-tuned model performed better than a non-fine-tuned baseline.

Example Predictions

"This movie was fantastic, I loved it." → Positive

"The acting was good, but the story was slow and confusing." → (Your model's output)

Repository Contents

notebook.ipynb

requirements.txt

README.md