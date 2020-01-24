[BOUAOUN Radhwen](https://www.linkedin.com/in/radhwen-bouaoun/) |
Dhiaeddine Alioui |
Oumaima Hmaied

# Balance EYE

1. **Introduction**
    Recognizing different kinds of vegetables and fruits is a re-current task in
    supermarkets, where consumers that attempt to buy fruits/vegetables must be
    able to point out not only the species of a particular fruit (i.e., ba-nana, apple,
    pear) but also its variety (i.e., Golden Delicious,Jonagold, Fuji), which will
    determine its price. In the past, several methods has been used in order to
    facilitate this task such as the use of barcodes or a small booklet with pictures
    and prices. These methods has its disadvantages as it is time consuming. In
    this project we tried to solve such problem by the use of a camera attached to
    the balance that identifies fruits and vegetables based on color, texture, and
    appearance cues.
2. **Problem Description**
    The problem of fruit/vegetable recognition is a recurrent problem that a
    consumer can face when he wants to buy fresh products. We personally faced
    such problem several times while in Carrefour and we also noticed that a lot
    of people, and more precisely elderly, spend a lot of time in front of the
    balance trying to identify fruits/vegetables types. Thus we thought about a
    camera placed on the balance and uses machine learning algorithms to
    identify the target product.
    It is a challenging problem as it deals with both different species of fruits and
    vegetables (e.g., apple, orange, potatoes) and many varieties of a single
    produced species (for example, Golden Delicious, Akane, Gala, and Fuji are
    different varieties of apples). Moreover the object can be inside a plastic bag
    that can add specular reflections and hue shifts.
    In our approach, ​given an image of fruits or vegetables of only one variety, in
    arbitrary position and number, the system must return a list of possible
    candidates of the form (species, variety).
    We based our approach on computer vision and image processing techniques
    and we tried to implement a Convolutional Neural Network


3. **Material and Method**<br/>
   a.  **Supermarket Produce data set**
       Datasets plays very important role in research as it is much
       expensive and harder to generate because companies don’t feel
       freely giving away their investment.
       And this was one of the major problems that we have faced, we
       thought that such dataset will be available for training and testing.
       However we couldn’t find any neither on Github nor on ALOI and
       Caltech that are used for general categorization to test the algorithm
       performance. We tried to build our proper data, but such huge amount
       of images will need months of on-site data collection in the local fruits
       and vegetables distribution center and also a professional camera.
       Because of the lack of resources and the limited time that we had for
       this project, we limited our work to the available dataset ​of fruits and
       vegetables spread across  74  labels​. We selected, from a large data set of
       120  labels, only the types of fruits/vegetable that are most common in
       carrefour.<br/>
    b.  **Convolutional Neural Networks**
       To solve the problem of automatic fruit/vegetable recognition, we
       used the deep Convolutional Neural Network that have proven very
       effective in areas such as image recognition and classification. Four
       main operations are performed in the Conv.Net as shown in the Figure
       below:
          - Convolution
          - Non Linearity (ReLU)
          - Pooling or Sub Sampling
          - Classification (Fully Connected Layer)


    Convolution in case of Conv.Net is used to extract features from
    the input image. Convolution preserves the spatial relation between
    pixels by learning image features using small squares of input
    image. The more number of filters we have, the more image features
    get extracted and the better the network becomes at recognizing
    patterns in unseen images.
    In our model we used 4 convolutions.
    ReLU: stand for rectified linear unit is a non-linear operation. The
    purpose of ReLU is to introduce to non-linearity in our Conv.Net
    because mostly Conv.Net has to learn non-linear real-world data. The
    biggest advantage of ReLU is non-saturation of its gradient, which
    greatly accelerates the convergence of stochastic gradient
    descent compared to the sigmoid / tanh functions.
    Pooling or Sub Sampling: ​The function of Pooling is to progressively
    reduce the spatial size of the input representation. In particular,
    pooling makes the input representations (feature dimension) smaller
    and more manageable. It also reduces the number of parameters and
    computations in the network, therefore, controlling overfitting.
    Another advantage of pooling that it makes the network invariant to
    small transformations, distortions and translations in the input image
    (a small distortion in input will not change the output of Pooling –
    since we take the maximum / average value in a local neighborhood).
    This is very powerful since we can detect objects in an image no matter
    where they are located.
    Classification​: The Fully Connected layer or classification is a
    traditional Multi Layer Perceptron that uses a softmax activation
    function in the output layer.
    The output from the convolutional and pooling layers represent
    high-level features of the input image. The purpose of the Fully
    Connected layer is to use these features for classifying the input image
    into various classes based on the training dataset.
    In general, the more convolution steps we have, the more complicated
    features our network will be able to learn and to recognize.


    Based on our research for image classification, we used  2  fully
    connected layers.

3.  **Experiments result & Analysis**
    We used Python 3.6 to implement our solution. We have developed this in
    keras.
    At the first step we used the whole dataset with  82110  images of fruits and
    vegetables and we could reach a test accuracy of 0.97 using RGB images
    Then we did some processing to the dataset, we converted the input image
    from RGB to HSV image + grey scale, the new input shape is ( 100 x 100 x 4 ).
    We obtained the following result :

The test accuracy obtained is less than the one we got using RGB images as
input.

4. **conclusions**
    During this project we tried to solve a real problem that we faced while
    shopping in the supermarket. But because of the lack of a complete and
    well-documented fruit and vegetables image data set, we couldn’t train and
    test our model to be implemented in the real world.


