# ISL Two-Way Sign Language Translator

The ISL Two-Way Sign Language Translator is a machine learning and computer vision-based application designed to improve communication between sign-language users and non-sign-language users.

The system provides two-way communication by supporting speech/text-to-sign conversion and gesture-to-text/speech conversion.

## Features

* Real-time hand gesture recognition
* Speech-to-text conversion
* Text-to-sign representation using images/GIFs
* Gesture-to-text conversion
* Text-to-speech output
* Hand landmark detection using MediaPipe
* Random Forest-based gesture classification
* Web-based user interface

## Technologies Used

* Python
* OpenCV
* MediaPipe
* Scikit-learn
* NumPy
* Flask
* SpeechRecognition
* HTML
* CSS
* Matplotlib
* Seaborn

## System Workflow

### Speech/Text to Sign

Speech Input → Speech Recognition → Text → Sign Image/GIF → Display

The user's speech is converted into text using speech recognition. The generated text is then mapped to corresponding predefined sign-language images or GIFs.

### Gesture to Text/Speech

Webcam → OpenCV → MediaPipe → Hand Landmarks → Random Forest → Predicted Gesture → Text/Speech

The webcam captures the user's hand gesture. MediaPipe detects the hand and extracts 21 hand landmarks. These landmark features are passed to the trained Random Forest classifier, which predicts the corresponding gesture.

## Machine Learning Model

The gesture recognition module uses a Random Forest classifier.

The landmark-based dataset is divided into:

* Training Data: 80%
* Testing Data: 20%

After training, the model is saved as `model.p` and loaded by the application for real-time gesture prediction.

## Model Performance

The model was evaluated on the test dataset using accuracy, precision, recall, F1-score, and a confusion matrix.

| Metric    | Result |
| --------- | -----: |
| Accuracy  | 99.47% |
| Precision |   1.00 |
| Recall    |   0.99 |
| F1-Score  |   0.99 |

The confusion matrix shows that most test samples were classified correctly, with very few misclassifications.

## Installation

Clone the repository:

```bash
git clone https://github.com/uzibytes/sign2text.git
cd sign2text
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Model Training

To train and evaluate the Random Forest model:

```bash
python train_classifier.py
```

The script loads the dataset, performs an 80:20 train-test split, trains the Random Forest classifier, evaluates the model, and saves the trained model.

## Running the Application

Run the Flask application:

```bash
python app.py
```

Open the following address in your browser:

```text
http://127.0.0.1:5000/
```

## Future Scope

The project can be further improved by increasing the size and diversity of the gesture dataset, adding more word-level and dynamic gestures, improving recognition under different environmental conditions, and extending the system to support a larger sign-language vocabulary.
