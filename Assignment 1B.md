# EVA Project1 - Assignment 1B
What are Channels and Kernels (according to EVA)?  
**Kernel** is a matrix which filter/extract features from the input image when applied. Kernel; typically of size 3x3 is convolued over input image to get an output. Kernel values depend on what feature is been extracted. Initally set random numbers, they are updated during back propagation for effective extraction of features. In initial layers basic features like edges, shades are extracted, it progressively extracts complex features in later layers.

**Channel** is a container for convolved feature extracted by a kernel. When a kernel is convolved over the image, the resultant matrix is channel. There can be multiple chanels from a given input; at begining recieving raw input image or output of a convolved layer being fed as input to next layer. Each channel has its own kernel, focusing on extracting specific feature. For ex: with colors, there could be 3 each for color Red, Green, Blue. Or of different color filters. It could also be for extractng edges, shapes in intial layers and go on to extract edges, parts, c&nbsp;omplex parts, etc. Typically a layer will have atleast same number of channels as in previous layer. Number of channels can be increased, or merged as required in network.  
Another example can be a image of peas pulav, which is a combination of multiple ingredients. We can define kernels to filter/extract each ingredient like; peas, rice, onions, bayleaf, spice etc. These featuers are onctained in a channel, when merged gets back to original image. Similiarly same can be extended to music composition or essay with English essay which is made up of 26 chars, channels one for each char in alphabet. In a music composition, it made of different instruments and can be seperated in different channels for each instrument. In these example each ingredient/alphabet/musical instrument are all kernel.
In practise we dont define each channel and what is extracts. Number of channels is specified and network will identify what channels are required and defines the kernel values required to extract the feature.




Why should we only (well mostly) use 3x3 Kernels?  
3x3 is popular and widely used kernel size in the industry. Kernel size is always set to odd number (square matrix) as even numbered filter does not facilitate in maintaining symetry, and also to avoid waste of computational capacity. 
Local receptive field with 3x3 is smaller thus captures complex, local and finer details in each convolution. These finer details might be useful in later layers.
Hardware manufacturers have optimized the GPU for 3x3 kernel. Thus computation is much faster compared to larger filters. Using larger kernels will take more time than 3x3.
Further 3x3 kernel helps in reducing the parameters for computation than larger filters. For ex: for a 7x7x1 input image, a 5x5 kernel will have to scan twice (5x5, 1x1) to reach 1x1; thus (5x5) + (5x5) = 50 parameters, while a 3x3 kernel will take 3 scans; 5x5, 3x3, 1x1; thus 9+9+9 = 27 parameters, which is 23 lesser than 5x5. Lesser parameters results in lesser computation and faster computation.
Because of larger number of layers required to cover the image, complex and npn-linear features can be learnt




![alt text](https://github.com/asudupa/Project1/blob/master/conv.gif)  
![alt text](https://github.com/asudupa/Project1/blob/master/convolution.png)  






How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations).
Without Maxpooling, it takes 99 operations to reach 199x199 to 1x1.

In below list, each convolution operation (3x3) reduces the receptive field size by 2(with stride of 1 and padding 0). Layer count is  indexed next to size starting from 199x199 till 1x1.

199 -0, 197 -1, 195-2, 	193 -3, 191 -4, 189 -5,	187 -6, 185 -7, 183 -8,	181 -9,	179 -10, 177 -11, 175 -12, 173 -13, 171 -14, 169 -15, 	167 -16, 165 -17, 163 -18, 161 -19, 159 -20, 157 -21, 	155 -22, 153 -23, 151 -24, 149 -25, 147 -26, 145 -27, 143 -28, 141 -29, 139 -30, 137 -31, 135 -32, 133 -33, 131 -34, 129 -35, 127 -36, 125 -37, 123 -38, 121 -39, 119 -40, 117 -41, 115 -42, 113 -43, 111 -44, 109 -45, 107 -46, 105 -47, 103 -48, 101 -49, 99 -50, 97 -51, 95 -52, 93 -53, 91 -54, 89 -55, 87 -56, 85 -57, 83 -58, 81 -59, 79 -60, 77 -61, 75 -62, 73 -63, 71 -64, 69 -65, 67 -66, 65 -67, 63 -68, 61 -69, 59 -70, 57 -71, 55 -72, 53 -73, 51 -74, 49 -75, 47 -76, 45 -77, 43 -78, 41 -79, 39 -80, 37 -81, 35 -82, 33 -83, 31 -84, 29 -85, 27 -86, 25 -87, 23 -88, 21 -89, 19 -90, 17 -91, 15 -92, 13 -93, 11 -94, 9 -95, 7 -96, 5 -97, 3 -98, 1 -99, 

