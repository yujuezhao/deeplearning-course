### Special applications：Face recognition & Neural style transfer

1. Face verification requires comparing a new picture against one person's
   face, whereas face recognition requires comparing a new picture against
   K person's faces.

   > True

2. Why do we learn a function d(img1,img2) for face verification? (Select all that apply.)

   > * This allows us to learn to recognize a new person given just a single image of that person.
   >
   > * We need to solve a one-shot learning problem.

3. In order to train the parameters of a face recognition system, it would be reasonable to use a training set comprising 100,000 pictures of 100,000 different persons.

   > False

4. Which of the following is a correct definition of the triplet loss? Consider that α>0. (We encourage you to figure out the answer from first principles, rather than just refer to the lecture.)

   > ==$\max \left(\|f(A)-f(P)\|^{2}-\|f(A)-f(N)\|^{2}+\alpha, 0\right)$==

5. Consider the following Siamese network architecture: 

   <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week4/images/1.PNG' width='80%' height='80%'>

   The upper and lower neural networks have different input images, but have exactly the same parameters.

   > True

6. You train a ConvNet on a dataset with 100 different classes. You wonder if you can find a hidden unit which responds strongly to pictures of cats. (I.e., a neuron so that, of all the input/training images that strongly activate that neuron, the majority are cat pictures.) You are more likely to find this unit in layer 4 of the network than in layer 1.

   > True

7. Neural style transfer is trained as a supervised learning task in which the goal is to input ==two images (x)==, and train a network to output a new, ==synthesized== image (y).

   > False

8. In the deeper layers of a ConvNet, each channel corresponds to a different feature detector. The style matrix G[l] measures the degree to which the activations of different feature detectors in layer l vary (or correlate) together with each other.

   > true

9. In neural style transfer, what is updated in each iteration of the optimization algorithm?

   > - [x] ==The pixel values of the generated image G==
   > - [ ] The neural network parameters

10. You are working with 3D data. You are building a network layer whose input volume has size 32x32x32x16 (this volume has 16 channels), and applies convolutions with 32 filters of dimension 3x3x3 (no padding, stride 1). What is the resulting output volume?

    > $30 \times 30 \times 30 \times \underbrace{32}_{\# filter}$

