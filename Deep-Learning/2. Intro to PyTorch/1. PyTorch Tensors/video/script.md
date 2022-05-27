- torch tensors are the main datatype used all over pytorch
- they are much like numpy arrays, but have much more functionality
<!-- to allow for things like automatic differentiation -->

<!-- TODO move this section below to a lesson on "what is a tensor?" -->

- the word tensor is a generalisation of a matrix, with more dimensions than just height and width
- a matrix would be a 2d tensor, and a vector would be a 1-d tensor
- but the word tensor can refer to a block of numbers with any number of dimensions
- and yes that means more than just 3 dimensions, which is hard to visualise
<!-- EXAMPLE -->
- but it's easy to understand intuitively with this following example
- a black and white image can be represented as a matrix, where each value represents the brightness of a pixel at a particular height and width - those are the two dimensions
- but a color image needs to represent the brightness of the primary colors too
- so it would have one matrix for the red intensity, another for the green intensity, and another for the blue intensity all stacked on top of each other
- that gives it another dimension, which we call the color channel dimension, so now it's 3 dimensional tensor
- but now imagine a color video
- to represent it, we need a color image for each different frame of the video
- so you might try to picture a stack of those image tensors
- the position of each value in this data structure is specified by 4 numbers: its vertical position, its horizontal position, what color channel it appears in, and at what time it appears
- that makes it a 4-dimensional tensor
- to take it even further, imagine not just one video, but a dataset of videos, all stacked on top of each other
- that's another dimension!
- but all of those, can be represented as tensors
<!-- TODO create animation for visualising the above explanation -->

<!-- CREATING TENSORS -->

- we can create tensors in MANY different ways

_Switch to screen capture of python file_

- in fact, almost every numerical value generated by any method in pytorch will return you a torch tensor
- but the most basic way to create a torch tensor is to cast another data type into one using the `torch.tensor` function
- you can easily cast ints, floats or numpy arrays into torch tensors like this

\_Show casting an int, a float, and a numpy array into a torch tensor

- another really common way to create tensors is by initialising them randomly
- there are loads of torch methods you can use to do that
- one of them is rand, which creates a tensor with the size you specify as the first argument

_Create 3 x 4 matrix_

- this is a 3 x 4 matrix
- you can print a tensor's size by using its `.shape` attribute
- and you can print the datatype by using the `.dtype` attribute
- the default is a 32 bit floating point number

- i could just as easily create a 4 dimensional tensor

_Create 4D tensor_

- other common ways to initialise tensors exist too
- like creating a tensor full of zeros

_Show torch.zeros_

- or a tensor full of ones

_Show torch.ones_

- as you'd expect, you can do all of the usual mathematical operations on tensors
- they behave in a very similar way to numpy arrays

_add an integer to a tensor_

- notice here that any value computed from a tensor will also be a tensor

_print type(result)_

- you can use torch to do other common operations on tensors too

_Show matmul_

_Show sum_

- that's a good start
- but that's just the basics