Automated Intelligent Attendance System Using Face Recognition

Overview
This project is an AI-powered attendance system designed to automate presence tracking in educational and corporate environments. By integrating real-time CCTV video processing with advanced deep learning models, the system offers a contactless, efficient alternative to manual roll-calls

Key Features

Real-time Face Detection & Recognition: Accurately identifies individuals from live video streams.
Anti-Proxy & Liveness Detection: Implements logic to prevent "proxy" attendance and spoofing attempts using photos.
Continuous Monitoring: Tracks individuals throughout a session to ensure they remain present.
Automated Logging: Automatically marks attendance with precise timestamps in a CSV or SQL backend.
Robust Performance: Designed to work under varying lighting conditions, difficult angles, and partial occlusions.

Tech Stack
Programming Language: Python
Libraries: OpenCV (Video Processing), Pandas (Data Logging), NumPy
Deep Learning Frameworks: PyTorch, dlib
Models:
RetinaFace: For high-accuracy face detection and landmarking.ArcFace / FaceNet: For generating unique 128 to 512-dimensional face embeddings.

System Architecture
The system follows a multi-stage pipeline:
Capture: Live video is captured via CCTV/Webcam (RTSP streams).
Pre-process: Frames are resized and normalized for optimal AI processing.
Detect: RetinaFace identifies face bounding boxes and landmarks.
Extract: ArcFace/FaceNet transforms faces into unique identity embeddings.
Recognize & Record: Identity is matched against a pre-registered database using Euclidean or Angular distance, and attendance is logged.

Getting Started
Prerequisites
Python 3.x

CUDA-enabled GPU (optional but recommended for real-time performance) 

Installation
Clone the repository.

Install required dependencies:

pip install opencv-python numpy pandas face_recognition

Configuration
Update the Config class in the source code to set your environment:
DB_PATH: Folder containing student images (e.g., student_database/).
TOLERANCE: Adjust to change recognition strictness (default: 0.6).
DEVICE: Set to "cuda" for GPU or "cpu".
Database Setup
Create a folder named student_database.
Add clear photos of each student, naming the files as student_name.jpg (e.g., amit.jpg).
Future Enhancements
Multi-camera re-identification for broader coverage.
Integration with ERP/LMS systems.
Deployment to Edge AI devices (Raspberry Pi, NVIDIA Jetson).
Author: Ashish Kumar 
Project Date: November 2025 
