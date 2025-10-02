# Face Detection with Python

This project provides a simple implementation of face detection using Python and OpenCV.

## Key Features & Benefits

*   **Real-time Face Detection:** Detect faces in real-time using a webcam.
*   **Easy to Use:** Simple and straightforward code for easy understanding and modification.
*   **OpenCV Integration:** Leverages the power of OpenCV for efficient image processing.

## Prerequisites & Dependencies

Before running this project, ensure you have the following installed:

*   **Python:** (Version 3.6 or higher recommended)
*   **OpenCV (cv2):**  Install using pip: `pip install opencv-python`

## Installation & Setup Instructions

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/muhammadalief19/face-detection-python.git
    cd face-detection-python
    ```

2.  **Install the required dependencies:**

    ```bash
    pip install opencv-python
    ```

3.  **Download `face_rev.xml`:**
    *   This file should be included in the repository. If not, it can be found and obtained from OpenCV's pre-trained classifiers available online. Commonly, it is part of the Haar cascades collection.  Search for `haarcascade_frontalface_default.xml`. Place it in the same directory as `main.py`.

## Usage Examples

1.  **Run the `main.py` script:**

    ```bash
    python main.py
    ```

    This will open a window displaying your webcam feed with bounding boxes around detected faces.

2.  **Understanding the Code:**

    The `main.py` script utilizes OpenCV's `CascadeClassifier` to detect faces.  Here's a breakdown:

    *   **`face_rev = cv2.CascadeClassifier("face_rev.xml")`:**  Loads the pre-trained Haar cascade classifier for frontal face detection.  Ensure "face_rev.xml" (or the downloaded haarcascade file) is in the same directory.
    *   **`camera = cv2.VideoCapture(0)`:** Initializes the webcam. `0` typically represents the default camera.
    *   **`face_detection(frame)`:** Converts the frame to grayscale and uses `detectMultiScale` to find faces.
    *   **`drawer_box(frame)`:** Draws rectangles around the detected faces.
    *   **`close_window()`:** Releases the camera and closes all OpenCV windows.

## Configuration Options

*   **Camera Index:**  You can change the camera index in `cv2.VideoCapture(0)` if you have multiple cameras. For example, `cv2.VideoCapture(1)` would use the second camera.
*   **Scale Factor:**  The `scaleFactor` in `face_rev.detectMultiScale(optimized_frame, scaleFactor=1.1)` controls how much the image size is reduced at each image scale.  Smaller values increase accuracy but also increase processing time.  Experiment with values like `1.05`, `1.1`, or `1.2`.
*   **Rectangle Color:**  Modify the color of the bounding box in `cv2.rectangle(frame, (x, y), (x + w, y + h), (255, 0, 0), 4)`.  The `(255, 0, 0)` represents blue in BGR format.  Change this to other BGR color values.
*   **Haar Cascade File:** Replace `face_rev.xml` with other Haar cascade files to detect different objects (e.g., eyes, smiles).

## Contributing Guidelines

Contributions are welcome! Here are the guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Make your changes and commit them with descriptive messages.
4.  Submit a pull request with a clear explanation of your changes.

## License Information

This project is licensed under the MIT License - see the `LICENSE` file for details.

## Acknowledgments

*   This project utilizes the OpenCV library.
*   The Haar cascade classifier is based on the work of Paul Viola and Michael Jones.