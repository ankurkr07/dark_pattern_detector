# Detecting Dark Patterns in Text Data Using BiLSTM

This project focuses on developing a machine learning model to identify dark patterns in text data, particularly targeting deceptive or manipulative phrases commonly found on e-commerce websites. Dark patterns refer to user interface design choices crafted to deceive or manipulate users into making decisions that may not be in their best interest.

## Overview
Dark patterns pose ethical concerns in user experience design as they exploit human psychology for the benefit of website owners. This project aims to automate the detection of such patterns using a bidirectional Long Short-Term Memory (BiLSTM) neural network.

## Implementation
- **Data Preprocessing:**
  - The dataset is imported from a CSV file using Pandas.
  - Text labels are encoded using a label encoder.
  - Tokenization is performed using Keras's Tokenizer, with a maximum vocabulary size of 10,000.
  - Sequences are padded to ensure uniform length for model input.

- **Model Architecture:**
  - The model architecture comprises an embedding layer followed by a bidirectional LSTM layer.
  - A Spatial Dropout layer is incorporated to prevent overfitting.
  - Binary classification is performed using a dense layer with ReLU activation.

- **Training and Evaluation:**
  - The dataset is split into training and testing sets (80% training, 20% testing).
  - The model is compiled with binary cross-entropy loss and Adam optimizer.
  - Training is conducted for 5 epochs with a batch size of 64.
  - Model performance is evaluated using accuracy metrics on the test set.

- **Model Persistence:**
  - After training, the model is saved using pickle for future use.

- **Inference:**
  - The saved model is loaded for inference on new texts.
  - New text sequences are tokenized and padded.
  - Predictions are made on the padded sequences to identify dark patterns.
  - Decoded predictions are inverse transformed to obtain meaningful labels.

## Results
Upon evaluation, the model demonstrates its efficacy in detecting dark patterns from text data, achieving a respectable accuracy. The identified dark patterns are printed for further analysis and action.

## Usage
- Ensure Python and the required libraries are installed (`numpy`, `pandas`, `scikit-learn`, `keras`).
- Clone the repository and navigate to the project directory.
- Run the script to train the model and save it.
- Use the saved model for inference on new text data to identify dark patterns.
