# Authorship Verification using GRU and BERT

Group21
- Da In Kim
- Minjun Choi

## Project Overview
This project is part of the COMP34812 coursework, focusing on the Authorship Verification (AV) task. We employ GRU and BERT model to determine if two text sequences are written by the same author.

## Attribution
### Data Sources 
- **Training and Development Data**: Provided exclusively for the COMP34812 coursework, encompassing 30K training pairs and 6K development pairs.

### Inspirational Sources
- **Research Paper**: This implementation is inspired by the findings in [Deep learning based authorship identification](https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1174/reports/2760185.pdf) and [Siamese BERT for Authorship Verification](http://ceur-ws.org/Vol-2936/paper-193.pdf).

## Code base

### Model Links
Our trained models are stored on cloud platforms to ensure easy accessibility and reproducibility. 
All files used in this coursework can be found at [NLU Courswork Drive](https://drive.google.com/drive/folders/1ftMmPac1U5CRPaPnI1JeFb1Tkt4_6Gs1?usp=drive_link)

You can download and use the models from the following link:
- [GRU Authorship Verification Model](https://drive.google.com/file/d/1zEJXRFZe2_wmbCekr_Vvbf-5jsZ5GOwB/view?usp=drive_link) 
- [BERT Authorship Verification Model](https://drive.google.com/file/d/1oRUNyWGEJNvp8yqb3xJxOA_5edK1Kyan/view?usp=drive_link) 

### Running the Code
#### Prerequisites
Ensure you have Python installed on your system. This project is tested on Python 3.8+. You can download it from [Here](python.org).

#### Training GRU model
- Installation and Setup for GRU Authorship Verification Model
```bash
pip install pandas numpy tensorflow nltk scikit-learn
```
You must download the glove.6B.100d.txt file for the Glove embedding from [Here](https://www.kaggle.com/datasets/sawarn69/glove6b100dtxt )
To train the GRU Authorship Verification model can be executed using the gru_train.ipynb Jupyter notebook.



#### Training BERT model
- Installation and Setup for BERT Authorship Verification Model
```bash
pip install torch pandas transformers scikit-learn
```
The Authorship Verification model can be executed using the bert_train.ipynb Jupyter notebook.


#### Running the demo code



## References
This project utilizes concepts from the following sources:
- [Qian, Chen, Tianchang He, and Rao Zhang. "Deep learning based authorship identification." Report, Stanford University (2017): 1-9](https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1174/reports/2760185.pdf)
- [Tyo, Jacob, Bhuwan Dhingra, and Zachary C. Lipton. "Siamese Bert for Authorship Verification." CLEF (Working Notes). 2021](https://ceur-ws.org/Vol-2936/paper-193.pdf)
