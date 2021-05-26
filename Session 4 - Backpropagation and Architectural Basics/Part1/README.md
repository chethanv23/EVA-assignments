
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

with our fixed i1 and i2 and random weights we calculated all the hidden layers neurons.


and calculate error using MSE.

![image](https://user-images.githubusercontent.com/65776820/119711418-2a039780-be7d-11eb-992e-05e1b2a4e46d.png)

Back-Propagation:
Back-propagation is the essence of neural net training. It is the practice of fine-tuning the weights of a neural net based on the error rate (i.e. loss) obtained in the previous epoch (i.e. iteration). Proper tuning of the weights ensures lower error rates, making the model reliable by increasing its generalization.

Back-propagation is all about feeding this loss backwards in such a way that we can fine-tune the weights based on which. The optimization function (Gradient Descent in our example) will help us find the weights that will — hopefully — yield a smaller loss in the next iteration

we need to find the loss at every unit/node in the neural net because we need to find out which node is responsible for most of the loss in every layer, so that we can penalize it in a sense by giving it a smaller weight value and thus lessening the total loss of the model.

we are finding partial derivetive of Etotal with respect to each weights.

∂e_total/∂w5 = ∂(E1+E2)/∂W5

since E2 hs no effect on w5

∂e_total/∂w5 = ∂(E1)/∂W5

∂E_total/∂w5 = ∂(E1)/∂W5=∂E1/∂a_o1*∂a_o1/∂o1*∂o1/∂w5

that can be re written as 

∂e_total/∂w5= (a_o1-t1)*a_o1 *(1-a_o1)*a_h1

simillarly,

∂e_total/∂w6= (a_o1-t1)*a_o1 *(1-a_o1)*a_h2

∂e_total/∂w7= (a_o2-t2)*a_o2 *(1-a_o2)*a_h1

∂e_total/∂w8= (a_o2-t2)*a_o2 *(1-a_o2)*a_h2

so we can write Etatal with respect to a_h1 and a_h2

∂E_total/∂a_h1 =  (a_o1-t1)*a_o1 *(1-a_o1)*w5 +(a_o2-t1)*a_o2 *(1-a_o2)*W7

∂E_total/∂a_h2 =  (a_o1-t1)*a_o1 *(1-a_o1)*w6 +(a_o2-t1)*a_o2 *(1-a_o2)*W8

and now 

∂E_total/∂w1 = ∂E_total/∂a_h1*∂a_h1/∂h1*∂h1/∂w1

∂E_total/∂w2 = ∂E_total/∂a_h1*∂a_h1/∂h1*∂h1/∂w1

∂E_total/∂w3 = ∂E_total/∂a_h2 *∂a_h2/∂h2*∂h2/∂w3

∂E_total/∂w4 = ∂E_total/∂a_h2 *∂a_h2/∂h2*∂h2/∂w4

above equations can be expanded as 

∂E_total/∂w1 = ((a_o1-t1)*a_o1 *(1-a_o1)*w5 +(a_o2-t2)*a_o2 *(1-a_o2)*W7)*a_h1*(1-a_h1)*i1

∂E_total/∂w2 = ((a_o1-t1)*a_o1 *(1-a_o1)*w5 +(a_o2-t2)*a_o2 *(1-a_o2)*W7)*a_h1*(1-a_h1)*i2

∂E_total/∂w3 = ((a_o1-t1)*a_o1 *(1-a_o1)*w6 +(a_o2-t2)*a_o2 *(1-a_o2)*W8) *∂a_h2*(1-∂a_h2)*i1)

∂E_total/∂w4 = ((a_o1-t1)*a_o1 *(1-a_o1)*w6 +(a_o2-t2)*a_o2 *(1-a_o2)*W8) *∂a_h2*(1-∂a_h2)*i2)

now we have back propagated from error to each weights.

![image](https://user-images.githubusercontent.com/65776820/119713913-de9eb880-be7f-11eb-8089-8fb75b72eb48.png)


once we find our partial derivatives. we can update the weights using set learning rate.

Learning rate is a hyper-parameter that controls how much we are adjusting the weights of our network with respect the loss gradient

new_weight = existing_weight — learning_rate * gradient

![image](https://user-images.githubusercontent.com/65776820/119716932-4f939f80-be83-11eb-9a33-fbd9f8b7a1ab.png)


![image](https://user-images.githubusercontent.com/65776820/119717120-88337900-be83-11eb-9783-1325ec370552.png)

































