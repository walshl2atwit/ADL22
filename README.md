## 1. Introduction
> What is your MSE/MAE with linreg vs tuned network?
- The original MSE was 24.29 and the tuned network got it to 12.36.
- The original MAE was 3.32 and the tuned network got it to 1.93.
- I increased the depth and width of the network as well as the training time.
> What happens to your train and test results if you add 5 hidden layers with 128 neurons each?
- Adding 5 hidden layer with 128 neurons each brought the MSE down to 10.68.
## 2. Intro to convolution operations: padding
- The response layers are the filters that stack on top of each other.
- Given the filter shape (26,26,32) the three numbers represent height, width, and the number of filters
- Given 6x6 input and filter of (3,3) the response shape would be 4x4.
- Given (33,33,1) input and filter of (2,2) the response shape would be (32,32).
- Valid padding is when padding is disabled and same padding is when padding is done to make the output size equal to the input size. Given 6x6 input and filter of (3,3) the response shape for valid padding would be (4,4) and the response shape for same padding would be (6,6).
## 3. Convolution parameters: stride and pooling
- Max pooling is a way to donwsample by just taking the maximum of a window
- If you apply pooling of 2 (2,2 window with a strife of 2) to a (6,6) array the resulting size will be (3,3).
## 4. ConvNet Architectures, layers
- I: Input volume, F: filter, S: stride, P: padding, O: (I-F+2P)/S + 1. This gives the resulting size of the network's output.
- The output size if input = (100,100), kernel size = (2,2), stride of 1, and no pooling would be (99,99).
- If you had 24 such filters stacked (conv2_24) the resulting number of weights would be 470448.
- P = (S(O - 1) + F - I)/2
