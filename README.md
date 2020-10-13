[//]: # (Image References)

[image1]: /images/seq2seq.png "seq2seq"
[image2]: /images/seq2seq_2.png "seq2seq2"
[image3]: /images/attention2.png "attention"

# Attention enhanced LSTM network to translate dates

## Project description
My own implementation of an LSTM encoder-decoder architecture **with** attention mechanism. I applied the architecture to translate dates from human readable format ("3 May 1979", "5 April 09") to machine readable format ("1979-05-03", "2009-04-05"), achieving accuracy of 80% on the testing set.

The project is based on the programming assignment of deeplearning.ai, course Sequence models, Neural machine translation with attention. It was implemented in Keras and I reimplemented it using TensorFlow 1.14.

## Implementation
[Jupyter Notebook](https://nbviewer.jupyter.org/github/vgkortsas/Attention_enhanced_LSTM/blob/master/Attention_mechanism_translate_dates.ipynb)

## Requirements
A full list of the requirements is given [here](https://github.com/vgkortsas/Attention_mechanism_translate_dates/blob/master/requirements.txt). The Python and deep learning library versions are:
- Python 3.5.5
- TensorFlow 1.14.0

## Some comments on the importance of the attention mechanism
### Encoder-decoder model ***without*** attention
The encoder-decoder models **without** attention have the following challenges:

* One single context vector, the final hidden state in the encoder RNN/LSTM, holding the meaning of the entire sentence/input sequence}. The challenge of this type of architectures is that the longer the input sequence length is, the more difficult it is for the final hidden state to capture the context. 

![seq2seq][image1]

* The information from the beginning of the input sequence is faded. The more updates are made to the same vector, the higher the chances are the earlier inputs and updates are lost.

<img src="https://github.com/vgkortsas/Attention_enhanced_LSTM/blob/master/images/seq2seq_2.png" width="350">

### Encoder-decoder model ***with*** attention
The challenge of one single context vector, i.e. the final hidden state in the encoder RNN, holding the meaning of the entire sentence/input sequence is addressed by replacing that **with an attention based context vector** generated for every decoder step.

![attention][image3]


## Reference
[deeplearning.ai Sequence models](https://www.coursera.org/learn/nlp-sequence-models)




