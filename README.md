# parking_space_detector

This project implements a Smart Parking System with two functionalities:

1. **Parking Space Selection (parking_space_picker.py):**
    * This script allows you to visually define parking space locations in an image.
    * It uses OpenCV for image processing and pickle for data persistence.
    * Clicking the left mouse button adds a new parking space location at the clicked point.
    * Clicking the right mouse button on an existing parking space removes it.
    * The script saves the defined parking space locations (`posList`) to a file named `CarParkPos`.

2. **Real-time Parking Availability Display (main.py & front.py):**
    * This application displays the real-time availability of parking spaces in a pre-recorded video (`carPark.mp4`).
    * It utilizes OpenCV for video processing, cvzone for drawing utilities, NumPy for image manipulation, and pickle for loading saved parking space locations.
    * The application loads the saved parking space locations from `CarParkPos`.
    * It processes each frame of the video and analyzes the parking space regions based on the saved locations.
    * A threshold for pixel intensity is used to determine if a space is occupied (darker) or free (lighter).
    * The application displays a rectangle around each parking space and indicates its availability status (free or occupied) on the video frame.
    * It also shows a summary of the total parking spaces and the number of free spaces.

# **GUI Interface (front.py):**
* This script (although not provided completely) seems to handle the graphical user interface (GUI) aspect of the system using the Tkinter library.
* It likely creates a window displaying an image as the background and buttons for starting the parking camera and exiting the application.

# **Running the System:**

## **Prerequisites:**

* Ensure you have the necessary libraries installed: OpenCV (`pip install opencv-python`), NumPy (`pip install numpy`), cvzone (`pip install cvzone`), pickle (`usually included in Python`), tkinter (`usually included in Python`).
* Make sure you have the following files in the same directory:
    * `carPark.mp4`: The video file containing the parking scene.
    * `carParkImg.png`: The image used for defining parking space locations (used in `parking_space_picker.py`).
    * `CarParkPos` (optional): This file will be created after running `parking_space_picker.py`.

## **Steps:**

1. **Define Parking Spaces:**
    * Run `parking_space_picker.py`.
    * Open the image of your parking area in the displayed window.
    * Click the left mouse button at each parking space location to define them.
    * Click the right mouse button on any incorrectly placed parking space to remove it.
    * Close the window (press 'q') to save the defined parking spaces to `CarParkPos`.

2. **Run the Parking Availability Display:**
    * Run `main.py`.
    * The application will start processing the video and displaying the parking availability on each frame.
    * You can close the application window (press 'q') to stop.
