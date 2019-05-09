# Malaria Parasite Detection using Deep Learning

In this project I have used the publicly available dataset of blood smear cell images published by NIH. The dataset consists 
of equal counts of parasitized and uninfected cases of cell images ,i.e,
* 13,779 Parasitized cell images
* 13,779 Unifected cell images

The link to this dataset is [here](https://ceb.nlm.nih.gov/repositories/malaria-datasets/).

##### Introduction:
Malaria is a serious problem in the developing world with over 216 Million reported cases just in 2016. This disease is spread by mosquitoes and is caused by single celled parasitic organisms called plasmodium. Till date, diagnosis of malaria is done by microscopic examination, which is held as the “gold standard” for laboratory confirmation of malaria. This procedure can be tedious and possibly erroneous, with some subjectivity leading to inconsistent or incorrect diagnosis which may cause incorrect or untimely treatment or even result in the death of the patient. To solve this problem NIH proposed a deep learning solution - to automatically count parasites using CNN in digitized images of blood films. 

The Published paper of this work at NIH is [Pre-trained convolutional neural networks as feature extractors toward improved malaria parasite detection in thin blood smear images](https://lhncbc.nlm.nih.gov/system/files/pub9752.pdf). 

In this paper they used following six pre-trained CNN's :
* A custom CNN architecture built by them
* ResNet-50
* Xception
* AlexNet
* VGG-16
* DenseNet-121

They used these models for feature extraction and subsequent training which in all took a little over 24 hours. They obtained 95.9% accuracy.

I think this strategy is not optimal as having so many models is computaionally inefficient. 

So, in this project I aim to build a custom CNN model using keras with following traits:
* Comparable accuracy with the NIH model
* Smaller architecture (model) which takes less time to train and is computationally efficient

# Results:
I was able to built a CNN model that trained significalty faster than the NIH model (~ 10 mins) and also had a comparable performance if not better (95.75% accuracy).

Here is the accuracy plot for training and validation data:


![Accuracy Plot](https://github.com/npatel25/Malaria-Parasite-Detection/blob/master/final_acc_plot.png)

Below is the classification report:


                  precision  recall   f1-score   support

    Parasitized       0.98      0.94      0.96      2767
    Uninfected        0.94      0.98      0.96      2745

    micro avg         0.96      0.96      0.96      5512
   
    macro avg         0.96      0.96      0.96      5512
   
    weighted avg      0.96      0.96      0.96      5512
