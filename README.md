## M1 Abrams Tank Classifier

#### Project Goal: Train a CNN model to determine whether a given image contains an M1 Abrams tank or not.

The massive amount of images and footage uploaded to social media today from conflict zones has provided opportunities for creative and new types of research and analysis. Experts such as those at Bellingcat and Armament Research Services have proven the power of this new type of open-source information in their analysis on everything from chemical weapons attacks to the capabilities of various armed opposition groups in Syria.

In some cases, these arms control experts spend hours sifting through battlefield footage and pictures to assess what types of weapons each combatant is using. This work is extremely important in ensuring that weapons legally sold or transferred from one country to another are not then sold or otherwise transferred to potentially unintended third-party users.

One of the more alarming such incidents occurred in Iraq in 2015 when Kata'ib Hezbollah, an Iraqi Shia militia group sanctioned as a terrorist organization by the US Treasury, uploaded a video to YouTube showing that an M1 Abrams tank had come into their possession. These main battle tanks had been sold by the United States to the Iraqi Army over the past decade, but it is unclear then how Kata'ib Hezbollah came to be in possession of one of them.

(https://www.longwarjournal.org/archives/2015/01/video-shows-hezbollah-brigades-convoy-transporting-american-m1-tank.php)

A model that can accurately determine whether an image contains this very specific American tank can massively accelerate the work of these arms control experts and allow them to focus more issues such as keeping up with new, useful social media accounts to follow or determining just how the tank may have been transferred from the intended end user to the third party.

#### Dataset

For my dataset, I downloaded and curated a set of images of ~1500 M1 Abrams tanks alongside ~400 images of similar military equipment as the other class using the Fatkun Batch Downloader Chrome extension. Dividing up the folders by each class allowed me to make use of Keras' ImageDataGenerator and avoid many of the complexities of cycling through each folder with os to read the images into a dataframe.

#### Notes

I used Google Colab to fit the image classifier. While far faster to train than on my local machine, the file I/O with Drive gets wonky and the runtime drops after ~15 minutes of inactivity.

#### Conclusions on v1

I am quite pleased at the first pass at this. My model was successfully able to detect the presence of an M1 Abrams tank in each of the four test images I passed it from various Iraqi militia social media accounts. More broadly, the model performs well on the testing data.

###### TensorBoard Graph showing loss on validation data over 100 epochs

<img width="1077" alt="Screen Shot 2019-04-21 at 9 35 50 PM" src="https://user-images.githubusercontent.com/31871105/56478449-7c438480-647d-11e9-9725-7c7c37cc3d6d.png">

###### TensorBoard Graph showing accuracy on validation data over 100 epochs

<img width="1071" alt="Screen Shot 2019-04-21 at 9 37 47 PM" src="https://user-images.githubusercontent.com/31871105/56478501-e1977580-647d-11e9-80fb-ac96bd8cebc6.png">


#### Next Steps

1. Further adjust layers in the CNN to see if I can further reduce false negatives.
2. Use YOLO object detection or Fast R-CNN to immediately detect and track each M1 Abrams tank in a given image.
3. Determine what other systems or equipment are of similar "high risk" and train models to detect them.
4. Use Django or Flask to build a GUI so that one can easily input their own images.
