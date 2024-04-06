# What are Neural Networks
Neural Networks are a type of algorithm that simulates how netowrks of neurons work. Neural Networks are comprised of multiple "neurons" or "nodes" that are placed in layers. Each layer is connected to adjacent layers.

-----%Insert image here of neural network

Each connection of a neural network has a parameter attached, which is called a weight. The weight is typically a number between 0 and 1. Each node also has a parameter attached called the bias. The bias can be thought of as a threshold for when the neuron activation becomes significant enough. Sort of like a "you must be this tall to ride" for the neural signal. The purpose of the weight tells us how important any given connection is. For example, a useless connection will have a weight of 0.

-----%Insert image here of weights and biases

Each signal in a node must also be run through something called an activation function, an activation function can be thought of as an importance assigning function. What it does in essence is it assigns a relative importance to any given value of a signal. For example, it does not really matter if an object is 5000 Celsius or 5500 Celsius, even though it is a very large gap. The activation function here would assign a similar importance value to 5000 and 5500, whereas it would give wildly different ones for 0 and 500.

------%Insert image of sigmoid activation function

The function displahed above is an example of an activation function, we can see how it flattens as the value gets smaller and smaller or larger and larger. This specific function is known as the sigmoid activation function

For the specifics of neural networks, refer to ------%Insert link to neural_network.md

You may be wondering why neural networks are sufficient for some given problem. In other words, hwo do we know that a neural network exists that can solve the problem given. For more information about this, refer to -----%Insert link to proof_of_existence.md

# What is Machine Learning: Loss Functions
We can think of a neural network as a function that takes an input and a set of parameters(the weights and biases) and gives an output. Let's consider the case of a classification problem. A classification problem is one where each object has a class and the algorithm tries to predict the class based off the object. One example of this is the prototypical handwriting recognition problem. A written letter is fed into the function, and the function tries to guess which letter it is.

Machine learning is the process of iteratively improving the accuracy of a an algorithm by adjusting the parameters. One way that this can be thought of is as a minimiation problem. The quantity being minimized here is the inaccuracy of the algorithm. Measuring the inaccuracy can be done through the loss function. The loss function quantitizes how inaccurate the algorithm is. In general for classification problems, not only including neural entworks, the goal of a classification problem is to find an algorithm that can establish an accurate decision boundary.

-----%Insert image of decision boundary

Machine learning is one way that this is done. A loss function can for example measure on average how "incorrect" a given classification is. For mroe about loss functions, refer to -----%Insert link to loss_function.md

In summary, machine learning is the process of improving an algorithm to do a specific problem. We can think of an algorithm as a tool to solve a given problem. Machine learning is a way to improve this tool, and a neural network is a type of tool.

# What is Machine Learning: The Minimization Problem
We can think of machine learning as minimizing the loss function, or in other words the loss function, by iteratively tweaking the parameters to minimize the loss. A neural network is still fundamentally a function, and if the activation function is "smooth", then the network itself when viewed as a function is also smooth. 

Below here, we have the same idea but in more technical terms. 

The loss function is continuously differentiable if the activation function is continuously differentiable. This is because a neural network is generally written as a linear combination of the activation function, the weights, and biases. Since continuous differentiability is conserved under addition and multiplication, the neural network is continuously differentiable if the activation function is. For more information, refer to -----%Insert link to loss_function.md

The loss function is a function of a set of parameters and the input. We can think of this as a function from $\mathbb{R}^n\rightarrow\mathbb{R}$. Now imagine fixing the input variable, then we have a function that maps several parameters to one real number. If we limit the number of parameters to 2(Which cannot happen in general, this is for illustration purposes), we get a simple function of two variables, which looks like the attached image below.

-----%Insert image of loss function with x-axis being parameters.

Now of course, ordinarily we cannot see the complete picture as above. However, it turns out we do not need to. To find a local minimum, we don't need much information, we only need to know what direction to head in. This is the essence of gradient descent. A common analogy is that the loss function is like a mountainous terrain, minimizing the loss function would be finding a valley in this landscape. Gradient descent essentially says that if you walk in the direction of steepest descent, you will find this valley, thus minimizing the loss function. Mathematically, this requires something called "the gradient". For the sake of efficiency, there is also a certain step size that must be chosen, since recalculation of the gradient can take some time.

-----%Insert image of gradient descent

The way that the gradient is calculated for any given input, output, loss function, activation functions, weights, biases, etc. relies on something called backpropogration. Backpropogation relies on the fact that the "chain rule" for multivariable function relies on the compuation of individual derivatives of the components of the function. In other words, it relies on the derivative of the composition of functions to be the product of the derivatives of the individual component functions. In simpler terms, it relies on the derivative of a composition of functions' ability to be broken up and computed individually. Backpropogation is an efficient way to compute the gradient, avoiding duplicate calculations. 

# Practical Considerations
What has been described here is the generic example of using gradient descent and backpropogation to train a feedforward neural network. However, there are usually many other considerations to a problem that may change the algorithms used, the activation function used, the step size, loss function, method of training, type of algorithm trained, etc. for example often the sigmoid activation function is not used, instead RELU and GELU are used, which are often more efficient, GELU being the smooth form of RELU. Although it may seem like a good idea to reduce the step size to as low as possible to ensure accuracy, the training time needs to be considered. On the other end of the spectrum, increasing the step size is not necessarily a good idea either, as a phenomenom called overtaining can happen, which can be thought of as accidentally stepping over small valleys in the terrain analogy. 

-----%Insert image of overtraining

Another consideration that must be made is the width of each layer and the number of layers used. Increasing the width vs increasing the number of layers have different effects on the training process, speed, and etc. Nodes cannot be easily added or removed either without causing significant loss of progress after training has begun, so the exact layer widths and number of layers are also a consideration that must be made. With less nodes, the network might struggle to accurately model the problem and data, if possible at all(see Theoretical Considerations). However, with too many nodes, the network might take too long to train. 

# Theoretical Considerations
How can we ensure that for any given problem we have, a feedforward neural network can even be trained for it?