# Machine Poet
## Mechanism
1. Language Model
1. Word Embedding
1. LSTM NN
1. Sampling
## Model
1. [x] Data Input
    1. Textline Reader
        1. token for `\n`
    1. Poems
1. Word Embedding
    1. Model based on [Tensorflow-hub](https://www.tensorflow.org/hub)
    1. Tansfer Learning based on text materials from poet
1. Model
    1. Tensorflow/Keras
    1. Structure
        1. Input Function
        1. LSTM layer
        1. Dropout
        1. LSTM
        1. Dropout
        1. Softmax
## Data Format
1. Sonnets
    1. `xxxnewlinexxx` means new line
    1. Every line in the txt file is one sonnet
1. Poems
## Reference
1. https://www.tensorflow.org/tutorials/text_classification_with_tf_hub