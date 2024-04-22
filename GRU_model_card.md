---
{}
---
language: en
license: cc-by-4.0
tags:
- text-classification
repo: https://drive.google.com/drive/folders/1ftMmPac1U5CRPaPnI1JeFb1Tkt4_6Gs1?usp=drive_link

---

# Model Card for j33990dk-a35338mc-AV

<!-- Provide a quick summary of what the model is/does. -->

The GRU (Gated Recurrent Unit) model employed for Authorship Verification is designed to analyze textual data and determine if two text samples are written by the same author. This model utilizes a sequence-based deep learning approach, leveraging GRU layers to capture and analyze the temporal dependencies in text.  .


## Model Details

### Model Description

<!-- Provide a longer summary of what this model is. -->


    This GRU model is developed for the Authorship Verification (AV) task. It uses a sophisticated deep learning approach that operates without relying on transformer architectures. 
    Before the training, the paired text data are concatenated.
    The concatenated data is then embedded into a dense vector space through a pre-initialized Glove embeddings.
    Following the embedding layer, a GRU layer tracks and learns the sequential dependencies present in the merged text.
    The GRU's output is then condensed via global average pooling into a singular vector.
    Finally, the model incorporates a dense network with a regularization dropout layer, culminating in a sigmoid activation function that yields the probability of the texts having a common author.
    

- **Developed by:** Da In Kim and Minjun Choi
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** GRU
- **Finetuned from model [optional]:** tf.keras.layers.GRU

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** https://www.tensorflow.org/api_docs/python/tf/keras/layers/GRU
- **Paper or documentation:** https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1174/reports/2760185.pdf

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

The dataset comprises 30,000 pairs of text data with labels. 
    In the preprocessing stage, the training undergoes through a cleaning and preparation. 
    Initially, all text entries are converted to string format, normalized to lowercase, and stripped of punctuation to ensure uniformity.
    This is followed by the removal of English stop words to distill the content to its most informative elements. Consecutive stages involve eliminating extra whitespace, resulting in a clean and concise dataset. 
    For each record, the cleaned versions of text pairs (Text 1 and Text 2) are concatenated into a single sequence.
    A tokenizer is then employed to convert the textual data into tokens, which are then subsequently padded to a calculated optimal length. 
    

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


      - early_stopping_patience: 10
      - learning_rate: 0.001
      - train_batch_size: 32
      - eval_batch_size: 32
      - seed: NA
      - num_epochs: 50
      

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


      - overall training time: 3 minutes
      - duration per training epoch: 11 seconds
      - model size: 53.4MB

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data & Metrics

#### Testing Data

<!-- This should describe any evaluation data used (e.g., the development/validation set provided). -->

The model's performance was evaluated using a development dataset consisting of 3,000 text pairs, distinct from the training dataset. 
    This dataset undergoes the same preprocessing protocol as the training data, including standardization of text to lowercase, removal of punctuation and stopwords, and whitespace normalization.
    This ensures that the model is assessed under consistent conditions, allowing for a reliable measurement of its performance in authorship verification tasks.
    

#### Metrics

<!-- These are the evaluation metrics being used. -->


      - Accuracy: 0.5795
      - Precision: 0.5724465558194775
      - Recall: 0.6403188309531717
      - F1 Score: 0.6044834613575796
      

### Results

The model obtained an F1-score of 73.5% and an accuracy of 73.5% for predicting the labels of development data

## Technical Specifications

### Hardware


      - RAM: at least 15 GB
      - Storage: at least 3GB,
      - GPU: T4

### Software


      - Python version: 3.8+
      - TensorFlow 2.x

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->


    The preprocessing pads all text data to an optimal maximum length, which may not fully capture the complexity and variety of longer text entries.  
    The model's training corpus may not cover the extensive range of linguistic nuances across different authorship styles, which may lead to biases in prediction.
    

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

The hyperparameters were determined by experimentation
      with different values. This model leverages the glove.6B.100d.txt for its embeddings.
      
