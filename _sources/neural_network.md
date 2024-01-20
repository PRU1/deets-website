## What is an Artificial Neural network

An Artificial Neural Network is a network of nodes. This is designed to mirror brains, and in this analogy nodes are akin to neurons. Nodes are connected to each other and can send "signals". Nodes receive, process, and then send out those signals. A neural network itself simply takes and input and provides an output. At the fundamental level it is a type of algorithm and is not intrinsically linked to maching learning. How neural entworks process the signals received are dependent on a few parameters in the nodes, machine learning is the process of iteratively chaging those parameters to create a more accurate neural network. It should be noted the machine learning has a more broad usage than only neural networks.

### How is this implemeneted?

Nodes are split into several layers in a neural network. 

![neural_network]("_build/images/neural_network.png")

The input layer, then the hidden layers, and finally the output layer. The input layer is where the data starts. Every input node is a number, representing a trait of the data. 

For example in a neural network for handwriting recognition, you could upload a picture, and the input nodes would take the brightness value of each pixel in some order.

The hidden layers do the actual processing, and the output layer shows the result of all the processing. However, before the data reaches any hidden node there is another adjustment made. Between any two connected nodes, there is a *weight* attached. This weight is often a number between 0 and 1. The value of the input node is then multiplied by this weight before being sent to the next node. Remember that this weight value is specific to the node connection, and so can differ even if the same input value is being sent to a different node. 

![neural_network](https://github.com/PRU1/deets-website/blob/main/_build/images/neural_network_weight.png)

The hidden nodes, which are simply nodes in the hidden layer(s), apply a transformation to the received input(with the weight multipled). The first transformation applied is the addition of a parameter called the *bias*. The bias is specific to nodes, and is a way to assign a sort of importance to a node. For exmaple if a node does not matter, then a hugely negative bias could be assigned. Now imagine we have a neural network with one hidden layer. Let's say we had an input of 3 from node A, a weight of 0.5 applied, and then a bias of 0.2. Then we would have $0.5\cdot 3 +0.2$. 

![neural_network](https://github.com/PRU1/deets-website/blob/main/_build/images/neural_network_bias.png)

Now, the hidden node repeats this process for every other connected input node. For example, node B could have a weight of 0.8, and an input value of 2 and so the calculated value would be $0.8\cdot 2+0.2$. The values calculated for every single connected input nodes are then summed and a final transformation is applied onto this sum. The final transformation that is applied is something called the activation function. **Note:** $\Sigma$ means sum, $b$ is bias, $x$ is input, $w$ is weight, $f$ is activation function. 

![neural_network](https://github.com/PRU1/deets-website/blob/main/_build/images/neural_network_activation_function.jpg)

The activation function is a way to sort of assign a relative importance to all the nodes. It helps filter any unimportant details, and helps provide a scale to all the values calculated. For example, imagine a metal is heated to 4000K compared to 5000K, the activation function in this case recognizes that those are both incredibly hot and the 1000K difference between them doesn't really matter, and would provide both of them with similar activation values. 

Here is an example of a common activation function called the sigmoid.
![sigmoid](https://github.com/PRU1/deets-website/blob/main/_build/images/sigmoid.png)

#### Summary
- A neural network is a form of algorithm
- Machine learning is the process of improving an algorithm
- A neural network is not a type of machine learning
- A neural network is made of layers of nodes
- Nodes are connected between each successive layer
- Each layer has a specific job, input, output, and hidden(processing)
- Inputs are numbers
- Between any two nodes in consecutive layers, there is a connection with an attached *weight* between 0 and 1
- The weight is a measure of the importance of an input to the next node
- The bias is added in the hidden nodes and is specific to every hidden node
- The bias is added to the weight scaled input
- The bias is a measure of the importance of a node to the neural network as a whole
- After the inputs are weighted and bias added, they are summed and an activation function is applied
- An activation function is an importance curve
- The activation function filters important details and scales the calculated values

## Uses of Neural Networks

