# MediPredict - Personalized Medical Recommendation System

MediPredict is an AI-powered health diagnosis tool designed to help users identify potential health conditions based on their symptoms. The system utilizes machine learning to predict diseases and provides actionable recommendations, including medications, precautions, diets, and workouts.

## Features

- **AI Diagnosis:** Predicts potential diseases from user-provided symptoms.
- **Comprehensive Recommendations:**
  - **Description:** Detailed information about the predicted disease.
  - **Precautions:** Steps to take to manage the condition.
  - **Medications:** Commonly prescribed medicines.
  - **Diet:** Nutritional advice tailored to the disease.
  - **Workout:** Recommended physical activities.
- **Interactive UI:** A modern, responsive web interface built with Flask and Bootstrap.

## Tech Stack

- **Frontend:** HTML5, CSS3, Bootstrap 5
- **Backend:** Flask (Python)
- **Machine Learning:** Scikit-learn, Pandas, NumPy
- **Model:** Support Vector Classifier (SVC)

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/Recommender-System.git
   cd Recommender-System
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment:**
   - **Windows:**
     ```bash
     venv\Scripts\activate
     ```
   - **macOS/Linux:**
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Run the Flask application:**
   ```bash
   python main.py
   ```

2. **Open your browser and navigate to:**
   ```
   http://127.0.0.1:5000
   ```

3. **Enter symptoms:** Type your symptoms (e.g., "itching, skin_rash, nodal_skin_eruptions") in the input field and click "Predict".

## Project Structure

- `main.py`: The main Flask application.
- `cdac_project.ipynb`: Jupyter notebook containing data analysis and model training.
- `Datasets/`: Directory containing CSV files for symptoms, diseases, and recommendations.
- `model/`: Directory containing the trained machine learning model (`svc.pkl`).
- `templates/`: HTML templates for the web interface.
- `static/`: Static assets like images.

## License

This project is licensed under the MIT License.
