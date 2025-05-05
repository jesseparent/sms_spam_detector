# SMS Spam Detector 

A machine learning project that classifies SMS text messages as either **spam** or **ham** (not spam) using a Support Vector Classification (SVC) model and a Gradio interface for interactive testing.

---

## Project Overview

This project refactors an existing SMS text classification solution to:

1. Build a `LinearSVC` model using scikit-learn.
2. Wrap the logic in reusable functions.
3. Host an interactive Gradio app to test and visualize predictions in real time.

---

## Features

- Constructs a pipeline with `TfidfVectorizer` + `LinearSVC`  
- Classifies messages into "spam" or "ham"  
- Provides user feedback with clear prediction messages  
- Gradio web app interface for easy testing  
- Clean, modular, reproducible code

---

## Files in This Repository

- `SMSSpamCollection.csv` — Dataset of SMS messages labeled as spam or ham.
- `sms_text_classification_solution.ipynb` — Original notebook with classification logic.
- `gradio_sms_text_classification.ipynb` — Final notebook with modularized functions and Gradio UI.

---

## How It Works

### 1. `sms_classification(df)`

Creates and trains a text classification model using:
- `TfidfVectorizer` to convert text into numeric features
- `LinearSVC` classifier
- A pipeline to encapsulate the vectorization and model training

> **Note**: 33% of the dataset is reserved for testing.

### 2. `sms_prediction(text)`

Uses the trained model to classify a new SMS message:
- Returns:  
  `"The text message: '<message>', is spam."`  
  or  
  `"The text message: '<message>', is not spam."`

### 3. Gradio Interface

- Inputs: Text box for the user to enter a message  
- Outputs: Prediction label (spam / not spam)

---

## Sample Messages to Try

You can test the app with the following example messages:

1. `You are a lucky winner of $5000!`  
2. `You won 2 free tickets to the Super Bowl.`  
3. `You won 2 free tickets to the Super Bowl. Text us to claim your prize.`  
4. `Thanks for registering. Text 4343 to receive free updates on medicare.`

---

## Getting Started

### Install the dependencies

```bash
pip install pandas scikit-learn gradio
```

### Clone the Repository

```bash
git clone https://github.com/jesseparent/sms_spam_detector.git
cd sms_spam_detector
```

### Open Jupyter Notebook

- Open `gradio_sms_text_classification.ipynb` in VS Code
- Run cells to launch Gradio app NOTE: There is a cell to close teh app that must not be ru nor commented out to run app