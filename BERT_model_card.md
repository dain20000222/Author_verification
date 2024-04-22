---
{}
---
language: en
license: cc-by-4.0
tags:
- text-classification
repo: https://github.com/dain20000222/Author_verification

---

# Model Card for j33990dk-a35338mc-AV

<!-- Provide a quick summary of what the model is/does. -->


    This model employs a BERT-based approach for authorship verification, determining if two text samples are authored by the same person. 
Utilizing the inherent language understanding capabilities of BERT, coupled with cosine similarity measures, the model provides a nuanced assessment of authorship.
    


## Model Details

### Model Description

<!-- Provide a longer summary of what this model is. -->


    We fine-tuned a distilBERT Base model to classify pairs of texts for authorship verification. 
The model encodes texts to generate embeddings, which are then compared for similarity. 
A sigmoid activation function is applied to the output of a dense layer to provide a similarity score.
This model is based upon a BERT model that was fine-tuned on 60K pairs of  training text data.
    

- **Developed by:** Da In Kim and Minjun Choi
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** Transformers
- **Finetuned from model [optional]:** distilbert-base-uncased

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** https://huggingface.co/distilbert/distilbert-base-uncased
- **Paper or documentation:** https://ceur-ws.org/Vol-2936/paper-193.pdf

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

The dataset comprises 30,000 pairs of text data with labels. 
    In the preprocessing stage, any NA values within the text columns were replaced with empty strings to maintain data integrity. 
    Each text pair has gone through a specified index truncation and padding process to align with the input requirements of the model. 
    Subsequently, these processed text pairs were tokenized using the DistilBERT tokenizer, ensuring that the inputs are in the correct format for the DistilBERT model to encode. 
    

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


      - learning_rate: 5e-5
      - train_batch_size: 32
      - eval_batch_size: 32
      - seed: 42
      - num_epochs: 10
      

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


        - overall training time: 1 hour
        - duration per training epoch: 12 minutes
        - model size: 255.4MB
    

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data & Metrics

#### Testing Data

<!-- This should describe any evaluation data used (e.g., the development/validation set provided). -->


    The model's performance was evaluated using a development dataset consisting of 3,000 text pairs, distinct from the training dataset. 
    Similar to the training set, any NA values within the text columns of the development data were filled with empty strings to ensure consistency of the data. 
    Then, this development set were used to evaluate its efficacy in authorship verification of the model.
    

#### Metrics

<!-- These are the evaluation metrics being used. -->


      - Accuracy: 0.7335
      - Precision: 0.7320841551610783
      - Recall: 0.7396213882431086
      - F1 Score: 0.7358334710061126
      

### Results

The model obtained an F1-score of 73.5% and an accuracy of 73.5% for predicting the labels of development data

## Technical Specifications

### Hardware


      - RAM: at least 15 GB
      - Storage: at least 3GB,
      - GPU: T4

### Software


      - Python version: 3.8+
      - Transformers 4.18.0
      - Pytorch 1.6+

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->


    Any text data longer than 512 subwords will be truncated by the model. 
    The model's training corpus may not cover the extensive range of linguistic nuances across different authorship styles, which may lead to biases in prediction.
    

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

The hyperparameters were determined by experimentation
      with different values.
      
