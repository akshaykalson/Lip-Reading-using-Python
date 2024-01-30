
Lip Reading using Python
This repository contains code for a lip reading project implemented in Python. The project focuses on leveraging deep learning models, particularly a combination of Convolutional 3D (Conv3D) and Bidirectional Long Short-Term Memory (BiLSTM) layers, to analyze lip movements for enhanced speech recognition.

Setup
To run the code, make sure to install the required dependencies using the following command:

bash

pip install opencv-python matplotlib imageio gdown tensorflow
Data Loading
The project includes functions for loading lip reading data. The data is obtained from a provided Google Drive link, and video frames are extracted for further processing. Additionally, text alignments are loaded for training the model.

Model Architecture
The deep learning model is built using the TensorFlow framework. It consists of Conv3D layers for spatial feature extraction, followed by BiLSTM layers to capture temporal dependencies in lip movements. The model is trained using Connectionist Temporal Classification (CTC) loss, and an example callback function is provided to visualize predictions during training.

Training
The model is trained on lip reading data, and a learning rate scheduler is implemented to adjust the learning rate during training. Model weights are saved periodically using checkpoints. To train the model, uncomment the relevant code in the provided notebook.

Pre-trained Model
A pre-trained model is available for download from the provided Google Drive link. You can load the weights into the model using the following code:

python

url = 'https://drive.google.com/uc?id=1vWscXs4Vt0a_1IH1-ct2TCgXAZT-N3_Y'
output = 'checkpoints.zip'
gdown.download(url, output, quiet=False)
gdown.extractall('checkpoints.zip', 'models')

model.load_weights('models/checkpoint')
Inference
You can use the trained model to make predictions on new data. Examples of inference on test data and a single video file are provided in the notebook.

Feel free to explore and adapt the code for your lip reading applications. If you encounter any issues or have questions, please refer to the original notebook for additional details.
