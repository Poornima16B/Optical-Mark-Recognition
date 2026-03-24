# Optical Mark Recognition (OMR) using OpenCV 📷📝

This project is an Optical Mark Recognition (OMR) system built using Python and OpenCV. It automatically grades multiple-choice question (MCQ) bubble sheets by analyzing scanned images or camera feeds, extracting the marked answers, and computing the final score.

## 🚀 Features

- **Document Extraction:** Automatically detects the edges of the bubble sheet and applies a perspective transform (bird's-eye view) to isolate the testing area.
- **Bubble Detection:** Uses image processing techniques (Grayscale, Gaussian Blur, Canny Edge Detection, Thresholding) to find and isolate the bubbles.
- **Answer Evaluation:** Sorts the detected bubbles by region, identifies which bubbles are shaded (based on pixel density), and compares them against the correct answer key.
- **Visual Feedback:** Overlays visual feedback on the original image—highlighting correct answers in green, incorrect answers in red, and calculating the final grade percentage.

## 🛠️ Technologies Used

- **Language:** Python 3
- **Libraries/Dependencies:**
  - `OpenCV` (cv2) - For heavy lifting in image processing.
  - `NumPy` - For array and matrix operations required in image transformations.

## 📁 Project Structure

- [OMR_Main.py](cci:7://file:///c:/Users/poorn/Desktop/Optical%20Mark%20Recognition%20using%20OpenCV/OMR_Main.py:0:0-0:0): The main execution script. It loads the image, outlines the processing pipeline, evaluates the score, and displays the visual output.
- [utlis.py](cci:7://file:///c:/Users/poorn/Desktop/Optical%20Mark%20Recognition%20using%20OpenCV/utlis.py:0:0-0:0): Contains helper functions such as contour finding, rectifying points, applying perspective transforms, sorting bubbles, and overlaying text.
- [webCamFeed.py](cci:7://file:///c:/Users/poorn/Desktop/Optical%20Mark%20Recognition%20using%20OpenCV/webCamFeed.py:0:0-0:0): (Optional) Script for processing a live webcam video feed instead of static images.
- **Images/Assets (e.g., [1.jpg](cci:7://file:///c:/Users/poorn/Desktop/Optical%20Mark%20Recognition%20using%20OpenCV/1.jpg:0:0-0:0), [2.jpg](cci:7://file:///c:/Users/poorn/Desktop/Optical%20Mark%20Recognition%20using%20OpenCV/2.jpg:0:0-0:0)):** Sample test images used to demonstrate the OMR logic.

## 🏃‍♂️ How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Poornima16B/Optical-Mark-Recognition.git
   cd Optical-Mark-Recognition
2. **Install the required libraries:**
   ```bash
   pip install opencv-python numpy

3. **Run the main python script::**
   ```bash
   python OMR_Main.py

   


 How it Works underlying Image Processing
 
Preprocessing: The image is translated to grayscale and blurred. Canny Edge Detection runs to find prominent edges.
Contours: The code locates the largest rectangular contour corresponding to the MCQ paper.
Perspective Transform: It "warps" the image to a perfectly flat, top-down view centered on just the bubble choices.
Thresholding: Converts the warped image into black and white to easily distinguish shaded areas.
Grading: Separates the image into a grid of questions and options, counts non-zero pixels in each option boundary, and logs the highest value as the selected answer.

