# -Grammar-Scoring-Engine-for-Voice-Samples
Overview
This project aims to develop a machine learning-based Grammar Scoring Engine that evaluates spoken English audio samples and assigns a continuous grammar score ranging from 0 to 5. The dataset consists of audio files (45–60 seconds long) and corresponding ground truth labels based on MOS Likert Grammar Scores. The model processes the audio files, extracts meaningful features, and predicts grammar scores with improved accuracy.
Problem Statement
Evaluating the grammatical accuracy of spoken English is crucial in applications such as language learning, automated assessments, and communication tools. Manual evaluation is time-consuming and subjective, making it essential to build an automated system that provides consistent and objective grammar scoring.
Dataset
	•	Audio Files: `.wav` files for training (`audios_train`) and testing (`audios_test`).
	•	CSV Files:
	•	`train.csv`: Contains filenames and corresponding MOS Likert Grammar Scores (ground truth).
	•	`test.csv`: Contains filenames for test samples.
	•	`sample_submission.csv`: Provides the required format for submission.
Approach
1. Data Preprocessing
	•	Extracted multiple features from audio files using the `librosa` library:
	  •	MFCCs: Captures frequency patterns in audio signals.
    •	Spectral Contrast: Highlights differences between spectral peaks and valleys.
	  •	Chroma Features: Represents pitch classes in audio signals.
  •	Combined these features into a single feature vector for each audio file.
	•	Normalized features using `StandardScaler` to ensure consistent input for the model.
2. Model Architecture
	•	Implemented a Random Forest Regressor for predicting grammar scores:
	  •	Random Forest was chosen due to its robustness on tabular data (extracted features).
	  •	Hyperparameters were optimized using grid search to improve performance.
3. Training and Validation
	•	Split the training data into training and validation sets (80:20 ratio).
	•	Optimized the model using Mean Absolute Error (MAE) as the evaluation metric.
4. Evaluation Metrics
The model was evaluated using the following metrics:
	•	Mean Absolute Error (MAE): Measures average prediction error.
	•	Root Mean Squared Error (RMSE): Captures error magnitude in original units.
	•	R² Score: Indicates how well predictions match actual values.
5. Prediction
	•	Predicted grammar scores for test samples using the trained Random Forest model.
	•	Saved results in the required CSV format (`submission.csv`).
Results
	•	Validation Metrics:
	•	MAE: 
	•	RMSE: 
	•	R² Score: 
	•	The model demonstrates improved performance in predicting grammar scores, with reduced error compared to initial attempts.
Conclusion
This Grammar Scoring Engine leverages advanced feature extraction techniques and a robust regression model to provide accurate grammar scores for spoken English. The use of Random Forest ensures interpretability and reliability, making it suitable for real-world applications such as language assessments and communication tools.
