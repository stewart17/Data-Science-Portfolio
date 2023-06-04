# CNN - Covid19 X-Ray Prediction

With the national emergency of the Covid-19 pandemic officially over, funding has been less than certain when it comes to subsidizing Covid-19 tests. Reliable and affordable testing has become much less prevalent in recent months. 
As such, there is a need for other diagnosing tools outside of PCR and antigen tests to accurately diagnose the presence of Covid-19. One possible avenue for such diagnostic tools is X-Rays and CT scans. 
These tests are already used to detect the presence of other respiratory medical issues such as pneumonia, lung inflammation, abscesses and enlarged lymph nodes. Given that Covid-19 is itself a respiratory infection and is known to attack cells in the lungs, 
it may be possible to train a model to detect whether Covid-19 is present in those lungs. Not only would such a test be another option for testing that doctors can use to diagnose a patient, but it could also prove to be a useful avenue towards research. 
If a model can detect Covid-19 accurately, one could investigate exactly what kind of effect Covid-19 has on the lungs/respiratory tract which in turn could provide crucial information towards understanding the long-term impacts that Covid-19 has on the body.

## The Data

The data used in this project comes from Kaggle (Rahman 2020). A team of researchers compiled a database of Chest X-Ray images for Covid-19 positive cases, normal images, and viral pneumonia cases.

## The Analysis

The analysis is broken into two parts. In the first part, I built a binary image classification model to predict whether an X-Ray image is one with Covid-19 present or a normal image. The second part of the analysis added Viral Pneumonia images, to see how adding a third class affected the model’s ability to predict Covid-19.
In both cases a Convolutional Neural Network (CNN) was used, and they were evaluated based on accuracy and cross entropy loss (more specifically for the multi-class classifier a categorical cross entropy metric weas used).
For the binary classification model, the best model had three convolutional layers, three pooling layers, 3 dense layers, and 2 dropout layers applied between the dense layers. After 15 epochs, it had an accuracy of 99.6%, a validation accuracy of 96.81%, a loss of 1% and validation loss of 18.5%. Below one can see the accuracy and loss plots for the model.
