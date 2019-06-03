## M1 Abrams Tank Classifier

#### Project Goal 

Train a CNN model to determine whether a given image contains an M1 Abrams tank or not.

#### Motivation

Open source research such as that conducted by Bellingcat is a tedious process, especially so when it involves analyzing photos and videos from a conflict zone. To accelerate this process, I wanted to build a proof of concept CNN that would accurately determine if an image contains an M1 Abrams tank.

#### Dataset

I used the [Fatkun Batch Download Image](https://chrome.google.com/webstore/detail/fatkun-batch-download-ima/nnjjahlikiabnchcpehcpkdeckfgnohf?hl=en) extension for Google Chrome to download results of a Google Image search. The resulting dataset required manual cleaning as the downloader is fairly brute force and Google Image searches were sometimes polluted with images of non-Abrams tanks.

#### Training

I used Google Colab to provide added compute power and TensorBoard to visual the model's learning in real time.

#### Conclusions on v1

The model was successfully able to detect the presence of an M1 Abrams tank in each of the four test images I passed it from various Iraqi militia social media accounts. More broadly, the model performs well on the testing data.

###### TensorBoard Graph showing loss on validation data over 100 epochs

<img width="1077" alt="Screen Shot 2019-04-21 at 9 35 50 PM" src="https://user-images.githubusercontent.com/31871105/56478449-7c438480-647d-11e9-9725-7c7c37cc3d6d.png">

###### TensorBoard Graph showing accuracy on validation data over 100 epochs

<img width="1071" alt="Screen Shot 2019-04-21 at 9 37 47 PM" src="https://user-images.githubusercontent.com/31871105/56478501-e1977580-647d-11e9-80fb-ac96bd8cebc6.png">

#### Next Steps

1. Further adjust layers in the CNN to see if I can further reduce false negatives.
2. Determine what other systems or equipment are of similar "high risk" and train models to detect them.
