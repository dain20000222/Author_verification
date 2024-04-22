# Authorship Verification using GRU Models

Group21
- Da In Kim
- Minjun Choi

## Project Overview
This project is part of the COMP34812 Natural Language Understanding coursework at the University of Manchester. It features a Gated Recurrent Unit (GRU) model designed to verify authorship by determining if two sequences were authored by the same individual. The model is trained and evaluated using a specific dataset provided for this course, focusing on deep learning techniques to analyze writing styles.


## Data Sources
The dataset comprises approximately 30K training sequence pairs and 6K validation sequence pairs, provided exclusively for this coursework. These sequences are used to train and validate the model, ensuring it can effectively determine authorship based on textual similarities.


## Model Structure and Pipeline
### Data Pre-processing
- **Cleaning**: Convert text to lowercase, remove punctuation and stopwords.
- **Combining**: Text pairs are concatenated to form single inputs for verification.
- **Tokenization and Padding**: Sequences are tokenized and padded to ensure uniform input size.


### GRU Model Architecture
The model utilizes the GRU network for its ability to maintain important information through long sequences, ideal for style-based text analysis tasks such as authorship verification. The structure includes:
- **Embedding Layer**: Utilizes GloVe embeddings, which provide a robust foundation for the word representations.
- **GRU Layer**: Processes the text to capture the stylistic nuances that are indicative of authorship.
- **Global Average Pooling**: Condenses the sequence information into a single vector.
- **Fully Connected Layers**: Further processing and classification is done through dense layers with dropout for regularization.
- **Output Layer**: A sigmoid layer outputs the probability of texts being by the same author.


### Training and Evaluation
- **Compilation**: The model is compiled using Adam optimizer and binary cross-entropy loss, metrics include accuracy.
- **Early Stopping**: Used during training to prevent overfitting, monitoring validation loss.
- **Evaluation**: The model's effectiveness is assessed using accuracy, precision, recall, and F1-score on a held-out development set.


## Installation and Setup
Install necessary libraries using pip:
```bash
pip install tensorflow numpy pandas nltk
```
Ensure nltk resources are downloaded:

```bash
import nltk
nltk.download('stopwords')
```
## Running the Code

The Authorship Verification model can be executed using the `gru.ipynb` Jupyter notebook. To do so, follow these steps:

1. Open the `gru.ipynb` notebook in a Jupyter environment.
2. Ensure that all required libraries are installed. If not, install them using the notebook by running
3. Execute the cells in the notebook in order. The notebook will prompt you for the paths to the input text files.
4. Provide the paths to your text files when prompted, and the notebook will output the similarity score and authorship decision.

To facilitate a seamless experience, the notebook contains comments and instructions in each cell guiding you through the process.

Note: The notebook is pre-configured to run with default settings, which should be adequate for most use cases. However, if you need to adjust the parameters, you can modify the relevant cells within the notebook.

## Using the Model
Load the trained model to predict authorship of new text pairs:

- Prepare your input data in the same format as the training data.
- Use the model's predict method to get authorship probabilities.

## Model Card
For detailed information on the model's architecture, training data, metrics, and performance, please see the [Model card](https://github.com/JuneC7020/NLU2024/blob/main/GRU-BasedAuthorshipVerificationModelCard.md). This document provides comprehensive details that can help users and developers understand and utilize the model effectively.

## Acknowledgments
Thanks to the instructors and peers at the University of Manchester, and a special mention to the authors of the academic paper that guided our approach.

## References
This project utilizes concepts, data, and code from the following sources:
- [Qian, Chen, Tianchang He, and Rao Zhang. "Deep learning based authorship identification." Report, Stanford University (2017): 1-9](https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1174/reports/2760185.pdf)

