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
If machine learning can be thought of minimizing the error, or in other words the loss function, by iteratively tweaking the parameters then we can now tackle how exactly machine learning is done. An algorithm is a function, and a neural network is a type of continuous function(given that the activation function is continuous). Furthermore, if the activation function is continuously differentiable, then the neural network is continuously differentiable. This just means that is is smooth and that we can define a "slope" at any given point on the function.

The loss function is then typically also continuously differentiable if the activation function is continuously differentiable. To shorten, we will replace continuously differentiable with $C^0$. I say typically here, because it depends ont he choice of loss function but for almost all serious or practical applications, this is true. For mroe information, refer to -----%Insert link to loss_function.md

The loss function is a function of a set of parameters and the input. We can think of this as a function from $\mathbb{R}^n\rightarrow\mathbb{R}$. Now imagine fixing the input variable, then we have a function that maps several parameters to one real number. If we limit the number of parameters to 2(Which cannot happen in general, this is for illustration purposes), we get a simple function of two variables, which looks like the attached image below.

-----%Insert image of loss function with x-axis being parameters.

Now of course, ordinarily we cannot see the complete picture as above. However, it turns out we do not need to. To find a local minimum, it turns out we don't need much information, we only need to know what direction to head in.