# Skin Oiliness Detection API

This is a FastAPI-based web service for detecting skin types based on images. The API uses a pre-trained TensorFlow model to classify skin types into four categories: **Acne, Dry, Normal, and Oily**.

## Features
- FastAPI backend for handling image classification requests.
- Uses a TensorFlow model (`V 1.0.0.keras`) for skin type prediction.
- Supports image uploads via API requests.
- Returns the predicted skin type along with confidence percentage.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Thurunu/skin-oiliness-detection.git
   cd skin-oiliness-detection
   ```
2. Create and activate a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Ensure you have the trained model file `V 1.0.0.keras` in the project directory.

## API Endpoints

### 1. Health Check
**Endpoint:** `GET /ping`
- Returns: `"Server is running..."`

### 2. Skin Type Prediction
**Endpoint:** `POST /level`
- **Request:** Upload an image file (JPEG, PNG, etc.)
- **Response:**
  ```json
  {
    "Skin Type": "Oily",
    "Confidence": 95.3
  }
  ```

## Running the API
To start the FastAPI server, run:
```bash
uvicorn main:app --host localhost --port 8000
```

## Example Request
You can test the API using `curl` or a tool like Postman:
```bash
curl -X 'POST' \
  'http://localhost:8000/level' \
  -H 'accept: application/json' \
  -H 'Content-Type: multipart/form-data' \
  -F 'file=@path/to/your/image.jpg'
```

## Dependencies
- FastAPI
- TensorFlow
- OpenCV (cv2)
- Pillow (PIL)
- NumPy
- Uvicorn


