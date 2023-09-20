# Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set
Using LSTMs to Classify the 20 Newsgroups Data Set

# Dataset
Jeffrey Pennington, Richard Socher, and Christopher D. Manning. 2014. GloVe: Global Vectors for Word Representation. URL: https://nlp.stanford.edu/pubs/glove.pdf

# PART 1.
In this part, we used sklearn. fetch_20newsgroups dataset. We split data into two parts with a max length 20000, sequence length 30, batch size 32 and epochs 50 initially. Besides, we have a pre-trained word vector which is name Glove. We used glove.6b.100d.txt file.

### Model

We have 13,430,640 parameters in total. 15720 belongs to LSTM layer, and 620 belongs to dense (softmax) layer. Other parameters belong to embedding layer. Also, because of pre-trained model, we are going to freeze embedding layer. We used adam optimizer with a categorical crossentropy.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/fa69f0cf-687b-4035-a9e4-fd6db6255a7d)

### Epochs
After 50 epochs with a 32-batch size, our training loss reduced from 2.5882 to 1.333, accuracy increased from 0.1899 to 0.5813. Also, our test loss (val_loss) reduced from 2.3389 to 1.7630, test accuracy increased from 0.2606 to 0.4859. Also, the test score is 0.1.76. That’s a acceptable model since we do not have overfitting problem even if scores are low. The model can be improved.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/6d7a8608-38ad-43de-ab37-53a3a4d8d48f)

### Outputs of Initial Model

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/a6498d97-290a-4f87-88ed-4c471bb436c8)

# PART-2
## QUESTION 1
In this part, we used SimpleRNN with a same parameters to see the difference between LSTM and RNN. We have 13,418,850 parameters in total. 3930 belongs to SRNN layer, and 620 belongs to dense (softmax) layer. Other parameters belong to embedding layer.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/c143a66f-f54f-49c1-bced-7c77624e776f)

### Epochs
After 50 epochs with a 32-batch size, our training loss reduced from 2.3774 to 2.3267, accuracy increased from 0.2695 to 0.2884. Also, our test loss (val_loss) reduced from 2.3924 to 2.4197, test accuracy increased from 0.2556 to 0.2546. Also, the test score is 2.419 That’s not a good model obviously when we compared to LSTM model.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/638d3b53-593e-46b2-904b-147c3a48a218)

# QUESTION 2
In this part, we used LSTM without the pretrained word vectors (randomly initialize the weights and have them be learned during the training process) with same parameters. We have 13,430,640 parameters in total. 16,340 belongs to LSTM layer, and 620 belongs to dense (softmax) layer. Other parameters belong to embedding layer.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/a8b6a696-f399-44e6-b8b0-678834d94fd4)

### Epochs
After 50 epochs with a 32-batch size, our training loss reduced from 2.8359 to 1.9216, accuracy increased from 0.1552 to 0.4182. Also, our test loss (val_loss) reduced from 2.7175 to 2.4480, test accuracy increased from 0.1895 to 0.3230. Also, the test score is 2.447 That’s not a good model obviously when we compared to first model. So, using pre-trained model to be increased accuracy.

### Outputs of Model_3

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/30121537-57ae-405a-9bd9-96845e89b799)


# QUESTION 3
In this part, we are going to chance the parameters of first model such as sequence length and dimension.

## SEQ_LENGTH = 50
We have 13,430,640 parameters in total. 16,340 belongs to LSTM layer, and 620 belongs to dense (softmax) layer. Other parameters belong to embedding layer.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/df18cbb9-784a-48c1-9ee1-4b6394bfd26f)

### Epochs
After 50 epochs with a 32-batch size, our training loss reduced from 2.5421 to 1.0122, accuracy increased from 0.1909 to 0.6802. Also, our test loss (val_loss) reduced from 2.2273 to 1.1464, test accuracy increased from 0.2723 to 0.5826. Also, the test score is 1.416. That’s pretty good model obviously when we compared to first LSTM model.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/008abeea-4b20-4939-982c-34c8b9664003)

### Outputs of Model_4
![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/6e9e6659-921e-40fd-84ba-3edd83585145)



## SEQ_LENGTH = 100
We have same parameters.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/bcd49b49-6af3-4f3d-9a33-631618a528e6)


### Epochs
After 50 epochs with a 32-batch size, our training loss reduced from 2.4507 to 0.6649, accuracy increased from 0.2144 to 0.7838. Also, our test loss (val_loss) reduced from 1.9620 to 1.1260, test accuracy increased from 0.3440 to 0.6730. Also, the test score is 1.125. That’s pretty good model obviously when we compared to model_4. So, for now when we increased the seq_length, the model fitting good.
![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/aaca0bd5-7d8c-4fc4-8fd4-662006409a6d)


### Outputs of Model_5
![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/a7d31d5f-8f5c-4342-a476-eb89f7d0995a)


## DIMENSION = 200
In this part, we chance the dimension shape from 100 to 200 with a sequence length 30. We have 26,856,940 parameters in total. 28,340 belongs to LSTM layer, and 620 belongs to dense (softmax) layer. Other parameters belong to embedding layer

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/5190d784-1f7a-46ae-90a1-4ad5f57f53af)

### Epochs
After 50 epochs with a 32-batch size, our training loss reduced from 2.5639 to 1.3183, accuracy increased from 0.1933 to 0.5883. Also, our test loss (val_loss) reduced from 2.3074 to 1.7763, test accuracy increased from 0.2658 to 0.4819. Also, the test score is 1.77. That’s not a good model obviously when we compared to last model. So, when we increased the dimension, the model not fitting good.

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/0bb890d1-e939-4d20-9cb4-bebee2501b46)

### Outputs of Model_6

![image](https://github.com/onlinEngineer/Using-LSTMs-to-Classify-the-20-Newsgroups-Data-Set/assets/70773825/a38cdd34-ff4d-46e0-95c7-9fcf64499a78)

