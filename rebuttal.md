#### **Table S2. Training-free methods surpass supervised baselines on challenging low-data regimes (MSAD, UBnormal).**
|   Methods	|Supervision| MSAD $AUC$ 	|MSAD $AUC_a$  |MSAD $AP$|MSAD  $AP_a$ |UBnormal $AUC$   |
|------|-------|-------|-------|-------|-------| -------|
|RTFM     | Weakly Supervised|  86.65           |     -		| 66.30	|         -    |  60.94|
|OVVAD| Weakly Supervised|  -           |     -		|  -	|         -                    |  62.94|
|MGFN |  Weakly Supervised|   84.96		 |    -         	|   -	| -	 | -|   
|TEVAD |  Weakly Supervised|  86.82		 |    -           	|     -	| -      | -|
|UR-DMU  |  Weakly Supervised|   85.78	|    67.95          |    67.35	| 75.30  | 59.9|
|$\pi$ VAD |  Weakly Supervised|   88.68	|    71.25    |     71.26	| 77.86   | -|
|LAVAD |**Training-Free**		|  -           |     -		|  -	|         -    |  64.23|
|VADTree |**Training-Free**		|89.32|67.85|71.41|75.49 |-|
|Unified |**Training-Free**			|85.9|-|76.4|-|68.98|
|PANDA |**Training-Free**			|-|-|-|- |**75.78**|
|**OneVAD(ours)** |**Training-Free**|**92.36**|**76.47**|**78.19**|**81.45** |74.30|


#### **Table S2  Component-level inference time consumption analysis of different methods on UCF-Crime.**
|   Methods	| Video segmentation			|Video/Text Encoding  |VLM Caption			| LLM Summary |LLM Scoring		| Total(GPU hours)| AUC(%)|
|------|-------|-------|-------|    -------|     -------|  -------|  -------| 
|LAVAD(CVPR2024)    |   -                                     			|     5.1h           		|   20h  				| 7.7h$\times$2 	|   7.7h$\times$2 		|	55.9			| 80.28	| 
|VADTree(NeurIPS2025)    |   0.3h			                                |    0.6h              		|     20.0h$\times$2	| -			   	| 	10.7h$\times$2	|	62.3			| 84.71 	|  
|			   |  							|					|   **VLM Holistic pass**     | **Collaborative Localization**|**VLM Zoom-in pass**	|			 |
|**OneVAD(Ours)** |  0.3h 			                        |    -               		    	|     17.2h$\times$2	|  	0.6h$\times$2		|2.8h$\times$2		|	41.5	| **86.48**	|  
