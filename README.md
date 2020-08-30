## dl.py
dl is a small library I made to understand how neural networks and gradient descent optimizers work. I have benchmarked momentum, Adam and RMSprop on MNIST and used dl for simple problems like modelling logic gates. dl can also be used to implement reinforcement learning algorithms like REINFORCE or DQL for simple games in OpenAI's gym environment like CartPole-v0, Pong-v0, Pacman-v0 etc or gridworld games. dl uses the standard backpropagation algorithm (shown below) for dense networks. Libraries like PyTorch and Tensorflow on the other hand, use reverse mode differentiation. All operations done on variables are kept track of (represented as a DAG), and calling the backward() (gradient(loss, parameters) in TensorFlow) method on the output scalar computes the gradient of that scalar w.r.t all the variables.

![](backpropagation.png)

![](optims.gif)

## GATES.ipynb - modelling logic gates using NNs
A classic problem in machine learning is using a neural networks to model XOR. XOR is not linearly separable - and neural networks are good at approximating non-linearly separable data. They are approximations becauase it's very hard to model with 100% accuracy. In the plots, we can clearly see boundaries (black->yellow) where the output jumps from 1 to 0. Logic gates have binary inputs but neural networks can have real inputs. So we can not only input 0 and 1, but all pairs of numbers in the range [0, 1] (with finite step size - here, it's 0.01). The contour plots of the corresponding outputs are shown below. Black regions and beyond => 1 and yellow regions and beyond => 0. For XOR - coordinates (0, 0) => 0, (1, 0) => 1, (0, 1) => 1 and (1, 1) => 0 as it should be.

![](gatecontours.png)

## GANs
Generative Adverserial Networks belong to a class of machine learning models called generative models. Generative models are used to learn data distributions using unsupervised learning. GANs were introduced in 2014 by Goodfellow et al. They can be used to create novel data. For example, given images of digits, GANs can be used to create different variations of digits. The cool thing about GANs is that the generator in a GAN takes in noise as input - which is why it's able to create novel data! There are many AWESOME uses for GANs. They can be used to create "filler" data to balance data sets with inequal ratios of training examples. They can be used to [make art](https://heartbeat.fritz.ai/artificial-art-how-gans-are-making-machines-creative-b99105627198), [make life-like human faces](https://www.whichfaceisreal.com/), [make life-like human figures and models](https://rosebud.ai/) and even [learn the rules of a video game and recreate it](https://blogs.nvidia.com/blog/2020/05/22/gamegan-research-pacman-anniversary/) by using pixel information alone! 

![](gan.jpeg)

![](gan.png)
