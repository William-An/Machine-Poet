# Machine Poet
## Mechanism
1. Language Model
1. Word Embedding
1. LSTM NN
1. Sampling
## Model
1. Data Input
    1. [x]Textline Reader (TF)
        1. Every poem is in one line
        1. Special Tokens
            1. `xxxnewlinexxx`
            1. `xxxstartxxx`
            1. `xxxendxxx`
            1. `xxxendofstanzaxxx`
    1. [x]Words2id
        1. Dictionary
            1. https://www.tensorflow.org/api_docs/python/tf/contrib/lookup
        1. Yes Punctuation
            1. Preprocess
                1. `re.sub`
                1. Insert ` ` around punctuations?
1. Word Embedding (Tensorflow)
    1. Model based on [Tensorflow-hub](https://www.tensorflow.org/hub)
    1. Tansfer Learning based on text materials from poet
1. Model (Tensorflow, LSTMCell)
    1. ~~Structure
        1. [x]Input Function
            1. Word
        1. Embedding
            1. Lookup in the dictionary
            1. Embed using the existing model from Tensorflow Hub
        1. LSTM layer
        1. Dropout
        1. LSTM
        1. Dropout
        1. Dense
            1. To Size of the dictionary
        1. Softmax
            1. Output Shape shall be the size of dictionary
    1. Variables initialization
    1. Train (Cell based)
        1. Loss
        1. For-loop as Steps
            1. Initialize States for LSTM Cell
            1. Initialize input for LSTM Cell
            1. For-loop for time step
                1. Input
                1. State
                1. LSTM cell
                1. Dense
                1. Calculate State
                1. Calculate y_hat as next input
                1. Calculate Loss
    1. Sampling
        1. Initialize States for LSTM Cell
        1. Initialize input for LSTM Cell 
        1. Run once and randomly select words as y_0
        1. Calculate state
        1. While-loop until `xxxendxxx` token is output
            1. Input
            1. State
            1. LSTM cell
            1. Dense
            1. Calculate State
            1. Calculate y_hat as next input
            1. Print y_hat
1. Model (TF Estimator)
    1. Data input label will be series of vectors as indices from the dictionary
    1. Sentence go through text_feature_columns from tf hub
    1. The embedding vectors thus enter LSTM layers 
    1. The output should then be compared with label from input_fn
## Data Format
1. Sonnets
    1. `xxxnewlinexxx` means new line
    1. Every line in the txt file is one sonnet
1. Poems
## Reference
1. https://www.tensorflow.org/tutorials/text_classification_with_tf_hub