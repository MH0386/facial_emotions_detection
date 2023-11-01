# Related Work

The provided related work discusses various studies on Facial Emotion Recognition using convolutional neural networks (CNNs). Here is a summary of the key points from each study:

1. Yu et al. [39] proposed a biometric quality assessment (BQA) method using a light CNN, which showed high effectiveness in FR applications.
2. Sun et al. [40] used a hybrid deep learning approach combining a ConvNet based on the restricted Boltzmann machine (RBM) model for face verification, achieving excellent performance compared to other methods.
3. Singh and Om [41] used a deep CNN to identify individuals from newborn infant datasets, finding that increasing the number of hidden layers did not improve identification accuracy.
4. Guo et al. [42] developed a CNN-based model that used both visible light and near-infrared images for facial recognition, achieving enhanced performance and robustness to illumination variation.
5. Hu et al. [43] investigated the performance of CNNs on 2D and 3D FR systems, finding better accuracy with their CNN-2 model on both types of recognition.
6. Nam et al. [44] proposed a CNN model named PSI-CNN for face recognition, which outperformed the VGG-Face model and maintained stable performance with low-resolution images.
7. Prasad et al. [7] studied deep learning-based face representation for various FR challenges, showing that VGG-Face and lightened CNN approaches provided good results.
8. Khan et al. [45] proposed a face recognition system using portable smart glasses based on CNN, achieving high-detection and accuracy rates.
9. Qin et al. [46] developed a recognition algorithm based on deep CNNs, which performed well on recognizing faces with various poses in an indoor environment.
10. Menotti et al. [47] investigated deep learning approaches for iris spoof detection and fingerprint variations, emphasizing the need for comprehensive spoofing detection frameworks.
11. Simón et al. [48] proposed a multimodal facial recognition approach using CNNs fused with different feature descriptors, significantly reducing the recognition error rate.
12. Parkhi et al. [49] proposed the VGG-Face system, a 16-layer CNN trained on a large image database, achieving improved results in face recognition.
13. Zhenyao et al. [50] used a deep network to warp faces into a canonical frontal view and performed face verification using PCA and an ensemble of SVMs.
14. Guo et al. [51] developed an FR system based on CNNs and optimized training techniques, achieving high-recognition rates in less training time.
15. Deep-Face [13] trained an eight-layer CNN architecture on a large face database, achieving exemplary performance in face recognition benchmarks.
16. DeepID [53] used an ensemble of small CNNs and network fusion for face verification, achieving high accuracy on the LFW dataset.
17. DeepID2+ [55] improved upon DeepID and DeepID2 by using a larger training set and enhancing the number of filters in all layers, resulting in sparse, selective, and robust face representations.
18. Lu et al. [56] proposed the Deep Coupled ResNet (DCR) model, consisting of a trunk network and two branch networks, which achieved better performance than state-of-the-art models on the LFW and SCface datasets.

These studies demonstrate the effectiveness of CNNs for various FR tasks, including face quality assessment, verification, identification, and recognition. The researchers used different CNN architectures, optimization techniques, and datasets to improve performance and address specific challenges in FR.

## Summary of Methodology and Experiments:

### Methodology:

Two approaches were followed in the study:
* Using pre-trained CNNs (AlexNet and ResNet-50) for feature extraction and SVM for classification.
* Applying transfer learning from AlexNet for feature extraction and classification.

The stages of the study included pre-processing, face representation using CNNs, and classification. SVM was chosen as the classifier due to its effectiveness in handling nonlinear data and pattern recognition problems. The SVM classification process involved finding a hyperplane that maximizes the margin between two input classes. The study did not focus on optimizing SVM strategies.


### Experiments:

The experiments were conducted on a Windows platform with an Intel Core i7 CPU, 16 GB RAM, and NVIDIA GEFORCE GTX 1050TI. MATLAB 2018a was used for evaluating the method, feature selection, and classification. Pre-processing involved resizing images to suitable sizes (227x227 for AlexNet and 224x224 for ResNet-50). The performance of the pre-trained CNN system was evaluated based on recognition accuracy. Three datasets were used in the study:
* ORL database: It contains 10 images of 40 individuals with variations in face angles, expressions, and details.
* GTAV face database: It includes images of 44 individuals with different pose views and illuminations.
* Georgia Tech face database: It consists of images of 50 individuals taken in different sessions, orientations, and scales.

Overall, the study aimed to investigate face recognition performance using CNNs, SVM, and transfer learning. The effectiveness of different approaches and the comparison between SVM and transfer learning from pre-trained AlexNet were analyzed using multiple datasets.



#### Experiment 1: Pre-Trained CNN AlexNet with SVM

The experiment used a pre-trained CNN model called AlexNet.The images were resized to 227x227 pixels and converted to RGB. The data was split into 80% training and 20% test sets. Features were extracted from different layers of the network, specifically `fc6`, `fc7`, and `fc8`. SVM (Support Vector Machine) was trained using the extracted features. The highest recognition accuracy was achieved with features extracted from the 'fc7' layer. The model achieved high accuracy on various datasets: 100% on YTF, 99.55% on GTAV face, 99.17% on ORL, and 98% on F_FLW. Lower accuracy was obtained on FEI (97.50%), Georgia Tech face (96%), and LFW (94%) datasets.

#### Experiment 2: Pre-Trained ResNet-50 Model with SVM

The experiment used a pre-trained CNN model called ResNet-50.The images were resized to 224x224 pixels and converted to RGB.The data was split into 70% training and 30% validation sets.Features were extracted from the 'fc1000' layer.SVM was trained using the extracted features.The ResNet-50 model achieved high accuracy on several datasets: 100% on GTAV face, ORL, and YTF, 98.50% on FEI, and 96% on Georgia Tech face. The specific accuracy for the LFW dataset is not mentioned in the provided information.

##### Summary of Experiment 2:
Both experiments used pre-trained CNN models (AlexNet and ResNet-50) for feature extraction, followed by training SVM classifiers. The experiments achieved high-recognition accuracy on various datasets, with the best results obtained using features from specific layers of the networks.





#### Experiment 3: Transfer learning from AlexNet for feature extraction and classification:

* **Model Architecture**: AlexNet, a pre-trained network with 25 layers, was used. The first 23 layers were used for feature extraction, while the last three layers were for classifying the features into 1000 groups.

* **Transfer Learning**: The last three layers of AlexNet were removed, and a new fully connected layer was added to match the number of classes in the new dataset. This transferred network was then trained on the new classification task.

* **Training Setup**: The model was trained with different numbers of epochs, and the highest accuracy was achieved with 20 epochs. A mini-batch size of 20 was used, and the network was validated every 3 training steps. The data was divided into 70% for training and 30% for validation.




* Performance Analysis:

  * **Accuracy**: The transfer learning model achieved the highest accuracy of 100% on the Georgia Tech face dataset, GTAV face dataset, and YouTube face dataset. The AlexNet + SVM model achieved 100% accuracy on the YTF dataset, while the ResNet-50 + SVM model achieved 100% accuracy on the GTAV face, ORL, and YTF datasets.
  * **Precision**: All approaches (AlexNet + SVM, ResNet-50 + SVM, transfer learning from AlexNet) achieved precision values between 92% and 99.50%.
  * **Recall**: All approaches achieved high-recall results between `93%` and `99.98%`
  * **F-Measure**: The transfer learning model achieved the highest F-Measure results overall, but the ResNet-50 + SVM model obtained the highest value with the ORL dataset.

* **Testing Time**: The ResNet-50 + SVM model exhibited faster testing times compared to the other networks with all datasets. The transfer learning model using AlexNet took less time than the AlexNet + SVM model.

* **Dataset Performance**:
  * FEI Faces: All three models achieved good accuracy, with the transfer learning model achieving the highest accuracy of 98.7%.
  * ORL Dataset: All three models outperformed previous state-of-the-art models, with accuracy ranging from 99.17% to 100%.
  * YouTube Face Dataset: All models achieved 100% accuracy, surpassing previous results.
  * LFW Dataset: The transfer learning model achieved an accuracy of 95.63%, while the other models achieved 94%. These results were higher than some previous methods that used pre-processing techniques.

##### Summary of Experiment 3:

The transfer learning model from AlexNet showed improved performance compared to the AlexNet + SVM model in terms of accuracy, precision, recall, and F-Measure. It achieved high accuracy on various datasets and demonstrated better time efficiency compared to other models.


















