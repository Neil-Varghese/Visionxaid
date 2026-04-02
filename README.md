# VisionXaid

VisionXaid is an AI-powered retinal disease screening web application.
It provides:

- Fundus image upload and prediction
- Class probabilities for supported retinal conditions
- Grad-CAM heatmap for visual explainability
- Downloadable PDF report of prediction output

## Live Project

https://visionxaid.onrender.com/

## Project Screenshots

### Landing & Features
<p align="center">
  <img src="https://github.com/Neil-Varghese/Visionxaid/raw/main/src/assets/landing.png" width="45%" />
  <img src="https://github.com/Neil-Varghese/Visionxaid/raw/main/src/assets/features.png" width="45%" />
</p>

<br/>

### Prediction & Analysis
<p align="center">
  <img src="https://github.com/Neil-Varghese/Visionxaid/raw/main/src/assets/predict.png" width="45%" />
  <img src="https://github.com/Neil-Varghese/Visionxaid/raw/main/src/assets/nerdystuff.png" width="45%" />
</p>

<br/>

### UI Components
<p align="center">
  <img src="https://github.com/Neil-Varghese/Visionxaid/raw/main/src/assets/testimony.png" width="45%" />
  <img src="https://github.com/Neil-Varghese/Visionxaid/raw/main/src/assets/cta.png" width="45%" />
</p>

## Tech Stack

Frontend:
- React + Vite
- Tailwind CSS

Backend:
- FastAPI
- TensorFlow / Keras
- OpenCV, Pillow, NumPy
- ReportLab (PDF generation)

## Repository Structure

visionxaid/
- src/                 -> React frontend source
- backend/app/         -> FastAPI app code
- backend/models/      -> ML model file (v50.keras)
- backend/requirements.txt
- package.json

## Run Locally

## 1) Clone the Repository

Use your repository URL:

	git clone YOUR_REPO_URL_HERE
	cd VisionXaid

## 2) Frontend Setup (React + Vite)

From project root:

	npm install

Create a .env file in the project root:

	VITE_API_URL=http://localhost:8000

Start frontend:

	npm run dev

Frontend runs at:
- http://localhost:5173

## 3) Backend Setup (FastAPI)

From project root:

	cd backend

Create and activate a virtual environment.

Windows (PowerShell):

	python -m venv .venv
	.\.venv\Scripts\Activate.ps1

Install dependencies:

	pip install -r requirements.txt

Ensure the model exists at:
- backend/models/v50.keras

Optional environment variable (for CORS):

	ALLOWED_ORIGINS=http://localhost:5173

Run backend server:

	uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload

Backend runs at:
- http://localhost:8000

## 4) Verify Backend Health

Open:
- http://localhost:8000/health

Expected response includes model_loaded and status fields.

## 5) Use the App

1. Open frontend at http://localhost:5173
2. Upload a fundus image from the prediction page
3. Review predicted class, confidence scores, and Grad-CAM heatmap
4. Download PDF report if needed

## API Endpoints (Local)

- GET /               -> API info
- GET /health         -> Health status
- POST /predict       -> Image prediction
- POST /report        -> Generate PDF report

## Common Issues

1. Model not loaded:
- Check that backend/models/v50.keras exists.

2. CORS error in browser:
- Set ALLOWED_ORIGINS to include http://localhost:5173.

3. Frontend cannot reach backend:
- Verify VITE_API_URL in root .env is http://localhost:8000.
- Ensure backend server is running.

## Notes

- This is a clinical decision-support/research prototype.
- It is not a replacement for professional ophthalmic diagnosis.
