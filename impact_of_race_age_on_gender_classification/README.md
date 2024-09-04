# Investigating the Impact of Age and Race on Gender Classification Performance in Facial Recognition Systems using UTKFace

## Introduction

- Facial recognition systems are becoming increasingly used in various applications i.e, from security to personalized user experiences. 
- Despite their increased usage, the performance of these systems can vary significantly across different demographic groups, leading to potential biases. 
- In this project, it try to investigate the impact of age and race on the performance of gender classification models. 
- The main focus is on understanding how well these models perform across different age and race groups and identifying any biases that may exist.

## Objective

- The primary objective of this project is to evaluate the gender classification performance of various models across different age and race groups using the UTKFace dataset. 
- It aim to identify any significant differences in performance metrics that could indicate biases in the models' predictions.

## Methodology
To achieve our objective, we follow these steps:
    1. **Data Preparation:**
       - Use the UTKFace dataset, which contains images of faces labeled with age, gender, and race.
       - Preprocess the images and labels to create a structured dataset suitable for training and evaluation.

    2. **Model Training:**
       - Train several gender classification models including ResNet, CNN, Random Forest, and SVM.
       - Use these models to predict gender for each image in the test set.

    3. **Evaluation of Bias:**
       - Group the age labels into distinct categories: Child (0-12), Youth (13-25), Adult (26-40), Middle-aged (41-60), and Senior (61+).
       - Calculate performance metrics (e.g., accuracy, F1 score, Cohen's Kappa score) for each model across these age and race groups.
       - Analyze True Positives (TP), True Negatives (TN), False Positives (FP), and False Negatives (FN) to understand the models' performance in detail.

    4. **Visualization and Analysis:**
       - Use visualizations such as grouped bar plots to compare the performance of different models across age and race groups.
       - Identify patterns that indicate potential biases, focusing on any significant discrepancies in performance metrics.

## Data
- The project uses the UTKFace dataset, a large-scale dataset containing facial images labeled with age, gender, and race. 
- The dataset is crucial for this study because it provides a diverse range of demographic attributes, allowing us to perform a comprehensive analysis of age and race-related biases in gender classification models.
- **Dataset Link:** [UTKFace Dataset](https://www.kaggle.com/datasets/jangedoo/utkface-new/data)


## Importance
- Being able to understand and mitigate biases in facial recognition systems is critical to ensuring fairness and accuracy. Age and race-related biases in gender classification can lead to unfair treatment of certain demographic groups and diminish the overall effectiveness of these systems. 
- By identifying and addressing these biases, we can improve the reliability and inclusivity of facial recognition technologies.

## Conclusion
- Through this project, it aim to highlight the importance of evaluating model performance across different demographic groups. 
- The analysis will provide insights into the presence of age and race-related biases in gender classification models and suggest potential improvements to enhance their fairness and accuracy.


---

## 📊 Model Performance Comparison

| Model                    | Accuracy | F1 Score | Precision | Recall   | Kappa Score | Misclassification Count | Percentage Misclassification |
|--------------------------|----------|----------|-----------|----------|-------------|-------------------------|-----------------------------|
| **CNN Model**            | 0.5235   | 0.359767 | 0.274052  | 0.5235   | 0.000000    | 953                     | 0.4765                       |
| **ResNet Model**         | 0.6165   | 0.591265 | 0.636916  | 0.6165   | 0.214693    | 767                     | 0.3835                       |
| **Random Forest Classifier** | 0.7840   | 0.783781 | 0.783966  | 0.7840   | 0.566390    | 432                     | 0.2160                       |
| **SVM Classifier**       | 0.7960   | 0.796070 | 0.796269  | 0.7960   | 0.591443    | 408                     | 0.2040                       |

## 📝 Conclusion

The SVM Classifier achieved the highest performance in gender classification, with an accuracy of 0.7960 and the lowest misclassification rate of 0.2040. The Random Forest Classifier followed closely, demonstrating strong overall performance with a slightly higher misclassification rate. The ResNet Model showed moderate success, but the CNN Model struggled, with the lowest accuracy and highest misclassification rate.

## Bias Analysis in Terms of Age and Race
THis analysis tries to come up with the last part of this project with the aim to evaluate the potential bias of different models (ResNet, CNN, Random Forest, and SVM) in terms of age and race. The goal is to understand how each model performs across different demographic groups and to identify any discrepancies that might indicate bias.


### Methodology of analysis.
- The prediction results for test data was first grouped by age, categorising the ages into five distinct groups: Child (0-12), Youth (13-25), Adult (26-40), Middle-aged (41-60), and Very Old (61-100) and also by each of the race
- A computation of F1 Score and Cohen's Kappa Score for each model within specific demographic groups, such as race and age.
- The results were then consolidated into clear and understandable tables and a grouped bar plots were created to visualise the performance of each model across different demographic groups. 
- The following figures represent kappa cohen scores performance based on each of the groups above. More about f1 and also tables can be observed at the appendix. These present bias analysis results, focusing on the performance metrics of each model by race and age group. 

![image](https://github.com/user-attachments/assets/8e6ec5f4-320e-462b-bf73-580d4c608624)

- It is observed;
   - CNN model had very poor performance and it is ignored since the score is zero. It cannot be used for comparison.
   - The ResNet model might show bias towards certain age groups. It has the highest performance for all groups except children and the very old. This suggests ResNet might struggle with accurately detecting ages in the children and old people.
   - Random Forest model and SVM also seems to unfavour children as it has very low scores in them while having good performance in youths and middle aged.


The figure below showcases a barchart plot which shows how models performed across different races provided in the dataset;
![image](https://github.com/user-attachments/assets/bed03937-0e42-4f86-b4a0-db461c95e50d)


- As from the bar chart, the following can be observed;
  - The CNN model is also ignored in this case as it had zero performance which can't be compared to others.
  - Resnet model is seen to be favourable to all races except for Others where it had the least agreeability performance.
  - In Terms of SVM and Random forest, the agreeability scores were good except for Asian race,  which were seen to vary a lot from other races;


These results highlight potential biases in the models' performances, with certain models showing better or worse performance across different demographic groups. The Random Forest and SVM models generally perform better in both race and age group analyses, suggesting they may be less biassed compared to ResNet and CNN.


## ACCESS REPOSITORY
---
[Impact of Age and Race on Gender Classification Repository](https://github.com/Stephen-Kamau/Impact-of-Age-and-Race-on-Gender-Classification-Using-Facial-Data)

---