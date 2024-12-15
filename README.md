# OCR Digits Classification Project

## Overview
This project is a Handwritten Digit Recognition system built using a Convolutional Neural Network (CNN). It is designed to classify digits (0-9) from digital images, making it ideal for Optical Character Recognition (OCR) tasks. The project includes model training, testing, and deployment using a Django web application, offering real-time predictions through an interactive user interface.

You can deploy app on server using  digitalocean follow this link https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu

---

## Dataset
The dataset consists of 885 grayscale images distributed across 10 classes:

| Digit | Number of Images |
|-------|------------------|
| 0     | 105              |
| 1     | 91               |
| 2     | 77               |
| 3     | 78               |
| 4     | 112              |
| 5     | 115              |
| 6     | 80               |
| 7     | 52               |
| 8     | 75               |
| 9     | 100              |

The images were preprocessed and resized to ensure consistent input dimensions for the model.

---

## Features
- **Deep Learning Model**: A CNN designed for accurate digit classification.
- **Web Application**: A Django-based user interface for uploading and processing images.
- **Real-Time Predictions**: Displays predicted digit and confidence probability for uploaded images.

---

## Installation and Setup

### Prerequisites
- Python 3.8 or higher (my version install Python 3.10.2)
- Virtual environment (recommended)

### Steps
1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate    # For Linux/Mac
   venv\Scripts\activate      # For Windows
   ```

3. Install the required dependencies:
   #pip3 freeze -l > requirments_docker.txt to save all depencency libs for your env
   ```bash
   pip3 install -r requirements.txt
   ```

5. Apply Django migrations:
   ```bash
   python manage.py migrate
   ```

6. Run the development server:
   ```bash
   python manage.py runserver
   ```

7. Access the application at `http://127.0.0.1:8000/` in your web browser.

---

## Dockerize Django App
You can run this project using Docker for easier deployment and environment management.
using Dockerfile and .dockerignore .
In this project not create database for just simple demo so we haven't to use Dockercompose 
to manage different environments.
Dockercompose is better when we manage database

### Steps to Dockerize the App

1. **Build the Docker Image:**
   ```bash
   docker build -t ocr-digits-classifier .
   ```

2. **Run the Docker Container:**
   ```bash
   docker run -d -p 8000:8000 ocr-digits-classifier
   ```

3. **Access the Application:**
   Open your browser and navigate to `http://127.0.0.1:8000`.

### Dockerfile Overview
The `Dockerfile` is configured to:
- Use a slim Python base image for smaller size.
- Install all dependencies from `requirements_docker.txt`.
- Expose port 8000 for the Django app.
- Run the app using Gunicorn for production readiness.
---
## Usage
1. Launch the Django web application.
2. Upload an image of a printed digit.
3. View the predicted digit and its probability on the results page.

---

## Model Architecture
The CNN consists of the following layers:
- Convolutional layers for feature extraction.
- MaxPooling layers to reduce spatial dimensions.
- Dropout layers to prevent overfitting.
- Fully connected layers for classification.

---

## Future Enhancements
- Expand the dataset to improve model accuracy.
- Add support for multi-digit recognition.
- Optimize the deployment for production environments.

---

## Acknowledgments
Special thanks to the open-source community for providing tools and resources to build this project.

