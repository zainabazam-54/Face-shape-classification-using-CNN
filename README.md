Face Shape Classification Using CNN
Overview
This project uses a Convolutional Neural Network (CNN) built with TensorFlow/Keras to classify face images into five face-shape categories. The notebook loads a preprocessed image dataset, converts images to grayscale, resizes them to 32 × 32 pixels, and trains a CNN model to predict the category of each image.
Dataset
The notebook uses a preprocessed dataset stored in the Kaggle input directory:
- Training images: faceshape-processed/dataset/train
- Test images: faceshape-processed/dataset/test
The notebook reports 3,981 training images and 998 test images, belonging to five classes. The class names are loaded from the dataset's directory structure, so the exact category labels depend on the dataset folders.
The dataset is not included in this repository. Download or attach the dataset in Kaggle, or update the paths to match your local dataset location.

Technologies Used
- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Jupyter Notebook / Kaggle Notebook
Model Architecture
The notebook implements a CNN with the following layers:
1. Input: 32 × 32 grayscale image
2. Convolutional layer: 6 filters, 5 × 5 kernel, tanh activation
3. Average pooling: 2 × 2
4. Convolutional layer: 16 filters, 5 × 5 kernel, tanh activation
5. Average pooling: 2 × 2
6. Flatten layer
7. Dense layer: 120 units, tanh activation
8. Dense layer: 84 units, tanh activation
9. Output layer: 5 units, softmax activation
The model is compiled with the Adam optimizer and sparse categorical cross-entropy loss. Early stopping monitors validation loss with a patience of five epochs and restores the best weights.
Workflow
1. Load the training and test images from their folders.
2. Resize images to 32 × 32 and convert them to grayscale.
3. Inspect an example image and its class label.
4. Convert the image batches into NumPy arrays for inspection.
5. Normalize pixel values by dividing by 255.
6. Build and compile the CNN.
7. Train the model with early stopping.
8. Plot training and validation loss.
9. Evaluate the model and inspect a few predicted versus true labels.
Results
The saved notebook reports:
- Test accuracy: approximately 56.81%
- Test loss: approximately 1.0834
These are the results recorded in the notebook, not a guarantee of performance on other data.
Evaluation note: The notebook passes test_ds as the validation data during training and then evaluates the model on the same dataset. For a more reliable final performance estimate, create separate training, validation, and test sets, and reserve the test set for one final evaluation.
How to Run
1. Clone this repository
git clone <your-repository-url>
cd <your-repository-folder>
2. Install dependencies
pip install tensorflow numpy matplotlib jupyter
3. Set up the dataset
Download or attach the preprocessed face-shape dataset. Update the train_dir and test_dir variables in the notebook to point to the correct folders.
train_dir = "path/to/dataset/train"
test_dir = "path/to/dataset/test"
4. Run the notebook
Open face-shapae.ipynb in Jupyter Notebook or upload it to Kaggle, then run the cells in order.
Project Structure
.
├── face-shapae.ipynb
└── README.md
Possible Improvements
- Use separate training, validation, and test datasets.
- Experiment with image resolution and data augmentation.
- Compare the current CNN with transfer-learning models.
- Review per-class precision, recall, and a confusion matrix.
- Tune the model and evaluate it on images not used during training.
Disclaimer
This project is intended for educational purposes. Its predictions depend on the quality, balance, and coverage of the dataset and should not be treated as definitive face-shape assessments.
