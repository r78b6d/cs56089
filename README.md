java c
Homework #4
EE 541:  Fall 2024
Due:  Sunday, 13 October at 22:00. Submission instructions will follow separately on brightspace.
1. Backprop by HandConsider an MLP with three input nodes, two hidden layers, and three outputs.  The  hidden  layers use the ReLU activation function and the output layer users softmax. The weights and biases for this MLP are:

(a) Feedforward  Computation: Perform. the  feedforward  calculation  for  the  input  vector x = [ +1  − 1  + 1 ]T .  Fill in the following table.  Follow the notation used in the slides,  i.e., s(l)   is the linear activation, a(l) = h(s(l)), and a˙(l)  = h˙(s(l)).
l:
1
2
3

s(l) :




a(l) :




a˙(l) :



(not needed)
(b) Backpropagation Computation: Apply standard SGD backpropagation for the input assuming a multi-category cross-entropy loss function and one-hot labeled target: y = [ 0  0   1 ]T .  Follow the notation used in the slides, i.e., δ(l) = ▽s(l)C.  Enter the delta values in the table below and provide the updated weights and biases assuming a learning rate η = 0.5.
l:
1
2
3

δ(l) :




W(l):




b(l) :



2.  Logistic regressionThe MNIST dataset of handwritten digits is one of the earliest and most used datasets to benchmark machine learning classifiers.  Each datapoint contains 784 input features – the pixel values from a 28 × 28 image – and belongs to one of 10 output classes – represented by the numbers 0-9.
In this  problem you will  use  numpy  to  classify  input  images  using  a  logistic-regression.   Use  only Python standard library modules, numpy, and mathplotlib for this problem.
(a)  Logistic  “2” detector
In this part you will use the provided MNIST handwritten-digit data to build and train a logistic “2” detector:

A logistic cl代 写EE 541: Fall 2024 Homework #4Python
代做程序编程语言assifier takes learned weight vector w =  [w1 , w2 ,...wL]T   and the  unregularized offset bias b 纟 w0  to estimate a probability that an input vector x = [x1 , x2 ,..., xL]T  is  “2”:

Train a logistic classifier to find weights that minimize the binary log-loss (also called the binary cross entropy loss):
where the sum is over the N samples in the training set.  Train your  model until convergence according to some metric you choose.  Experiment with variations of ℓ1- and/or ℓ2-regularization to stabilize training and improve generalization.
Submit answers to the following.
i.  How  did you determine a  learning rate?  What values did you try?  What was your final value?
ii.  Describe the  method you used to establish model convergence.
iii.  What regularizers did you try? Specifically, how did each impact your model or improve its performance?
iv.  Plot  log-loss (i.e., learning curve) of the training set and test set on the same figure.  On a separate figure plot the accuracy against iteration number of your model on the training set and test set.  Plot each as a function of the iteration number.
v.  Clasify each input to the binary output  “digit  is  a  2” using a 0.5 threshold.  Compute the final loss and final accuracy for both your training set and test set.Submit your trained weights to Autolab. Save your weights and bias to an hdf5 file.  Use keys w and b for the weights and bias, respectively. w should be a length-784 numpy vector/array and b should be a numpy scalar.  Use the following as guidance:with  h5py.File(outFile,  'w')  as  hf:hf.create_dataset('w',  data  =  np.asarray(weights))hf.create_dataset('b',  data  =  np.asarray(bias))
Note:  you will not be scored on your models overall accuracy.  But a low-score may indicate errors in training or poor optimization.



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
