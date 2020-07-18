# Background and basic Machine Learning Intutions

### Question 1. What are Channels and Kernels (according to EVA)

**Channels:**
In terms of basic/simple terms,
1. It is a container/folder of specific information/feature ie., we can add information which is contextualy similar into this particular channel.
2. In terms of color each individual channel captures just the intensity of a particular color.
3. The channel can be made by RGB, CMYK, Lab etc.,
4. The channel can have 'n' number of similar feature.

**Kernels**
1. A Kernel is a filter, which is used to extract the features.
2. And most of the time Kernel size of `3 X 3` matrix is used to extract the features from the image.
3. Output of Kernel: The kernel/feature extractor slides on the image and comes up with the new channel.

### Question 2. Why should we (nearly) always use 3x3 kernels?

1. Reason 1: If we are going for higher size kernel like `5 X 5` then we get higher number of weights of 25, and lower layers. Because of this it becomes computationally expensive. And due to the lower layers its learns simpler and non linear features. But instead of `5 X5` if we go with 2 `3 X 3` which is `3 X 3 + 3 X 3` we can get lower number of weights with more layers, because of which it is computationally efficient and learns more comples non linear features.
2. Reason 2: If we are using `1 X 1` then its just the image again, which is not feature extraction actually.
3. Reason 3: If we are using a even kernel size of `2 X 2` - If we consider the output pixels after the feature extractor it is obtained by convolving on the previous layer pixel. And all the previous layer pixel will be symmetrically around these pixels (outplut layer). without these symmetry we have to account for distrotion across the layers. This prob occurs on using a even size filter.

### Question 3: How many times to we need to perform 3x3 convolutions operations to reach close to 1x1 from 199x199 (type each layer output like 

100 times we need to iterate to reach close to to 1X1

199X199 > 197X197 > 195X195 > 193X193 > 191X191 > 189X189 > 187X187 > 185X185 > 183X183 > 181X181 > 179X179 > 177X177 > 175X175 > 173X173 > 171X171 > 169X169 > 167X167 > 165X165 > 163X163 > 161X161 > 159X159 > 157X157 > 155X155 > 153X153 > 151X151 > 149X149 > 147X147 > 145X145 > 143X143 > 141X141 > 139X139 > 137X137 > 135X135 > 133X133 > 131X131 > 129X129 > 127X127 > 125X125 > 123X123 > 121X121 > 119X119 > 117X117 > 115X115 > 113X113 > 111X111 > 109X109 > 107X107 > 105X105 > 103X103 > 101X101 > 99X99 > 97X97 > 95X95 > 93X93 > 91X91 > 89X89 > 87X87 > 85X85 > 83X83 > 81X81 > 79X79 > 77X77 > 75X75 > 73X73 > 71X71 > 69X69 > 67X67 > 65X65 > 63X63 > 61X61 > 59X59 > 57X57 > 55X55 > 53X53 > 51X51 > 49X49 > 47X47 > 45X45 > 43X43 > 41X41 > 39X39 > 37X37 > 35X35 > 33X33 > 31X31 > 29X29 > 27X27 > 25X25 > 23X23 > 21X21 > 19X19 > 17X17 > 15X15 > 13X13 > 11X11 > 9X9 > 7X7 > 5X5 > 3X3 > 1X1

### How are kernels initialized? 

The values in the Kernels are initialized from the sample of random numbers.

### What happens during the training of a DNN?
*In general training the neural network is someting we are trying to reach the optimal weights and bias by reducing the overall error.*
*High Level explanation :* The Deep Neural network consist of different connected layers of node, And each node has many weights and bias inititalized for an example. Lets take an example of classifying the image as cat or dog - So the DNN tries to predict whether the given image is cat or dog, based on the prediction the DNN will compute the error between the prediction and the expected result. Based on the error, it back propagates through the layer and updates the parameters to reduce the error in the sub sequent predictions.