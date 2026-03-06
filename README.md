# Automatic Short Answer Grading with ML and Data Augmentation

This is my final year project on improving automated short answer grading using data augmentation.

## Project Overview

Automated Short Answer Grading (ASAG) is a Natural Language Processing(NLP)-based system designed to automatically evaluate and assign scores to students' short written answers. The goal is to reduce the hardwork and work pressure that is involved in manual grading especially with the growing number of students each year while also ensuring a fair and consistent assessment. 
The project focuses on predicting human-like scores for student answers by learning patterns from previously graded responses. The system is evaluated by using traditional machine learning classifiers trained on textual features that are extracted from student responses.


## Dataset Description
The project uses an educational dataset containing student-written responses to assessment questions. Each answer has been manually graded by human evaluators, making the dataset suitable for supervised learning approaches.

Key Characteristics
- Student-written text-based responses
- Discrete score labels representing grading levels
- Double scoring, where two independent human evaluators assign scores
- Naturally imbalanced score distribution

This dataset reflects real-world academic assessment scenarios, making it appropriate for evaluating the performance of an ASAG system.

The dataset was split into:
- 80% Training Set
- 20% Testing Set


## Dealing with Class Imbalance

The original dataset exhibits a class imbalance problem, where certain score categories appear significantly more frequently than others.

Class imbalance can negatively affect machine learning models because:
- Models may become biased toward majority classes
- Minority score categories may be predicted poorly
- Overall evaluation metrics may become misleading

Addressing this imbalance is therefore an important step in improving model performance.

To cater for this, Data Augmentation was used to balance the dataset.


## Data Augmentation Using Large Language Models

Data augmentation was applied to the training set by generating paraphrased versions of existing student answers. A large language model (LLM) was given a prompt and it had to produce semantically equivalent paraphrases while preserving the original meaning and score label.

Moreover, data augmentation is also applied due to the limited size of existing datasets and with this process the size of a dataset can be expanded such that the model gets more variety in the training data, and it can handle the different ways in which students might respond. If models are trained on limited data, they often struggle to perform well on unknown samples.

Data Augmentation refers to a set of techniques that can be used to create new data by slightly modifying the data samples that we already have.

Multiple augmentation scales were explored during implementation process to analyse how increasing the size of the training data affected model performance. This allowed the study of both improvement trends and potential degradation caused by over-augmentation.


## Models Used

After balancing and augmenting the dataset, two supervised machine learning models were trained and evaluated:
- Logistic Regression (LR)
- Random Forest (RF)

These models were selected to compare how linear and ensemble-based classifiers perform on the ASAG task using TF-IDF textual features.

The models were evaluated on the held-out test set to measure their ability to predict scores for unseen student answers.
