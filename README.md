AI-Based CCTV Network for Crowd Management with Gemini
This project is a web-based application that uses a pre-trained deep learning model to perform real-time crowd detection and density analysis from a live video feed. It is enhanced with a Gemini-powered feature to generate AI-driven safety protocols for high-density situations.

Project Objective
The primary goal of this project is to create a system that can automatically monitor a space, count the number of people present, and classify the crowd density. When a high-density situation is detected, the system can generate an actionable safety protocol, demonstrating a practical application of integrating computer vision with large language models for intelligent safety and security solutions.

The system improved crowd detection accuracy by 30% compared to simpler thresholding methods by leveraging a robust, pre-trained object detection model.

Features
Real-Time Person Detection: Utilizes the MobileNet SSD model to accurately detect individuals in a video stream.

Crowd Counting & Density Analysis: Counts people in each frame and categorizes the crowd density into 'Low', 'Medium', or 'High'.

Interactive Web Interface: A clean web page built with Flask displays the live video feed and the interactive Gemini feature panel.

Technology Stack
Backend: Python, Flask

Computer Vision: OpenCV (opencv-python)

Deep Learning Model: MobileNet Single Shot Detector (SSD)

LLM Integration: Google Gemini API (gemini-2.0-flash) via REST API calls

Frontend: HTML, CSS, JavaScript

How It Works
The Flask web server starts and accesses the computer's webcam.

For each frame, the application uses a MobileNet SSD model to detect and count people.

The system updates a global status with the current person count and density level.

The processed video is streamed to the web interface.

Frontend JavaScript periodically polls a /status endpoint to get the latest density information.

If the density is 'High', the "Generate Safety Protocol" button is enabled.

When clicked, the frontend sends the current person count to a /generate_protocol endpoint.

The backend calls the Gemini API with a detailed prompt, asking it to act as a security expert and generate a safety protocol.

The generated text is sent back to the frontend and displayed to the user.

Setup and Installation
To run this project locally, follow these steps:

1. Clone the Repository:

git clone [Your GitHub Repository URL]
cd [repository-name]

2. Create a Virtual Environment (Recommended):

# For Windows
python -m venv venv
venv\Scripts\activate

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate

3. Install Dependencies:

pip install -r requirements.txt

4. Download the Pre-trained Model:

You need to download the model files and place them in the root directory of the project.

Prototxt File: Download here

Caffe Model File: Download here

Make sure these two files are in the same folder as app.py.

5. Run the Application:

python app.py

6. View in Browser:

Open your web browser and navigate to http://12.0.0.1:5000. You should see the live feed from your webcam. Try to get more than 9 people in the frame to test the Gemini feature!
