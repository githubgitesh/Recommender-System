# MediPredict - Personalized Medical Recommendation System

[![GitHub language](https://img.shields.io/github/languages/top/yourusername/Recommender-System?style=flat-square)](https://github.com/yourusername/Recommender-System)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/yourusername/Recommender-System/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/yourusername/Recommender-System?style=flat-square)](https://github.com/yourusername/Recommender-System/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/yourusername/Recommender-System?style=flat-square)](https://github.com/yourusername/Recommender-System/network/members)
[![GitHub issues](https://img.shields.io/github/issues/yourusername/Recommender-System?style=flat-square)](https://github.com/yourusername/Recommender-System/issues)

## Description

MediPredict is an AI-powered health diagnosis system designed to provide personalized medical recommendations. By analyzing user-provided symptoms, it leverages machine learning to predict potential diseases and offers comprehensive, actionable advice including descriptions, precautions, medications, dietary suggestions, and recommended workouts to improve user well-being. This project aims to enhance user experience by delivering relevant health insights efficiently.

## Features

*   🩺 **AI-Powered Diagnosis**: Predicts potential diseases based on a list of user-provided symptoms using a trained Support Vector Classifier model.
*   📄 **Detailed Disease Information**: Provides comprehensive descriptions for each predicted disease.
*   ⚠️ **Actionable Precautions**: Offers practical steps and precautions to manage and prevent disease progression.
*   💊 **Medication Recommendations**: Suggests relevant medications for the identified health conditions.
*   🥗 **Personalized Diet Plans**: Recommends dietary adjustments to support recovery and health.
*   🏃 **Tailored Workout Regimens**: Proposes suitable physical activities to aid in health management.
*   🌐 **Intuitive Web Interface**: A user-friendly web application built with Flask and Bootstrap for easy interaction.

## Tech Stack

| Category           | Technology           |
| :----------------- | :------------------- |
| **Frontend**       | HTML5, CSS3, Bootstrap 5 |
| **Backend**        | Flask (Python)       |
| **Machine Learning** | Scikit-learn, Pandas, NumPy |
| **Model**          | Support Vector Classifier (SVC) |
| **Development**    | Jupyter Notebook     |

## Project Structure

```
.
├── Datasets/
│   ├── Symptom-severity.csv
│   ├── Training.csv
│   ├── description.csv
│   ├── diets.csv
│   ├── medications.csv
│   ├── precautions_df.csv
│   ├── symtoms_df.csv
│   └── workout_df.csv
├── model/
│   └── svc.pkl
├── static/
│   └── img.png
├── templates/
│   ├── about.html
│   ├── blog.html
│   ├── contact.html
│   ├── developer.html
│   └── index.html
├── .gitignore
├── cdac_project.ipynb
├── main.py
├── README.md
└── requirements.txt
```

## Getting Started

Follow these steps to get a local copy of the project up and running on your machine.

### Prerequisites

Ensure you have the following installed:

*   Python 3.8+
*   pip (Python package installer)
*   Git

### Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/yourusername/Recommender-System.git
    cd Recommender-System
    ```

2.  **Create a virtual environment:**

    ```bash
    python -m venv venv
    ```

3.  **Activate the virtual environment:**

    *   **Windows:**

        ```bash
        venv\Scripts\activate
        ```

    *   **macOS/Linux:**

        ```bash
        source venv/bin/activate
        ```

4.  **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

### Environment Setup

No additional environment variables are strictly required for basic operation, but the application runs in debug mode by default.

## Usage

1.  **Run the Flask application:**

    ```bash
    python main.py
    ```

2.  **Open your web browser** and navigate to:

    ```
    http://127.0.0.1:5000
    ```

3.  **Enter symptoms**: On the homepage, type your symptoms (e.g., "fever, headache, itching, fatigue") into the input field. Symptoms should be comma-separated.

4.  **Analyze Symptoms**: Click the "🔍 Analyze Symptoms" button to get your AI diagnosis, including the predicted disease, description, precautions, medications, diet, and workout recommendations. These results will be displayed in interactive modals.

## API Reference

The core logic is exposed through Flask routes and internal Python functions.

### Flask Routes

*   **`/`** (GET):
    *   Renders the main `index.html` page, which is the entry point for the symptom analysis.
*   **`/predict`** (POST):
    *   **Method**: `POST`
    *   **Description**: Receives user-submitted symptoms, predicts a disease, and returns comprehensive recommendations.
    *   **Parameters**:
        *   `symptoms` (form data, string): A comma-separated string of symptoms (e.g., "itching, skin_rash").
    *   **Returns**: Renders the `index.html` template with `predicted_disease`, `dis_des` (description), `my_precautions`, `medications`, `my_diet`, and `workout` data.
*   **`/about`** (GET):
    *   Renders the `about.html` page.
*   **`/blog`** (GET):
    *   Renders the `blog.html` page.
*   **`/developer`** (GET):
    *   Renders the `developer.html` page.
*   **`/contact`** (GET):
    *   Renders the `contact.html` page.

### Core Prediction Functions

*   `helper(dis: str) -> Tuple[str, List[str], List[str], List[str], List[str]]`
    *   **Description**: Retrieves detailed information (description, precautions, medications, diets, workouts) for a given disease from the loaded datasets.
    *   **Parameters**:
        *   `dis` (str): The name of the predicted disease.
    *   **Returns**: A tuple containing the disease description, a list of precautions, a list of medications, a list of recommended diets, and a list of workouts.

*   `get_predicted_value(patient_symptoms: List[str]) -> str`
    *   **Description**: Takes a list of symptoms, converts them into a numerical input vector, and uses the pre-trained SVC model to predict the most likely disease.
    *   **Parameters**:
        *   `patient_symptoms` (List[str]): A list of symptoms provided by the user.
    *   **Returns**: The predicted disease name as a string.

## Configuration

The Flask application runs with `debug=True` when executed directly via `python main.py`. This enables automatic reloader and a debugger, which is suitable for development but should be set to `False` for production environments.

```python
if __name__ == "__main__":
    app.run(debug=True) # Set debug=False for production
```

Dataset paths are hardcoded within `main.py` relative to the application's root. Ensure the `Datasets/` directory and its contents are correctly placed.

## Contributing

We welcome contributions to the MediPredict project! While formal contributing guidelines are currently under development, you can contribute by:

*   **Reporting Bugs**: Open an issue if you find any bugs.
*   **Suggesting Features**: Propose new features or enhancements.
*   **Submitting Pull Requests**: If you'd like to contribute code, please fork the repository and submit a pull request with your changes. Ensure your code adheres to basic Python best practices.

A big thank you to our top contributor:

*   [yadnyeshkolte](https://github.com/yadnyeshkolte) (2 commits)

## License

This project is licensed under the MIT License. See the `LICENSE` file (if available in the original repository) for details.

## Changelog / Recent Activity

*   **April 17, 2026**: Last significant update to the codebase.
*   **November 11, 2025**: Project initialized and development began.

## Known Issues / Roadmap

### Known Issues

Currently, there are no known open issues.

### Roadmap

Future enhancements and features planned for MediPredict include:

*   **Improved Model Accuracy**: Exploring more advanced machine learning models or ensemble techniques to enhance prediction accuracy.
*   **Voice Input Integration**: Adding a feature for users to input symptoms via voice.
*   **Expanded Dataset**: Continuously expanding the dataset with more diseases, symptoms, and comprehensive recommendations.
*   **User Authentication & History**: Implementing user accounts to allow for personalized symptom history tracking and more tailored recommendations over time.
*   **Mobile Responsiveness**: Further optimizing the UI for a seamless experience across various mobile devices.

## Community & Support

The project currently has a community health score of 28%. To foster a more robust and engaged community, we aim to establish formal contributing guidelines, a code of conduct, and issue/pull request templates in the future. In the meantime, feel free to open issues for bugs or feature requests, and we'll do our best to provide support.