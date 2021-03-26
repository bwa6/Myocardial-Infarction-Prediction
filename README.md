# Myocardial-Infarction-Prediction
Predicting death of patients using data from three days of hospital visits

This project uses a dataset from the UCI Machine Learning Repository.  The dataset contains data collected from patients over three days at a hospital following an episode of myocardial infarction.  During graduate school, I studied cardiac tissue engineering to create stem cell-derived cardiac tissues that can be implanted on the heart following myocardial infarction, so naturally I took an interest in this dataset.  I was interested in my ability to understand the medical terminology represented by each feature in the dataset to properly clean the data of any missing values.  I researched the features to recognize relationships among them to properly impute missing data.

After cleaning the data, I used the dataset to practice supervised learning classifiers, including K-nearest neighbors, random forests, support vector machines, and adaboost.  I used grid searches with cross-validation to optimize the hyperparameters to get the most accurate fit. I generated ROC curves to determine the thresholds to optimize recall at the cost of false positives.  In the case of predicting death, it is particularly important to maximize recall so that we can identify as many patients at risk of dying as possible to allocate more hospital resources to saving their lives.  

After developing models with an inadequate recall, I decided to perform feature selection to eliminate features that do not contribute to predicting death.  Using backward selection, I eliminated several features that led to improvements in the AUC of the ROC curve.  I also eliminated a considerable number of features that neither helped nor hurt the AUC.  Ultimately, this led to identifying 16 features that are critical to predicting death.  For the most part, these features relate to the presence of 1) heart problems in the patient's medical history and 2) MI in the left ventricle according to the ECG.  

The benefit of feature selection is two-fold.  First, it improved the interpretability of the model by distinguishing important from irrelevant features.  Second, it improved the accuracy of the model by optimizing the AUC.  For instance, before feature selection, the SVM classifier had a recall of 71.7% and false positive rate of 20.2%.  After feature selection, the recall increased to 77.4% and the false positive rate decreased to 15.3%.

The optimized model was developed using Adaboost with a gridsearch and cross-validation to optimize hyperparameters following feature selection.  The recall was 79.2% and the false positive rate 12.5%.  Of course, the threshold could be further adjusted by considering the financial ramifications of allocating hospital resources to a greater percentage of patients who are actually false positives.

In conclusion, this project improved my skills in data wrangling and machine learning algorithms. I have only just begun my pursuit of data science as a career. I recently graduated with a Ph.D. in biomedical engineering and have taken a rather long break after graduation due to a surprising diagnosis with a brain tumor. I began the long road to recovery follwoing the surgery in December 2020. I have been rigorously and enthusiastically been exploring the field of data science since early February. This represents my second project to practice my new skills as I learn them.  This has been an exciting time despite a difficult recovery from  brain surgery!
