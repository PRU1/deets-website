## Disclaimer

This is more of a tangent on the universal approximation theorem, which proves that neural networks(With a few asterisks attached) can theoretically approximate processes(with a few asterisks attached). The universal approximation theorem that we will discuss here is the one given by Cybenko in "Approximation by Superpositions of a Sigmoidal Function" in 1989.

## Formal definitions

The universal approximation theorem examines theoretical neural networks with only one single hidden layer. The inputs are assumed to be a vector from $\mathbb{R}^n$, as well as the weights and biases. The activation function used here is only restricted to sigmoidal activation functions which are functions of a single variable that approach -1 as the input approaches $-\infty$ and +1 as the input approaches $+\infty$. 
