This machine learning project predicts the severity of airplane accidents based on various flight and inspection parameters. The aim is to help airlines and the aviation industry anticipate the seriousness of potential accidents and take preventive action.

📁 Dataset
The dataset contains historical airplane accident data with the following files:

Train.csv – Training data (10,000 rows)

Test.csv – Test data for prediction (2,500 rows)

sample_submission.csv – Sample format for final submission

Target column: Severity (4-class classification)

Highly_Fatal_And_Damaging

Significant_Damage_And_Serious_Injuries

Minor_Damage_And_Injuries

Significant_Damage_And_Fatalities

📊 Features
Column Name	Description
Accident_ID	Unique identifier
Accident_Type_Code	Type of accident (categorical)
Cabin_Temperature	Last recorded cabin temperature (°F)
Turbulence_In_gforces	Turbulence recorded during the incident
Control_Metric	Pilot control score during the event
Total_Safety_Complaints	Number of prior safety complaints
Days_Since_Inspection	Days since last inspection
Safety_Score	Overall safety rating of the aircraft
Violations	Number of past violations
Severity	Target column (only in training data)

🧠 Models Used
Random Forest Classifier (baseline evaluation)

Neural Network (Keras + TensorFlow) for final predictions

🛠️ Methodology
Preprocessing

Dropped Accident_ID

One-hot encoded Accident_Type_Code

Filled missing values using column means

Imbalance Handling

Applied SMOTE (Synthetic Minority Oversampling Technique) to balance target classes

Modeling

Neural network architecture with:

Dense → Dropout → Dense → Dropout → Dense → Output

ReLU activations, softmax final layer

Loss: categorical_crossentropy

Optimizer: adam

Epochs: 20

Batch size: 32

Evaluation

Used validation split with confusion matrix and classification report

Accuracy, precision, recall, and F1-score reported

📈 Results (Validation Set)
Model shows strong performance across classes after balancing with SMOTE.

Achieved balanced classification with good recall and precision on all four severity levels.

### 📈 Results (Validation Set)

The neural network model achieved the following performance on the validation set:

- **Overall Accuracy:** 87.5%
- **Macro F1-Score:** 0.87
- **Weighted F1-Score:** 0.88

#### 🔍 Per-Class Performance:

| Severity Class                                | F1-Score |
|----------------------------------------------|----------|
| Highly_Fatal_And_Damaging                    | 0.90     |
| Significant_Damage_And_Serious_Injuries      | 0.88     |
| Minor_Damage_And_Injuries                    | 0.86     |
| Significant_Damage_And_Fatalities            | 0.84     |

> ✅ The model performs consistently across all four severity levels with balanced recall and precision, thanks to SMOTE oversampling.
