# Emotion Detection Model

This project is a deep learning-based emotion detection system that classifies human emotions from images using a **Convolutional Neural Network (CNN)**. It is built using **TensorFlow, Keras, and Flask** for deployment.

---

## Features

- Train a **CNN** to classify emotions such as *angry, happy, neutral, sad, and surprised*
- Preprocess images using **data augmentation**
- Deploy the model with a **Flask web application**
- Accept user-uploaded images and predict emotions

---

## Installation

### **1. Clone the Repository**

```sh
git clone https://github.com/your-repo/emotion-detection.git
cd emotion-detection
```

### **2. Install Dependencies**

Ensure you have **Python 3.7+** installed. Then, install required dependencies:

```sh
pip install -r requirements.txt
```

If you don't have `tensorflow` installed, run:

```sh
pip install tensorflow
```

### **3. Dataset Preparation**

Ensure you have a dataset structured as:

```
dataset/
    train/
        angry/
        happy/
        neutral/
        sad/
        surprised/
    test/
        angry/
        happy/
        neutral/
        sad/
        surprised/
```

You can use **FER-2013** or similar facial expression datasets.

---

## Training the Model

Run the `train.py` script to train the CNN model:

```sh
python train.py
```

This will:

- Load the dataset using `ImageDataGenerator`
- Train a CNN model with **data augmentation**
- Save the trained model as `emotion_model.h5`

---

## Running the Flask App

1. Ensure the trained model (`emotion_model.h5`) is in the project directory.
2. Start the Flask application:

```sh
python app.py
```

3. Open your browser and go to `http://127.0.0.1:5000/` to access the web app.

---

## API Endpoint

### **POST /predict**

- Accepts an image file
- Returns the predicted emotion as JSON

**Example Request:**

```sh
curl -X POST -F "file=@image.jpg" http://127.0.0.1:5000/predict
```

**Example Response:**

```json
{
  "emotion": "happy",
  "file_path": "static/uploads/image.jpg"
}
```

---

## Future Improvements

- Improve accuracy with **transfer learning (ResNet, VGG16, etc.)**
- Deploy on **cloud services (AWS, GCP, Heroku)**
- Build a real-time **emotion detection web app** using WebRTC

---

## License

This project is open-source under the **MIT License**.

