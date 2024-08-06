# Optical Character Recognition with Flask and Google Generative AI

This repository contains a Flask application that performs Optical Character Recognition (OCR) on images and PDF files, and uses Google's Generative AI to process and extract details from the recognized text.

## Features

- Extract text from images using Tesseract OCR.
- Extract text from PDF files.
- Preprocess images for better OCR results using OpenCV.
- Use Google's Generative AI to process and extract details from the recognized text.
- Simple API to process files by providing a URL.

## Requirements

- Python 3.7 or higher
- Flask
- pytesseract
- Pillow
- PyPDF2
- OpenCV
- numpy
- requests
- google-generativeai

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ocr-flask-app.git
   cd ocr-flask-app
   ```

2. Create a virtual environment and activate it:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up your Google API key:
   ```bash
   export YOUR_GOOGLE_API_KEY="your_google_api_key"
   ```

## Usage

1. Run the Flask application:
   ```bash
   python app.py
   ```

2. Send a POST request to the `/process` endpoint with a JSON payload containing the URL of the file to process:
   ```json
   {
     "url": "https://example.com/path/to/your/file.pdf"
   }
   ```

## API Endpoints

### `/process`

- **Method**: POST
- **Description**: Processes the file provided in the URL and extracts text using OCR. The extracted text is then processed by Google's Generative AI to extract relevant details.
- **Request Body**:
  ```json
  {
    "url": "https://example.com/path/to/your/file"
  }
  ```
- **Response**:
  - Success: JSON object with extracted details.
  - Error: JSON object with an error message.

## Code Overview

### Dependencies

- **Flask**: A lightweight WSGI web application framework.
- **pytesseract**: Python-tesseract is an optical character recognition (OCR) tool for Python.
- **Pillow**: Python Imaging Library adds image processing capabilities to your Python interpreter.
- **PyPDF2**: A library that can read and write PDF files.
- **OpenCV**: An open-source computer vision and machine learning software library.
- **numpy**: A fundamental package for scientific computing with Python.
- **requests**: A simple, yet elegant HTTP library.
- **google-generativeai**: Client library for Google Generative AI.

### Main Components

- **Download File**: Downloads a file from a given URL.
- **Extract Text from PDF**: Uses PyPDF2 to extract text from PDF files.
- **OCR Preprocessing**: Functions to preprocess images for better OCR results using OpenCV.
- **Extract Text from Image**: Uses Tesseract OCR to extract text from images.
- **Process File**: Determines the file type (image or PDF) and extracts text accordingly.
- **Process Endpoint**: Flask route to handle file processing requests and use Google's Generative AI to extract details.

## Contributing

Feel free to submit issues or pull requests if you have suggestions for improvements or find any bugs.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

This README provides an overview of the OCR Flask application, including installation instructions, usage guidelines, and a description of the code components. For detailed code documentation, refer to the source code files.