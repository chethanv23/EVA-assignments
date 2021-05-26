
#FEED FORWARD NETWORKS and BACK PRAPAGATION

![image](https://user-images.githubusercontent.com/65776820/119707157-74cee080-be78-11eb-9f94-1f82938d6c83.png)


The first layer taking in inputs and the last layer producing the output. The middle layers have no connections with the external world and hence are called hidden layers. Each neuron or perceptron in one layer is connected to every perceptron on the next layer. Hence information is constantly "fed forward" from one layer to the next

Each of the circles is actually a neuron, but each line is the weight we are training and are of importance to us. Those circles are "temporary" values that will be stored. Once we train the model, lines are what all matter!

These lines are denoted by w's where i and j are the neurons it is connecting together.

Here i1 and i2 are the Input neurons and h1 is neuron created from wights w1 and w2 and Input layers i1 and i2.

ACTIVATION FUNCTION:

Activation function defines the output of input or set of inputs or in other terms defines node of the output of node that is given in inputs. They basically decide to deactivate neurons or activate them to get the desired output. It also performs a nonlinear transformation on the input to get better results on a complex neural network.

Without activation function, weight and bias would only have a linear transformation, or neural network is just a linear regression model

The most famous activation functions are given below, 

 

Binary step

Linear

ReLU

LeakyReLU

Sigmoid

Tanh

Softmax

In this study , we are using Sigmoid Activation function

Sigmoid Activation Function:
The sigmoid activation function is used mostly as it does its task with great efficiency, it basically is a probabilistic approach towards decision making and ranges in between 0 to 1.

![image](https://user-images.githubusercontent.com/65776820/119710914-8dd99080-be7c-11eb-88c4-0e72a2f62674.png)


in our example:

a_h1 activated layer which is sigmoid of h1.

 singmoid fumction  = o(x) = 1/1+e^(-x)

h1 = w1*i1+w2*i2

h2 = w3*i1+w4*i4

a_h1 = σ(h1)=1/(1+exp(-h1))

a_h2 = σ(h2)=1/(1+exp(-h2))

o1 = w5*ah1+w6*a_h2

o1 = w7*ah1+w8*a_h2

a_o1 = σ(o1) =1/(1+exp(-o1))

a_o1 = σ(o1) =1/(1+exp(-ho2))

Etotal is the total combined errors E1 and E2

THE error we considered here is MSE - Mean Squared error.

Etotal = E1+E2

E1 = 0.5(target1 - a_o1)^2

E1 = 0.5(target2- a_o1)^2

with our fixed i1 and i2 and random weights we calculate all the hidden layers neurons.

![image](https://user-images.githubusercontent.com/65776820/119711418-2a039780-be7d-11eb-992e-05e1b2a4e46d.png)











