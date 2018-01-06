Max pooling is a sample-based discretization process. The objective is to down-sample an input representation (image, hidden-layer output matrix, etc.), reducing its dimensionality and allowing for assumptions to be made about features contained in the sub-regions binned.
This is done to in part to help over-fitting by providing an abstracted form of the representation. As well, it reduces the computational cost by reducing the number of parameters to learn and provides basic translation invariance to the internal representation.

*Dropout* is a regularization technique for reducing overfitting in neural networks by preventing complex co-adaptations on training data.
It is a very efficient way of performing model averaging with neural networks.
The term "dropout" refers to dropping out units (both hidden and visible) in a neural network.


RMSprop

rprop: This combines the idea of only using the sign of the gradient with the idea of adapting the step size separately for each weight.
– Increase the step size for a weight multiplicatively (e.g. times 1.2). if the signs of its last two gradients agree.
– Otherwise decrease the step size multiplicatively (e.g. times 0.5).
– Limit the step sizes to be less than 50 and more than a millionth (Mike Shuster’s advice).

rprop doesn't work with mini batches - it averages the gradients over successive mini-­batches.
The problem with mini-­‐batch rprop is that we divide by a different number for each mini-­‐batch. So why not force the number we divide by to be very similar for adjacent mini-­‐batches?


We introduce Adam, an algorithm for first-order gradient-based optimization of stochastic objective functions, based on adaptive estimates of lower-order moments. The method is straightforward to implement, is computationally efficient, has little memory requirements, is invariant to diagonal rescaling of the gradients, and is well suited for problems that are large in terms of data and/or parameters. The method is also appropriate for non-stationary objectives and problems with very noisy and/or sparse gradients. The hyper-parameters have intuitive interpretations and typically require little tuning. Some connections to related algorithms, on which Adam was inspired, are discussed. We also analyze the theoretical convergence properties of the algorithm and provide a regret bound on the convergence rate that is comparable to the best known results under the online convex optimization framework. Empirical results demonstrate that Adam works well in practice and compares favorably to other stochastic optimization methods. Finally, we discuss AdaMax, a variant of Adam based on the infinity norm.

one epoch = one forward pass and one backward pass of all the training examples
batch size = the number of training examples in one forward/backward pass. The higher the batch size, the more memory space you'll need.
number of iterations = number of passes, each pass using [batch size] number of examples. To be clear, one pass = one forward pass + one backward pass (we do not count the forward pass and backward pass as two different passes).
Example: if you have 1000 training examples, and your batch size is 500, then it will take 2 iterations to complete 1 epoch.
