# CNN Based with ensemble method for PCB Defects Multi label Classification
### Brief Description
- A course project for Cloud Computing and Big Data Analytics
### Motivation
#### Background
- Many difficult market pressures.
- During manufacturing, the PCB goes through several process steps
- PCB board goes through various stages of production
- The need is for a reliable and accurate vision system
#### Challenges
- Largely dependent on user input to select algorithm set for the PCB 
- AOI equipment is commonly used for defect detection, which has the characteristic of “it is better to kill a hundred mistakes than to let one go”
### Dataset
- The dataset is from the competition Defect Classifications of AOI from AIdea
- [Download Link](https://tinyurl.com/uwrxf9f5)
- Format : PNG
- Data split : 1,769 for Training set, 379 for valid set, 380 for Test set.
- Label : defect classification category (shown in below table).

![image](https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/pic/label%20info.png)

- Sample Imgaes

![image](https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/pic/sample.png)

### Framework
- We implement two models with three ensemble that we have mentioned before. The work flow of our project is as below:

![image](https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/pic/workflow.png)

### Experimental Results
#### Single Model
- First, we implement only single machine to do detection, the result is as below:

![image](https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/pic/result%20of%20single%20model.png)
- We can observe the results and figure out that EfficientNet gets better performance than CoAtNet.
In addition, we visualize the picture by using grad cam after processed through the prediction. With Grad-CAM, we can understand the basis for the model's predictions.
![image](https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/pic/Experiments%20Result%20-%20Feature%20maps%20visualization%20of%20Efficientnet_B0.png)
![image](https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/pic/Experiments%20Result%20-%20Feature%20maps%20visualization%20of%20CoatNet.png)

#### Ensemble method part
- Here, we implement the three ensemble method (Voting, Soft Gradient Boosting, Snapshot Ensemble)
##### Acc of Two Model
![image](https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/pic/result%20ensemble%20of%20two%20models.png)
##### Acc of Three Model
![image](https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/pic/result%20ensemble%20of%20three%20models.png)

### Conclusion
#### Models
- In general, EffiecientNet got higher accuracy than coAtNet.
- CoAtNet performs better only when using Snapshot Ensemble of three models.
#### Ensemble
- Voting Classifier got both 100% with two models
- Soft Gradient Boosting has higher accuracy when ensemble 2 models
- Snapshot Ensemble has higher accuracy when ensemble 3 models

### Appendix and source code repo
- for more detail : https://github.com/KartaYu/CNN-Based-with-ensemble-method-for-PCB-Defects-Multi-label-Classification/blob/main/Documentation/Full%20Report.pdf
- [dataset resource](https://aidea-web.tw/topic/a49e3f76-69c9-4a4a-bcfc-c882840b3f27?lang=en)
- [torchessemble](https://github.com/TorchEnsemble-Community/Ensemble-Pytorch)
- [coatnet](https://github.com/chinhsuanwu/coatnet-pytorch)
