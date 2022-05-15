# CarRacer
This is a project that I worked on in my Machine Learning Fundamentals course to exemplify convolutional neural networks (CNN) and reinforcement learning. The goal was to create a model that can best drive the car simulation from [OpenAI](https://openai.com/). I only worked on the second cell in the notebook, everything else was provided to me for the assignment.

### Inputs/Outputs
The input to the model is a 96x96x3 image of the current state of the simulation. After the CNN is applied to the input image, a one-hot vector of length 7 indicating the model prediction of whether the car should do nothing, turn left, turn left and brake, turn right, turn right and brake, accelerate, or brake is outputted.

### Dataset Splits
The training dataset's retrieval has been omitted from the code; however, the training dataset consists of 11,132 examples of the states of the game and the correct actions to take. The data is randomly permuted and split into two subsets: 70% training and 30% validation. Models are trained on the training set, and the validation set is used for early stopping, learning rate reduction, hyperparameter optimization, and model selection. The simulation is used as a test set to test the performance of the model.

### Hyperparameter Optimization
To optimize the hyperparameters hand tuning was used. Layers were added and the hyperparameters were changed before running the simulation and the model with the best score in the simulation would be used. I changed the convolutional layer's filters to values between 10 and 30, kernel size to square sizes of (3, 3) to (10, 10), and activation function to one of the following activation functions: relu, selu, elu, tanh, or exponential. I changed the max pooling layer's pool size to square sizes of (2, 2) to (5, 5). Once the layers are optimized, other hyperparameters such as early stopping, learning rate reduction, and validation size were hand tuned as well.
