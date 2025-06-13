# How-Advanced-Neuromarketing-Methods-Can-Improve-Consumer-Preference-Prediction

## Study Objective

The study aimed to compare traditional self-reported measures (valence, arousal, dominance) with advanced neuromarketing techniques—specifically, FFT-based EEG analysis—in predicting consumer liking of experiential (intangible) products, like music videos. Kindly check the 'Results.docx' file for details. The main questions addressed were:

### RQ1: Can EEG (via FFT analysis) outperform self-reported measures in predicting liking?

### RQ2: Does combining EEG with self-reports enhance prediction?

### RQ3: Are these findings consistent across two datasets (DEAP and AMIGO)?

## Datasets & Preprocessing

### 1. DEAP Dataset
Signals Used: 40 electrodes (32 EEG + 8 physiological channels).

Transformation: FFT into five frequency bands: Theta, Alpha, Low Beta, High Beta, Delta.

Features: 203 total (200 frequency-domain EEG + Valence, Arousal, Dominance).

Data Split: 75% train (468,480 samples), 25% test (156,160 samples).

### 2. AMIGO Dataset
Signals Used: 17 electrodes (14 Emotive EEG + 3 physiological channels).

Transformation: FFT into the same five frequency bands.

Features: 88 total (85 signal features + Valence, Arousal, Dominance).

Data Split: 75% train (188,160 samples), 25% test (62,720 samples).

## Models Evaluated
Sixteen models were tested, including:

Traditional ML: Gaussian Naive Bayes, Logistic Regression, Decision Tree, Random Forest, etc.

Boosting: XGBoost, LightGBM, CatBoost, AdaBoost, RUSBoost.

Neural Networks: ANN, CNN, LSTM, GRU, MLP.

Proposed Model: Customized Residual 1D CNN.

## Key Results
✅ For RQ1: EEG Outperforms Self-Reports

### DEAP Dataset:

Self-reported arousal: F1 = 0.52

Self-reported valence: F1 = 0.73

EEG (FFT only): F1 = 0.96 → +23% over valence, +44% over arousal

### AMIGO Dataset:

Self-reported arousal: F1 = 0.45

Self-reported valence: F1 = 0.72

EEG (FFT only): F1 = 0.96 → +24% over valence, +51% over arousal

### Conclusion:

EEG alone substantially outperformed individual self-report measures in both datasets.

✅ For RQ2: EEG + Self-Reports Further Improve Prediction
## DEAP Dataset:

V+A (self-reports): F1 = 0.72

EEG+V+A: F1 = 0.99 → +27%

EEG+V+A+D: F1 = 1.00 → Perfect prediction

## AMIGO Dataset:

V+A (self-reports): F1 = 0.77

EEG+V+A: F1 = 1.00 → +23% → Perfect prediction

EEG+V+A+D: F1 = 1.00 → Perfect prediction

### Conclusion: 

Adding EEG to even the best self-report combinations (valence + arousal + dominance) provided significant gains in prediction accuracy.

✅ For RQ3: Generalizability Across Datasets
Consistency in results was confirmed using both DEAP and AMIGO datasets.

The proposed CNN model reached F1 scores of 0.96 (DEAP) and 0.98 (AMIGO), outperforming 16 traditional ML/DL models.

Best results across all performance metrics (Precision, Sensitivity, Specificity) were achieved when EEG+self-reports+physiological signals were combined.

### Performance Summary:
Model/Input Type	F1 Score (DEAP)	F1 Score (AMIGO)
Self-report (V+A)	0.72	0.77
EEG only	0.96	0.96
EEG + Self-report (V+A)	0.99	1.00
EEG + Self-report (V+A+D)	1.00	1.00
Proposed CNN (full EEG model)	0.96	0.98

## Other Findings

Precision Gains: Adding EEG to arousal or valence increased precision by up to 27–49%.

Recall Gains: Particularly striking improvements in recall for high-arousal classes (Class 1), where EEG corrected poor performance from self-reports.

Model Efficiency: The proposed CNN model had ~1 million parameters and low memory requirements (3.83MB to 4.70MB), showing good efficiency.

## Discussion & Implications
The study highlights the limitations of self-reported measures, especially for subjective, emotional experiences.

Neuromarketing with EEG (especially using FFT + CNN) is not only more accurate but also offers real-time, scalable, and reliable alternatives.

Results suggest that EEG-based neuromarketing techniques should become standard practice for studying experiential products.

## Limitations & Future Work
Results were derived from two datasets; generalizability to live subjects and other EEG datasets (e.g., SEED, DREAMER) should be explored.

Future studies can apply the method to other product types and emotional outcomes (e.g., fear, calmness).

The study emphasizes the need to integrate neuromarketing analytics with AI for both research and commercial applications.

**The codes are private.**
