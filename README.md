# OCR and Text Detection

This project provides a complete pipeline for detecting, recognizing, and evaluating text in images. It uses the **EAST (Efficient and Accurate Scene Text)** deep learning model for high-accuracy text detection and the **Tesseract OCR engine** for recognizing the detected text.

The system is designed to process images, draw bounding boxes around text, extract the text content, and evaluate the model's performance using standard computer vision metrics.

## Key Features

-   **Text Detection**: Implements the pre-trained EAST model to locate text in images, even in complex scenes.
-   **Text Recognition (OCR)**: Integrates the Tesseract OCR engine to convert the pixels of detected text into machine-readable strings.
-   **Data Processing**: Includes scripts for batch processing of image files and utilities for handling different data annotation formats.
-   **Performance Evaluation**: Provides code to measure the accuracy of the text detection model using **Precision, Recall, and F1-Score**, and visualizes the results.

## How It Works

The project follows a two-stage process:

1.  **Detection**: The EAST model, a deep learning-based text detector, analyzes an input image and outputs the coordinates of bounding boxes around any text it finds.
2.  **Recognition**: The region of the image within each bounding box is then passed to the Tesseract OCR engine, which recognizes the characters and returns them as a string.

## Requirements

Before running the project, you need to install the necessary libraries and dependencies.

-   **Tesseract OCR Engine**:
    ```bash
    sudo apt update
    sudo apt install tesseract-ocr
    ```
-   **Python Libraries**:
    ```bash
    pip install opencv-python pytesseract scikit-learn
    ```

You will also need the pre-trained EAST model file: `frozen_east_text_detection.pb`.

## Installation and Setup

1.  **Clone the Repository**:
    ```bash
    git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
    cd your-repository-name
    ```

2.  **Download the EAST Model**:
    Download the `frozen_east_text_detection.pb` file from the link below and place it in the root directory of the project.
    [**Download Pre-trained EAST Model**](https://drive.google.com/drive/u/0/folders/1qeCwZqcKE8vYObVS43J7McDd-nCFHoDw)

3.  **Organize Your Data**:
    Create a directory (e.g., `images/`) in the project folder and place all the images you want to process inside it.

## How to Use

To run the text detection and recognition script, execute the `NEW EAST.ipynb` notebook or run the core Python script.

Make sure to update the `image_folder_path` variable in the script to point to the directory containing your images.

```python
# Specify the path to your folder containing images
image_folder_path = 'images/'

# List all files in the directory
image_files = [f for f in os.listdir(image_folder_path) if f.endswith('.jpg')]

# Process each image
for image_file in image_files:
    image_path = os.path.join(image_folder_path, image_file)
    print(f"✅ Processing: {image_path}")
    # This function should contain your detection and OCR logic
    detect_and_ocr(image_path)
    print("-" * 20)
