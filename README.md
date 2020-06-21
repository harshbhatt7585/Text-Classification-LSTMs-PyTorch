# Text Classification through a LSTM-based model

The aim of this repository is to show a baseline model for text classification by implementing a LSTM-based model coded in PyTorch. In order to provide a better understanding of the model, it will be used a dataset of Tweets provided by Kaggle. 

## 1. Data
As it was mentioned above, the implemented dataset is about Tweets regarding fake news. The ``raw``dataset contains some unnecessary columns which are going to be removed in the preprocessing step, in the end, we will be working with a dataset with a head such as this: 

|id| text | target |
| ------------- | ------------- | ------------- |
| 1  | Our Deeds are the Reason of this #earthquake May ALLAH Forgive us all  |1  |
| 2  | SOOOO PUMPED FOR ABLAZE ???? @southridgelife  | 0  |
| 3  | INEC Office in Abia Set Ablaze - http://t.co/3ImaomknnA  | 1 |
| 4  | Building the perfect tracklist to life leave the streets ablaze  | 0  |

This raw dataset can be found in ``data/tweets.csv``. 

## 2. The model
As it was already commented, the aim of this repository is to provide a base line model for text classfication. In this sense, the model is based on a two-stacked LSTM layers followed by two linear layers. The dataset is preprocessed through a tokens-based technique, then tokens are associated to an embedding layer. The following image describes the pipeline of the model.
<p align="center">
<img src='img/model_architecture.png'>
</p>

## 3. Install dependencies
Working on

## 4. How to use it
The model can be executed easily by typing:
```
python main.py
```
You can define some hyperparameters manually, such as:
```
 main.py [-h] [--epochs EPOCHS] [--learning_rate LEARNING_RATE]
         [--hidden_dim HIDDEN_DIM] [--lstm_layers LSTM_LAYERS]
         [--batch_size BATCH_SIZE] [--test_size TEST_SIZE]
         [--max_len MAX_LEN] [--max_words MAX_WORDS]
```

## 5. Demo
The follwowing configuration was implemented in order to achieve the best results
```
python -B main.py --epochs 10 --learning_rate 0.01 --hidden_dim 128 --lstm_layers 2 --batch_size 64
```
by getting the following output:
```
Epoch: 1, loss: 0.53032, Train accuracy: 0.59376, Test accuracy: 0.63099
Epoch: 2, loss: 0.43361, Train accuracy: 0.63251, Test accuracy: 0.72948
Epoch: 3, loss: 0.36803, Train accuracy: 0.76141, Test accuracy: 0.75509
Epoch: 4, loss: 0.26117, Train accuracy: 0.80821, Test accuracy: 0.77807
Epoch: 5, loss: 0.19844, Train accuracy: 0.83547, Test accuracy: 0.77741
Epoch: 6, loss: 0.16377, Train accuracy: 0.86453, Test accuracy: 0.77216
Epoch: 7, loss: 0.02130, Train accuracy: 0.88391, Test accuracy: 0.75509
Epoch: 8, loss: 0.00315, Train accuracy: 0.89704, Test accuracy: 0.74787
Epoch: 9, loss: 0.02075, Train accuracy: 0.91018, Test accuracy: 0.76428
Epoch: 10, loss: 0.01348, Train accuracy: 0.92808, Test accuracy: 0.75378
```
So the learning curves will look like:
<p align="center">
<img src='img/performance.svg'>
</p>