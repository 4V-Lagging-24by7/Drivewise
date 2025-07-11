# 🚗Drivewise | Autonomous Self-Driving Cars
*A Computer Vision–based project leveraging Neural Networks*


## 🧠 Overview

This project builds an autonomous driving system using computer vision and deep learning. Leveraging the Udacity simulator, we collect and preprocess driving data to eliminate bias. The architecture and training methodology are inspired by Nvidia’s 2016 paper on end-to-end deep learning for self-driving cars.


## 📸 Data Collection

Training data is captured through the Udacity simulator, which replicates real-world driving conditions. As you manually drive the virtual car, the simulator records:

- Camera images
- Steering angles
- Throttle, brake, and speed

All data is saved into a CSV log file for further processing.

**Steps to collect data:**
1. Download the Udacity simulator executable.
2. Run the simulator and drive through various tracks to gather diverse driving scenarios.
3. The simulator automatically logs the data into the appropriate directory.


## 🧠 Model Training

We use an end-to-end learning approach, training a Convolutional Neural Network (CNN) to predict steering angles from input images. The model learns to associate raw visual input with driving actions. The trained model is saved in HDF5 format using Keras.


## 🕹️ Simulation & Real-Time Control

After training, the model is integrated back into the simulator to test autonomous driving capabilities. Initial tests revealed some overfitting to specific tracks, prompting further improvements.

**To enhance generalization, we implemented an edge detection–based control mechanism:**
- Real-time frames are captured from the simulator’s video feed.
- OpenCV applies Canny edge detection (developed by John F. Canny in 1986).
- Edge patterns are analyzed and converted into control signals using Python’s keyboard module.


## ⚙️ How to Run

1. Install all dependencies listed in `requirements.txt`.
2. Launch the Udacity simulator and run `drive.py` to establish communication via Flask + SocketIO.
3. Select a track in autonomous mode to watch the car drive itself using the trained model.
4. *(Optional)* Download Trackmania to test lane detection using edge-based logic.
5. Run the edge-detection script to capture, process, and steer in real-time.


## 🎥 Demo

Watch the demo video : https://youtu.be/oW5gA0JFwbM


## 🤝 Contributing

We welcome contributions! If you’d like to improve the model or suggest enhancements, feel free to open an issue or submit a pull request.
