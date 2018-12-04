# ChatBot using keras

## Dependencies
This model is constructed on Keras 2.2.2.
```
pandas
numpy
re
time
operator.itemgetter
copy.deepcopy
keras.models.Model
keras.layers.Input
keras.layers.LSTM
keras.layers.Dense
```


## Data Pre-preprocessing + Model Construction

Run code under block data **Pre-preprocessing** and **Model Construction** to complete pre-processing and establish the encoder-decoder model.

## Loading Pre-train Model

Our model is trained for 1000 epochs. Model can be loaded using keras.load_model from file `chatModel.h5` using
```
from keras.models import load_model
model = load_model('chatModel.h5')
```


**If pre-trained model is loaded, the model need not to be trained again. You can proceed to the next step.** Otherwise, run 
```
model.fit([encoder_input_data,decoder_input_data],decoder_target_data,batch_size=batch_size,epochs=1000,validation_split=0.2)
```
to train the encoder-decoder model.

## Decode Result
Run `Decode Result` code block to use the model we trained  to construct the pipeline(word sampling etc.) for chatting.

## Run Chatting
```
while True:
    print('==========================')
    input_seq = input("Human:")
    decoded_sentence = decode_sequence(get_input_embedding(input_seq))
    print('Chatbot:', decoded_sentence)
```

Run this block to start a chatting session.

## Limitations
1. Computational Resources are limited. 
2. Low efficiency and flexibility by implementing Chatbot on Keras in model construction. Traning a Keras-based model takes more time and making improvement over relatively detailed aspects of the model is harder compared to model using other libraries

## Referrence
[1] https://github.com/jkarimi91/chatbot[2] https://blog.keras.io/a-ten-minute-introduction-to-sequence-to-sequence-learning-in-keras.html[3] https://github.com/keras-team/keras/blob/master/examples/addition_rnn.py
