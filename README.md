This is my final year project on improving automated short answer grading using data augmentation.

**Project Overview** 📖

Automated Short Answer Grading (ASAG) is a Natural Language Processing(NLP)-based system designed to automatically evaluate and assign scores to students' short written answers. The goal is to reduce the hardwork and work pressure that is involved in manual grading especially with the growing number of students each year while also ensuring a fair and consistent assessment. 
The project focuses on predicting human-like scores for student answers by learning patterns from previously graded responses. The system is evaluated by using traditional machine learning classifiers trained on textual features that are extracted from student responses.


**Dataset Description** 📚

This project uses an educational dataset containing student-written answers to assessment questions. Each answer has been manually graded by human evaluators which makes it suitable for supervised learning.

Key Characteristics:
- Text-based responses written by students
- Discrete score labels representing grading levels
- Double-scored answers, where two independent human scores are available
- Naturally imbalanced distribution, with certain scores appearing more frequently than others.
This dataset reflects realistic academic assessment settings which makes it well suited for evaluating an ASAG system. It was split into training and testing sets using 80/20 ratio.


**Class Imbalance** ⚖️

As mentionned before, the original dataset has an imbalanced distribution across score categories, which is common in real educational assessment data. Student answers are not evenly distributed across all possible scores, resulting in certain score classes having significantly more samples than others. This imbalance presents a challenge for supervised learning models, as classifiers may become biased toward majority score classes and underperform on the rarer scores.


**Data Augmentation Using Large Language Models** 🖥️

To mitigate the effects of class imbalance, data augmentation was applied to the training set by generating paraphrased versions of existing student answers. A large language model (LLM) was given a prompt and it had to produce semantically equivalent paraphrases while preserving the original meaning and score label.

Moreover, data augmentation is also applied due to the limited size of existing datasets and with this process the size of a dataset can be expanded such that the model gets more variety in the training data, and it can handle the different ways in which students might respond. If models are trained on limited data, they often struggle to perform well on unknown samples.
Data Augmentation refers to a set of techniques that can be used to create new data by slightly modifying the data samples that we already have.

Multiple augmentation scales were explored during implementation process to analyse how increasing the size of the training data affected model performance. This allowed the study of both improvement trends and potential degradation caused by over-augmentation.


**Models Used** ⚙️

After balancing and augmenting the dataset, two supervised machine learning models were trained on these datasets to evaluate and compare their performance later.
