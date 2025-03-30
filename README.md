# ARMS: AI-Powered Accident Detection & Emergency Response System

"Every Second Counts. Every Life Matters."

ARMS (Accident Recognition & Monitoring System) is an AI-powered solution designed to detect road accidents in real-time, assess severity, and trigger an automated emergency response. Originally designed for CCTV-based surveillance, this prototype processes uploaded video footage to demonstrate its capabilities.

## 📌 Overview
Accidents often go unreported or experience delayed responses, leading to critical injuries and fatalities. ARMS aims to bridge this gap by leveraging AI to detect accidents, analyze severity, and send automated alerts.

## Key Features
✔️ Accident Detection – AI-powered analysis using CNN & OpenCV

✔️ Severity Assessment – Insights from Gemini AI on injuries and impact

✔️ Automated Alerts – Twilio-powered SMS & voice calls for rapid emergency response

✔️ User Verification – Authorities can confirm or dismiss detected accidents

✔️ Incident History – Verified cases are stored in Firebase for tracking and analysis

## ⚙️ Tech Stack
🔹 Machine Learning – CNN, OpenCV

🔹 AI Model Integration – Gemini AI for accident insights

🔹 Cloud Services – Google Cloud Storage, Firebase (Realtime Database)

🔹 Backend – Flask

🔹 Frontend – HTML, CSS, JavaScript

🔹 Alert System – Twilio (SMS & Voice Calls)

## 🚀 How It Works
### 1.Video Processing

The system extracts one frame per second from an uploaded video.

### 2.Accident Detection

A CNN model analyzes each frame for accidents.

### 3.Top Frames Selection

The two frames with the highest confidence score are selected.

### 4.AI Analysis

• The frames are sent to Gemini AI for insights on:

•Possible injuries

•Severity level

•Types & number of vehicles involved

### 5.Emergency Response

Twilio sends an automated voice call & SMS with accident details.

### 6.User Verification & History

•Authorities can verify or dismiss the alert.

•Verified cases are stored in Firebase for future analysis.

### 7.Dashboard Display

The accident details, including location, insights, and video links, are displayed on a dashboard.


## 🛠 Setup & Installation
🔹 Prerequisites

### Ensure you have the following installed:

•Python 3.x

•Flask

•OpenCV

•TensorFlow/Keras

•Firebase Admin SDK

•Twilio API

## 🔹 Installation Steps
### 1️⃣ Open the Colab Notebook
•Manually open Google Colab and upload the .ipynb file.

### 2️⃣ Install Dependencies
Since Colab provides a pre-configured Python environment, just install the required libraries:
```
!pip install -r requirements.txt  
```
(If needed, manually install specific libraries inside the Colab notebook.)

### 3️⃣ Connect to Firebase
•Set up Firebase Realtime Database.

•Upload your service account JSON file to Colab.

•Load it in your notebook:
```
import firebase_admin
from firebase_admin import credentials

cred = credentials.Certificate("/content/YOUR_SERVICE_ACCOUNT.json")  
firebase_admin.initialize_app(cred, {"databaseURL": "YOUR_FIREBASE_DATABASE_URL"})
```
### 4️⃣ Configure Twilio for SMS Alerts
•Create a Twilio account & get SID, Auth Token, and Phone Number.

•Store them as environment variables in Colab:
```
import os

os.environ["TWILIO_ACCOUNT_SID"] = "your_sid"
os.environ["TWILIO_AUTH_TOKEN"] = "your_auth_token"
os.environ["TWILIO_PHONE_NUMBER"] = "your_twilio_number"
```
### 5️⃣ Upload & Run the Accident Detection Model
•Upload your video manually or use Google Drive:
```
from google.colab import drive
drive.mount('/content/drive')  
```
•Run the model to process frames and detect accidents.

### 6️⃣ Verify & Store Accident Data
•If an accident is detected, users can verify whether it's a false alarm or a real accident.

•Verified data is stored in Firebase for future reference.

### Future Enhancements
🔹 Real-Time Integration – Deploy on CCTV cameras for instant accident detection

🔹 Geolocation Tracking – Pinpoint accident locations for better emergency response

🔹 Automated Report Generation – Generate accident reports for legal & insurance purposes

🔹 Multi-Language Voice Alerts – Support for regional languages in Twilio calls

###  🤝 Contributors

Ashwina K N [@Ashwinakn]

Kishore Narayanan  S R [@KISHORENARAYANANSR]

### 📜 License

This project is open-source under the MIT License.
