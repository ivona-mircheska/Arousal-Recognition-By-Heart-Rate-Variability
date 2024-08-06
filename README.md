Understanding arousal, a fundamental emotion, is crucial for analyzing human responses to various stimuli. Determining arousal levels using heart rate variability (HRV) presents significant challenges, especially in a contemporary setting. This research explores two primary methods—classification and regression—to analyze arousal levels in participants wearing masks equipped with sensors that monitor facial muscle activity while exposed to different video materials.

Key Findings:

High prediction accuracy was difficult to achieve, particularly in a calm environment with minimal movement and ineffective video content.
Classification methods yielded more satisfactory results compared to regression approaches.
A deeper understanding of arousal could lead to advancements in science and medicine, aiding in diagnosing cardiovascular and mental health issues. By examining physiological responses such as blushing, pupil dilation, facial movements, and changes in breathing and heart rate, researchers can gain insights into human emotions.

HRV and ECG Signals
Heart rate variability (HRV), a measure of the variation in time between successive heartbeats, is commonly analyzed using electrocardiogram (ECG) signals. These signals capture the electrical activity of the heart and include various waveforms used to diagnose heart diseases. In this study, the mask's sensors collected HRV data from the frontalis and corrugator muscles to extract relevant features for machine learning analysis.

Main Challenges
A key challenge was accurately estimating arousal values due to data anomalies.

Subjects Recruitment, Experimental Protocol, and Attributes
Subjects Recruitment:

Participants: 30 healthy volunteers aged 16-23, mostly 21.
Health Criteria: No cardiovascular, psychological, or neurological conditions.
Awareness: Participants were informed about the study's purpose.
Experimental Protocol:

Procedure: Participants wore masks with sensors while viewing 20 videos (happy, sad, uncomfortable) in random order.
Data Collection: Participants rated their arousal from 1 to 9 for each video. Features were extracted every 30 seconds with a 10-second sliding window.
Features Collected: 38 HRV features, including:
Mean heart rate
Interbeat intervals
Standard deviation of NN intervals (SDNN)
Standard deviation of successive RR interval differences (SDRR)
Statistical Analysis and Visualization
Data Split: Participants were divided into training (20), validation (5), and test (5) sets.
Methods: Classification (three classes: low, medium, high) and regression (nine classes: scores 1-9) were employed.
Class Distribution: Most common class was low arousal; high arousal was least common.
Normalization methods (baseline and min-max) were used to address data discrepancies. Baseline normalization involved extracting features during a calming video session, while min-max normalization scaled values between 0 and 1.

Arousal Classification
Five algorithms were tested: Decision Tree, Random Forest, Support Vector Machine (SVM), AdaBoost, and Extreme Gradient Boosting (XGBoost). Evaluation metrics included accuracy and macro f-score:

No Normalization:
SVM: Accuracy 55%, f-score 32%
Baseline Normalization:
SVM: Accuracy 51%, AdaBoost: f-score 34%
Min-Max Normalization:
AdaBoost: Accuracy 45%, f-score 35%
Decision Tree with undersampling (Condensed Nearest Neighbors) showed the best performance: Accuracy 45%, f-score 36%.

Arousal Regression
Regression models underperformed compared to classification. Metrics used were Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² score:

No Normalization:
Best: Decision Tree Regressor (MAE=1.99, MSE=5.46, RMSE=2.34, R²=-0.00)
Baseline Normalization:
Best: AdaBoost Regressor (MAE=1.94, MSE=5.48, RMSE=2.34, R²=-0.00)
Min-Max Normalization:
Best: AdaBoost Regressor (MAE=2.17, MSE=6.83, RMSE=2.61, R²=-0.25)
R² scores were low, indicating regression was not effective for this problem.

Conclusion
Classification methods outperformed regression in this study. The best model was the Decision Tree with baseline normalization and undersampling, achieving the highest f-score (36%).

Future research should address limitations such as ineffective video content and explore dynamic environments to induce higher arousal. Additionally, individual differences in emotions, mental state, and mood need to be considered for more accurate arousal measurement.
