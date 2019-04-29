# EVA Project1 - Assignment 1B
What are Channels and Kernels (according to EVA)?









Why should we only (well mostly) use 3x3 Kernels?












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
