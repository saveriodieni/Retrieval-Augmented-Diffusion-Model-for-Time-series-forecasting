|		             | ETTm1	         		             | ETTm2	         		             | ETTh1	         		             | ETTh2	         		             |

|--------------------|---------------------------------------|---------------------------------------|---------------------------------------|---------------------------------------|

| Model              | MSE     | MAE     | CRPS    | QICE    | MSE     | MAE     | CRPS    | QICE    | MSE     | MAE     | CRPS    | QICE    | MSE     | MAE     | CRPS    | QICE    |

|--------------------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|

| NsDiff             | 0.4468  | 0.4333  | 0.3402  | 2.4697  | 0.3499  | 0.3876  | 0.2912  | 2.6343  | 0.6606  | 0.5638  | 0.4149  | 0.9897  | **0.5062**  | **0.4948**  | **0.3679**  | 1.7390  |

| NsRatd-v1 w/o ref  | 0.4465  | *0.4307*  | *0.3309*  | *2.0358*  | 0.3482  | 0.3877  | 0.2899  | **2.6217**  | 0.6692  | 0.5655  | 0.4161  | 1.1367  | 0.5343  | 0.5044  | 0.3735  | 1.3671  |

| NsRatd-v1 with ref | **0.4367**  | **0.4304**  | **0.3270**  | **1.6630**  | 0.3479  | 0.3871  | *0.2896*  | *2.6294*  | 0.6664  | 0.5650  | 0.4157  | 1.0712  | *0.5329*  | *0.5038*  | *0.3723*  | **1.2858**  |

| NsRatd-v2 w/o ref  | 0.4477  | 0.4339  | 0.3418  | 2.4867  | **0.3396**  | **0.3794**  | **0.2848**  | 2.6869  | *0.6536*  | *0.5608*  | *0.4101*  | *0.9327*  | 0.5345  | 0.5040  | 0.3736  | 1.4249  |

| NsRatd-v2 with ref | *0.4452*  | 0.4330  | 0.3396  | 2.3961  | *0.3462*  | *0.3859*  | 0.2912  | 2.7085  | **0.6006**  | **0.5490**  | **0.4037**  | **0.7939**  | 0.5342  | 0.5046  | 0.3733  | *1.3052*  |


Given the full metric table, I counted how many times each model achieved the best value for each metric. I then produced two 
summaries: one considering only the best (top-1) results, and another counting both the best and second-best (top-2) results.
Looking at the top-1 summary, the models obtain a relatively similar number of best results, which makes it difficult to 
distinguish their overall performance. However, when we consider the top-2 results, the difference becomes clearer: both versions 
of NsRatd consistently outperform NsDiff across most metrics and datasets.
When aggregating the two NsRatd variants, the advantage becomes even more evident. 
Furthermore, the two NsRatd versions exhibit different behavior:
- NsRatd-v1 benefits more noticeably from the use of a reference, consistently improving when the reference is included.
- NsRatd-v2, on the other hand, shows stronger results even without the reference, and the improvement from the reference is more 
moderate.
Overall, these results indicate that the reference mechanism is generally beneficial.


| Model              | Best MSE | Best MAE | Best CRPS | Best QICE | **Total Best** |
| ------------------ | :------: | :------: | :-------: | :-------: | :------------: |
| NsDiff             |     1    |     1    |     1     |     0     |      **3**     |
| NsRatd-v1 w/o ref  |     0    |     0    |     0     |     1     |      **1**     |
| NsRatd-v1 with ref |     1    |     1    |     1     |     2     |      **5**     |
| NsRatd-v2 w/o ref  |     1    |     1    |     1     |     0     |      **3**     |
| NsRatd-v2 with ref |     1    |     1    |     1     |     1     |      **4**     |

| Model              | Best MSE | Best MAE | Best CRPS | Best QICE | **Total Best** |
| ------------------ | :------: | :------: | :-------: | :-------: | :------------: |
| NsDiff             |     1    |     1    |     1     |     0     |      **3**     |
| NsRatd w/o ref     |     1    |     1    |     1     |     1     |      **4**     |
| NsRatd with ref    |     2    |     2    |     2     |     3     |      **9**     |


| Model              | MSE Top-2 | MAE Top-2 | CRPS Top-2 | QICE Top-2 | **Total Top-2** |
| ------------------ | :-------: | :-------: | :--------: | :--------: | :-------------: |
| NsDiff             |     1     |     1     |      1     |      0     |      **3**      |
| NsRatd-v1 w/o ref  |     0     |     1     |      1     |      2     |      **4**      |
| NsRatd-v1 with ref |     2     |     2     |      3     |      3     |      **10**     |
| NsRatd-v2 w/o ref  |     2     |     2     |      2     |      1     |      **7**      |
| NsRatd-v2 with ref |     3     |     2     |      1     |      2     |      **8**      |

| Model              | MSE Top-2 | MAE Top-2 | CRPS Top-2 | QICE Top-2 | **Total Top-2** |
| ------------------ | :-------: | :-------: | :--------: | :--------: | :-------------: |
| NsDiff             |     1     |     1     |      1     |      0     |      **3**      |
| NsRatd w/o ref     |     2     |     3     |      3     |      3     |      **11**     |
| NsRatd with ref    |     5     |     4     |      4     |      5     |      **18**     |