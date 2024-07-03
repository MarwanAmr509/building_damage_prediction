# Building Damage Prediction Post-Earthquake

This project is an integrated system for predicting building damage post-earthquake using machine learning models. It focuses on three aspects: predicting damage grade, the number of floors, and the height of the building after an earthquake. The system employs a sequential flow where the output of each model serves as an input to the subsequent model.

## Overview

The prediction process involves the following steps:
1. **Damage Grade Prediction Model**: Takes user input data and predicts the damage grade of buildings post-earthquake.
2. **Floors Count Prediction Model**: Uses the damage grade along with the user input to predict the number of floors remaining after the earthquake.
3. **Height Prediction Model**: Uses the number of floors and user input to predict the building height post-earthquake.

## Tools and Technologies Used

- **Flask**: A micro web framework used to build the web application and serve the prediction models.
- **Pandas**: Used for data manipulation and preprocessing.
- **NumPy**: Used for numerical operations, such as handling and transforming prediction outputs.
- **Joblib**: Used for loading the pre-trained machine learning model pipelines.
- **Scikit-learn**: The machine learning library used to train and save the prediction models.
- **XGBoost**: A powerful machine learning algorithm used in the height prediction model.
- **HTML/CSS**: For rendering the web pages and displaying results in a tabular format.
- **Werkzeug**: A WSGI utility library used for handling file uploads securely.

## Functionality

### User Input Handling
The application accepts CSV file uploads containing building data.

### Data Preprocessing
Categorical and numerical columns are processed to handle missing values and ensure correct data types.

### Model Predictions
- **Damage Grade Prediction**: The damage grade is predicted first.
- **Floors Count Prediction**: This output, along with the user input, is used to predict the number of floors remaining post-earthquake.
- **Height Prediction**: The number of floors and user input are used to predict the building height post-earthquake.

### Result Display
The predictions are merged with the input data and displayed in an HTML table format, showing the first 10 rows for quick review.

### File Download
The full prediction results can be downloaded as a CSV file.

## Running the Application

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/building-damage-prediction.git
    cd building-damage-prediction
    ```

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Ensure the model pipelines are available in the correct paths:
    - `./damage_model_pipeline.joblib`
    - `./count_floors_logistic_regression_84_model.joblib`
    - `./height_prediction_xgboost_regressor_55_model.joblib`

4. Run the Flask application:
    ```bash
    python app.py
    ```

5. Open your web browser and navigate to `http://127.0.0.1:3001/`.

## Usage

1. Upload a CSV file containing the building data.
2. The system will process the data and generate predictions for damage grade, floors count, and building height post-earthquake.
3. The results will be displayed on the web page and can be downloaded as a CSV file.

## File Structure

- `app.py`: The main Flask application script.
- `requirements.txt`: List of required packages.
- `templates/`: Directory containing HTML templates.
  - `index.html`: The main upload page.
  - `result.html`: The result display page.
- `uploads/`: Directory where uploaded CSV files are saved.
- `results/`: Directory where prediction results are saved.
- `models/`: Directory containing the pre-trained model pipelines.
  - `damage_model_pipeline.joblib`: The damage grade prediction model.
  - `count_floors_logistic_regression_84_model.joblib`: The floors count prediction model.
  - `height_prediction_xgboost_regressor_55_model.joblib`: The height prediction model.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
