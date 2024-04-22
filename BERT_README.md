# Authorship Verification using BERT

Group21
- Da In Kim
- Minjun Choi

## Project Overview
This project is part of the COMP34812 coursework, focusing on the Authorship Verification (AV) task. We employ deep learning-based approaches underpinned by transformer architectures, specifically using a BERT model to determine if two text sequences are written by the same author.

## Data Sources 
**Training and Development Data**: Provided exclusively for the COMP34812 coursework, encompassing 30K training pairs and 6K development pairs. These datasets were utilized within the coursework guidelines. These data are specifically structured for the AV task and have been preprocessed accordingly to fit the input requirements of the BERT models.

### Inspirational Sources
- **Research Paper**: This implementation is inspired by the findings in [Siamese BERT for Authorship Verification](http://ceur-ws.org/Vol-2936/paper-193.pdf) by Jacob Tyo et al. The paper details the use of Siamese network structures with BERT for effective authorship verification.

## Model Description
The Authorship Verification model uses a dual BERT architecture to encode two pieces of text and determine their authorship. The process involves the following steps:

1. **BERT Encoding**: Each text (Text 1 and Text 2) is fed into its own BERT model, which encodes the text into a sequence of vectors.

2. **Mean Pooling**: The sequence of vectors from each BERT model is then subjected to mean pooling, reducing them to a single vector that captures the essence of the text.

3. **Dense Layer**: The pooled vectors are passed through a dense layer, resulting in a fixed-size text encoding for each text.

4. **Compute distance metric**: The encodings for Text 1 and Text 2 are compared using a distance metric, outputting a score between 0 and 1. A score closer to 1 suggests that the texts were likely written by the same author, while a score closer to 0 suggests different authors.


## Getting Started
### Prerequisites
- Python 3.8+
- Transformers library
- PyTorch


## Codebase Usage
### Installation
To run this project, you must first set up your Python environment and install the necessary libraries. This project relies on the Transformers library by Hugging Face, which can be installed using pip:

```bash
pip install transformers
```

### Running the Code
The Authorship Verification model can be executed using the `bert.ipynb` Jupyter notebook. To do so, follow these steps:

1. Open the `bert.ipynb` notebook in a Jupyter environment.
2. Ensure that all required libraries are installed. If not, install them using the notebook by running:
    ```python
    !pip install transformers torch
    ```
3. Execute the cells in the notebook in order. The notebook will prompt you for the paths to the input text files.
4. Provide the paths to your text files when prompted, and the notebook will output the similarity score and authorship decision.

The notebook contains comments and instructions to guide you through the process, facilitating a seamless experience.

*Note: The notebook is pre-configured to run with default settings, which should be adequate for most use cases. 
However, if you need to adjust the parameters, you can modify the relevant cells within the notebook.*

## Model Links and Storage
Our trained models are stored on cloud platforms to ensure easy accessibility and reproducibility. You can download and use the models from the following link:
- [BERT Authorship Verification Model](https://drive.google.com/file/d/1oRUNyWGEJNvp8yqb3xJxOA_5edK1Kyan/view?usp=drive_link) 

## Model Card
For detailed information on the model's architecture, training data, metrics, and performance, please see the [Model card](https://github.com/JuneC7020/NLU2024/blob/main/BERT_model_card.md). This document provides comprehensive details that can help users and developers understand and utilize the model effectively.


## Attribution
This project uses the Hugging Face Transformers library for the BERT model implementations:
Hugging Face Transformers

## License
This project is released under the MIT License. See the LICENSE file for more details. (Link to your LICENSE file in the repository)

## References
This project utilizes concepts, data, and code from the following sources:
- [Tyo, Jacob, Bhuwan Dhingra, and Zachary C. Lipton. "Siamese Bert for Authorship Verification." CLEF (Working Notes). 2021](https://ceur-ws.org/Vol-2936/paper-193.pdf)
