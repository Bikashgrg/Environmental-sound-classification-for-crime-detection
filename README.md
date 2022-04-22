# Environmental-sound-classification-for-crime-detection

The ANN and Random Forest model has been used in this project to classify the sound that may be used for crime scene investigations and can protect many individuals from criminal actions. The datasets on the given problem is provided by my professors Dr. Paul Fergus. Furthermore, a comparison of the two models has been done in order to assess how well this model performs.

Note: Because the size of the RF model was too large, I uploaded only the MLP model to the *save_model* folder. However, if you run the model using the above jupyter notebook, the RF model will be automatically saved to the *saved_model* folder in your workspace.

## The Data

The dataset contains around 8732 short audio recordings containing different sounds for creating an ML/DL model to detect crimes in the nearby region. UrbanSound8k (https://urbansounddataset.weebly.com/urbansound8k.html) is the dataset utilised here. An urban soundscape composed of 8732 tagged sound clips with a duration of less than or equal to 4 seconds in this dataset, which includes sounds such as air conditioners, automobile horns and jackhammers, as well as children playing and dogs barking. All the audio files are in WAV format. Below table shows the dataset classes, as well as the overall time of classes in seconds and the quantity of sound files that every class has:

![Data](https://user-images.githubusercontent.com/29011734/164766303-df9e05af-d18c-4f04-9179-465cb7aded2e.png)

I am going to use librosa with MFCC for feature extraction, which provides building blocks necessary to create music information retrieval systems. Librosa is a python package for music and audio analysis. It is commonly used for audio signal processing because of the given reasons:

1. It helps to converge the signal to mono.
2. It can represent an audio signal with respect to normalize pattern between -1 and 1 so that regular pattern is observed from all the audio.
3. It is able to see sample rate and by default it converts it into 22050 Hz. 

## Summary/Conclusion

Based on accuracy and evaluation section, it is clear that ANN outperforms RF in terms of accuracy. But, RF outperforms ANN in terms of training time. However, because the accuracy of ANN is so much higher, training time does not appear to be a significant issue. The benchmarks or the output of different parameters that I have tried for both models are shown below (ANN and RF).

### ANN model

![ANN](https://user-images.githubusercontent.com/29011734/164766765-e0b5906f-4913-498b-b991-d6ab6b159327.png)

### RF Model

![RF](https://user-images.githubusercontent.com/29011734/164766817-7e6ca115-f99a-4bf3-ab3f-eb5048ba541a.png)

According to the above benchmark, the MLP model performs the best with an accuracy of 92.73% when the number of epochs is 300, the batch size is 32, and the n mfcc is 80 in the scenario where the density of the first, second, and third layers is 300, 200, and 100, respectively. Similarly, in the RF model, the parameter with the best accuracy of 61.11% when n estimator or number of trees is 300, max depth, and max samples are set to their default values. It also concludes that neural networks outperform RF in terms of accuracy when the input dataset contains audio.

### Reasons for the selected model parameters

To determine the ideal parameters, I started with one parameter, such as the number of trees in RF, and gradually increased the number of trees to check if there was any gain in accuracy. Then, after choosing the optimum number of trees, I begin with another parameter starting with low values to determine which value helps to raise the accuracy, and so on. For training and testing split, I trained the model with several splits of training and testing data, such as 90/10, 70/30, and 95/5, however the 80/20 split performed better than the other splits.

I attempted and ran many various parameters, but only a few perimeters comparisons are presented in the comparison table or image above since the accuracy that other parameters provided when I used them was not good enough or better than the ones I selected. Also, the table would be excessively long as some of the parameters made accuracy poorer which wasn't worth it. However, I have highlighted a couple of the values where the performance was particularly bad, such as 37% or 49%, to demonstrate the variety of outcomes that I obtained with different parameters. 

## Thank you
