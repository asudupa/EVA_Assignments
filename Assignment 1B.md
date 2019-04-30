# EVA Project1 - Assignment 1B
What are Channels and Kernels (according to EVA)?









Why should we only (well mostly) use 3x3 Kernels?
3x3 is popular and widely used kernel size in the industry. Kernel size is always set to odd number (square matrix) as even numbered filter does not facilitate in maintaining symetry, and also to avoid waste of computational capacity. 
Local receptive field with 3x3 is smaller thus captures complex, local and finer details in each convolution. These finer details might be useful in later layers.
Hardware manufacturers have optimized the GPU for 3x3 kernel. Thus computation is much faster compared to larger filters. Using larger kernels will take more time than 3x3.
Further 3x3 kernel helps in reducing the parameters for computation than larger filters. For ex: for a 7x7x1 input image, a 5x5 kernel will have to scan twice (5x5, 1x1) to reach 1x1; thus (5x5) + (5x5) = 50 parameters, while a 3x3 kernel will take 3 scans; 5x5, 3x3, 1x1; thus 9+9+9 = 27 parameters, which is 23 lesser than 5x5. Lesser parameters results in lesser computation and faster computation.
Because of larger number of layers required to cover the image, complex and npn-linear features can be learnt










How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations).
Without Maxpooling, it takes 99 operations to reach 199x199 to 1x1.

In below list, each convolution operation (3x3) reduces the receptive field size by 2(with stride of 1 and padding 0). As counted, below the convolution size is the layer count.

199	197	195	193	191	189	187	185	183	181	179	177	175	173	171	169	167
	1	 2	3	  4	   5	 6	 7	 8	 9	10	 11	 12	13	14	15	16
	
165	163	161	159	157	155	153	151	149     147	145	143	141	139	137	135    133
 17	18	19	20	21	22	23	24	25       26	27	28	29	30	31	32	33
																									
131	129	127	125	123	121	119	117	115	113	111	109	107	105	103	101	99
34	35	36	37	38	39	40	41	42	43	44	45	46	47	48	49	50
																									
97  95	93	91	89	87	85	83	81	79	77	75	73	71	69	67	65	63	61	59	57	55	53	51	49
51  52	53	54	55	56	57	58	59	60	61	62	63	64	65	66	67	68	69	70	71	72	73	74	75
																									
47   45   43	41	39	37	35	33	31	29	27	25	23	21	19	17	15	13	11	9	   7	 5	 3	 1				
76   77   78	79	80	81	82	83	84	85	86	87	88	89	90	91	92	93	94	95	96	97	98	99				

199 -0, 197 -1, 195-2, 	193 -3, 191 -4, 189 -5,	187 -6, 185 -7, 183 -8,	181 -9,	179 -10, 177 -11, 175 -12, 173 -13, 171 -14, 169 -15, 	167 -16, 165 -17, 163 -18, 161 -19, 159 -20, 157 -21, 	155 -22, 153 -23, 151 -24, 149 -25, 147 -26, 145 -27, 143 -28, 141 -29, 139 -30, 137 -31, 135 -32, 133 -33, 131 -34, 129 -35, 127 -36, 125 -37, 123 -38, 121 -39, 119 -40, 117 -41, 115 -42, 113 -43, 111 -44, 109 -45, 107 -46, 105 -47, 103 -48, 101 -49, 99 -50, 97 -51, 95 -52, 93 -53, 91 -54, 89 -55, 87 -56, 85 -57, 83 -58, 81 -59, 79 -60, 77 -61, 75 -62, 73 -63, 71 -64, 69 -65, 67 -66, 65 -67, 63 -68, 61 -69, 59 -70, 57 -71, 55 -72, 53 -73, 51 -74, 49 -75, 47 -76, 45 -77, 43 -78, 41 -79, 39 -80, 37 -81, 35 -82, 33 -83, 31 -84, 29 -85, 27 -86, 25 -87, 23 -88, 21 -89, 19 -90, 17 -91, 15 -92, 13 -93, 11 -94, 9 -95, 7 -96, 5 -97, 3 -98, 1 -99, 

