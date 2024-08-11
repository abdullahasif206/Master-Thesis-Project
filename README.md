# Data Evaluation of 3-axis Acceleromter and 3-axis Gyroscope on vehicle door | Scenerio Classification using Artificial Intelligence

## Introduction
This project involves classifying scenarios using data from a 3-axis accelerometer and 3-axis gyroscope mounted on a vehicle door. A hybrid CNN-LSTM model is employed to effectively capture both spatial and temporal patterns in the sensor data for accurate scenario classification.

## Proposed Architecture
![Project Architecture](CNN-LSTM-Proposed-Model.png)

## Technology Used
1. Programming Language - Python
2. MATLAB
3. Hardware - 6-Axis Motion Sensor
4. Vector CANoe

## Dataset Used
The dataset includes scenarios involving various vehicle door and window operations, such as automatic and manual opening/closing, engine start/stop, block detection, and environmental interactions like ball hitting and finger impulses. It also covers unique conditions like passenger damping, music playing, and window lifter actions, offering a comprehensive range of motion and interaction patterns for classification.

## Proposed Model
The proposed model architecture begins by taking inputs from two sensors: a 3-axis accelerometer and a 3-axis gyroscope. A Convolutional Neural Network (CNN) processes this data, with the first layer converting the single-channel input into 16 channels. The second layer maintains the 16-channel size, and the third convolutional layer expands it to 64 channels. Each convolutional layer uses a 3x3 kernel, stride of 1, and padding of 1 to preserve spatial dimensions, with the ReLU activation function applied to introduce non-linearity. The output from the convolutional layers is reshaped and permuted to match the input size of the subsequent Long Short-Term Memory (LSTM) layer, which has four bidirectional layers with a hidden size of 64. The LSTM's output is fed into the first fully connected layer (fc1), reducing the size to 128 and applying ReLU activation. The final classification is performed by the second fully connected layer (fc2), producing the model's output.

## Evaluation and Results

### Confusion Matrix
The provided confusion matrix visualizes the performance of a CNN-LSTM model, which achieves 95% accuracy on the test set. Each cell in the matrix represents the number of instances where the true label (on the y-axis) matches the predicted label (on the x-axis). Diagonal values indicate correct predictions, while off-diagonal values show misclassifications. The high accuracy suggests that the model is effectively capturing the patterns in the data, with most of the predictions aligning closely with the true labels, and only a few instances of misclassification. This performance reflects the model's strong ability to generalize to unseen data.

![Project Architecture](https://github.com/abdullahasif206/Master-Thesis-Project/blob/main/Evaluation%20and%20Results/Confusion%20Matrix%20CNN-LSTM.png)

### Classwise Accuracy
The bar chart illustrates the class-wise accuracy of a CNN-LSTM model across various activities, demonstrating how well the model performs for each specific scenario. The accuracy is close to 100% for several activities such as "S," "PD," and "NM," indicating that the model reliably identifies these cases. Other activities like "FIO" and "WLD" have slightly lower accuracy, suggesting that the model encounters more challenges in correctly classifying these instances. Overall, the chart reflects the model's high accuracy across most activities, though there are a few cases where performance is less consistent. This detailed breakdown highlights the model's strengths and areas where it may need further refinement.

![Project Architecture](https://github.com/abdullahasif206/Master-Thesis-Project/blob/main/Evaluation%20and%20Results/Classwise-Accuracy.png)

### Force Estimation
The table presents force estimations for various activities classified by the CNN-LSTM model. The results indicate that the model effectively identifies and provides accurate force estimates for the majority of activities. However, there is a notable misclassification where the "Finger Impulse Open" (FIO) activity, which involved opening a door at a 15° angle, was incorrectly categorized as "Music" (M). This specific misclassification had a maximum estimated force of 0.24 N, which was incorrectly classified as noise, despite the actual activity involving human interaction with a force of 0.26 N. Overall, the model successfully detected and provided precise force estimations for 16 out of 17 activities, but one activity did not yield the expected results. This highlights both the model's strengths and a particular area where further refinement is needed.

![Project Architecture](https://github.com/abdullahasif206/Master-Thesis-Project/blob/main/Evaluation%20and%20Results/Force%20Estimation.png)

## Conclusion
This thesis focuses on enhancing scenario classification and human interaction estimation using data from a 6-axis motion sensor, which includes preprocessing steps like normalization, 3D coordinate transformation, signal analysis, and filtering to optimize input quality for model training. A key aspect of the research involved transforming the sensor's coordinate system to align with the vehicle's coordinate system, ensuring consistent data collection. Various AI models, including Random Forest and deep learning architectures like CNN, LSTM-LSTM, CNN-GRU, and CNN-LSTM, were evaluated on their ability to classify spatial and temporal data, with the CNN-LSTM model showing superior performance in accuracy and F1-score. Additionally, the thesis explored force estimation from the accelerometer data, revealing that the CNN-LSTM model accurately classified and estimated human interaction in 16 out of 17 activities, outperforming other models. This work highlights the effectiveness of machine and deep learning techniques in improving user experience and safety through advanced scenario classification and force estimation.

## Future Work
Future work could focus on integrating the CNN-LSTM model into real-time automotive systems to enhance safety and responsiveness, with further exploration into its use in active vehicle control. Expanding the dataset and incorporating additional sensors like radar and infrared could improve accuracy and generalizability. Enhancing real-time data processing would increase efficiency, and tailoring the model to passenger behavior could improve user experience, potentially influencing car door design and safety regulations.


Link to Project GUI : https://github.com/abdullahasif206/Master-Thesis-Project/blob/main/GUI-CNN-RNN-Classifier.mp4





