## **Table S1. Training-free methods surpass supervised baselines on challenging low-data dataset (MSAD, UBnormal).**
|   Methods	| Supervision          | MSAD $AUC$ 	|MSAD $AUC_a$  |MSAD $AP$|MSAD  $AP_a$ | UBnormal $AUC$ |
|------|----------------------|-------|-------|-------|-------|----------------|
|RTFM     | Weakly Supervised    |  86.65           |     -		| 66.30	|         -    | 60.94          |
|OVVAD| Weakly Supervised    |  -           |     -		|  -	|         -                    | 62.94          |
|MGFN | Weakly Supervised    |   84.96		 |    -         	|   -	| -	 | -              |   
|TEVAD | Weakly Supervised    |  86.82		 |    -           	|     -	| -      | -              |
|UR-DMU  | Weakly Supervised    |   85.78	|    67.95          |    67.35	| 75.30  | 59.9           |
|$\pi$ VAD | Weakly Supervised    |   88.68	|    71.25    |     71.26	| 77.86   | -              |
|Holmes-VAU | Instru-Tuned         |    -	|     -    |      -	|  -   | 56.77          |
|LAVAD | **Training-Free**		  |  -           |     -		|  -	|         -    | 64.23          |
|VADTree | **Training-Free**		  |89.32|67.85|71.41|75.49 | -              |
|Unified | **Training-Free**			 |85.9|-|76.4|-| 68.98          |
|PANDA | **Training-Free**			 |-|-|-|- | **75.78**      |
|**OneVAD(ours)** | **Training-Free**    |**92.36**|**76.47**|**78.19**|**81.45** | 74.30          |
**Note.** The MSAD dataset has fewer training samples for each type of anomaly, while UBnormal is an open-set dataset.

## **Table S2 Component-level inference time consumption analysis of different methods on UCF-Crime dataset.**
|   Methods	| Video segmentation			|Video/Text Encoding  | VLM Caption			        | LLM Summary                    | LLM Scoring		         | Total(GPU hours)| AUC(%)|
|------|-------|-------|-----------------------|--------------------------------|-----------------------|  -------|  -------| 
|LAVAD(CVPR2024)    |   -                                     			|     5.1h           		| 20h  				             | 7.7h $\times$ 2 	              | 7.7h $\times$ 2 		    |	55.9			| 80.28	| 
|VADTree(NeurIPS2025)    |   0.3h			                                |    0.6h              		| 20.0h $\times$ 2	     | -			   	                       | 	10.7h $\times$ 2	    |	62.3			| 84.71 	|  
|			   |  							|					| **VLM Holistic pass** | **Collaborative Localization** | **VLM Zoom-in pass**	 |			 |
|**OneVAD(Ours)** |  0.3h 			                        |    -               		    	| 17.2h $\times$ 2	     | 	0.6h $\times$ 2		             | 2.8h $\times$ 2		     |	41.5	| **86.48**	|  


## **Table S3. Comparison of Decision Period, Processing Time, and Decision Delay.**
|   Methods| Decision Period(s)   |  Processing Time(s)   | Delay(s) | 
|------|-------|-------|-------|    
REWARD| 6.4| 0.5| 6.9|
Montior|0.6 |5.9 |6.5|
OneVAD-online(ours)| 5 |1.3 |6.3|

## **Table S4 FP**

## **Table S5. Effect of different intermediate-layer ranges on attention aggregation stability and anomaly detection performance (AUC) on UCF-Crime dataset.**
| Attention Aggregation Range (Layers) | Localization Stability (Range Consensus sIoU) | AUC(%) | 
|---------------------------|----------------------------------------------|-------|    
| 1 - 20                    | 0.3898                                       | 85.64 | 
| 10 - 28                   | 0.4480                                       | 85.87 | 
| 10 - 20(Ours)             | **0.4905**                                   | **86.48** |
**Note.** Range Consensus sIoU is computed as the mean soft IoU between each selected layer and the layer-range prototype attention, averaged over all decode steps, segments, and videos. Since attentions were dumped with layer interval = 2, only saved even-numbered layers within each requested range are used.

## **Table S6. Comparison of performance of OneVAD under different VLM on UCF-Crime dataset.**
| Methods        | AUC(%) | 
|----------------|--------| 
| Qwen2.5VL-8B   | 0.5    |
| Qwen2.5VL-8B   | 0.5    |
| InternVL3-8B   | 0.6    |
| InternVL3_5-8B | 5      |
| InternVL3_5-8B | 5      |
