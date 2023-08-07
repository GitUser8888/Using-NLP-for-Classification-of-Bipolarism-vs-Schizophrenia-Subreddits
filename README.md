# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP

This project is done as part of the Data Science Immersive course in General Assembly, and was completed in a short time frame of only 2 weeks.

### Project Objectives:
 We are tasked in using Natural Language Processing (NLP) to build a model that classifies if a reddit post belongs to r/schizophrenia or r/bipolar.

### Background
To diagnose and assess mental health conditions, clinicians rely on:

**F2F interactions**
- Non-verbal cues like body and affect
- Other possible associated symptoms
- Physical state of the patient
- Family members to ask

**Direct diagnostic questioning**
- Questions that get straight to the point
- "How is your mood lately?"
- "Do you ever feel like your thoughts can be heard?"

### Challenges from the Emergence and Rise of Telemedicine
Increased accessibility and convenience, but at the cost of:
- Lack of non-verbal cues
- Limited rapport building
- Potential for misdiagnosis

Current diagnostic methods are also not perfect. Majority of mental health patients will remain undiagnosed, at about 50% of all schizophrenia patients, and about 70% of all bipolar patients
The primary healthcare system would hence greatly benefit from a preliminary alert filtering tool that is anonymous and community based.

**There is a need for better linguistic understanding of mental health conditions.**

---

### The Modeling Process
1. Scrape posts from r/schizophrenia and r/bipolar subreddits using PRAW.
2. Understand the data, and then work towards building the classification models. This process consists of:
    - Data Cleaning
    - Removing punctuations
    - Tokenizing
    - Removing stop words
    - Lemmatizing
    - EDA 
    - Data Visualization (Horizontal Bar chart & WordCloud)
    - Train-test split
    - Vectorizing
    - Grid Search for hyperparameters
    - Build different models to compare metrics

3. Evaluate models
    - Train score, test score
    - Precision, recall, and f1-score
    - Confusion matrix

---

### Data used:
We scraped our datasets from two subreddits, r/schizophrenia and r/bipolar. The dataset contains 3000 schizophrenia and bipolar posts. The raw data will undergo preprocessing steps before train-test split and modelling. Classification for bipolar and schizophrenia will be predicted using the trained classification model.

Information found in the raw datasets includes information suchs as the title, text.
The full information could be found in the data dictionary below.


---

### Data Dictionary:

<br>Each dataset from r/schizophrenia and r/bipolar contains the following: 



| Column | Description                                | Data Type             | Example                                          |
|--------|--------------------------------------------|-----------------------|--------------------------------------------------|
| Id     | A unique identifier for each record         | Numeric and/or alphanumeric | 142vtbk, 53xfmu, 149gdlq, ...                                     |
| Title  | The title or headline of the post           | Text/string         | "Breaking News: New Discovery in Science"        |
| Text   | The main body of the post      | Text/string         | "Scientists have recently made a groundbreaking discovery..." |
| Score  | Score of the reddit post      | Numeric (integer) | 8, 9, 65, ...            |
| Label  | Labelling of 0,1 corresponding to schizophrenia or bipolar respectively | Numeric (integer) | 0,1 |


### Model Summary:
|Count Vectorization Method|Model|Train Scores|Test scores
|:--|:--|:-:|:-:|
|**<font color = pink>Count Vectorizer</font>**|**<font color = pink>Naive Bayes Bernouli</font>**|**<font color = pink>0.8700</font>**|**<font color = pink>0.8101</font>**|
|Count Vectorizer|Naive Bayes Multinomial|0.8881|0.7904|
|Count Vectorizer|Logistic Regression|0.9914|0.7855|
|Count Vectorizer|Random Forest|0.9992|0.8372|
|Count Vectorizer|Adaptive Boosting|0.8548|0.7707|
|Count Vectorizer|Gradient Boosting|0.9227|0.8163|
|TF-IDF|Naive Bayes Bernouli|0.8939|0.7916|
|TF-IDF|Naive Bayes Multinomial|0.9029|0.7916|
|TF-IDF|Logistic Regression|0.9264|0.8015|
|TF-IDF|Random Forest|0.9992|0.8212|
|TF-IDF|Adaptive Boosting|0.8248|0.7867|
|TF-IDF|Gradient Boosting|0.8836|0.7953|



### Key takeaways from the project:
1. We tried out NLP as a way of converting and understanding mental health conditions
2. The best performing model that did not overfit is the Count Vectorizer Naive Bayes Bernouli model
3. This model can pick up text from posts from r/schizophrenia and r/bipolar, and distinguish between the two mental conditions with a certain accuracy
4. This can serve to assist clinicians in understanding how mental health can be diagnosed via non-contextual linguistic information.



---

### Future Works:
1. We can expand on this prototype model, and further train it to recognize a wider spectrum of mental health conditions, which to further aid clinicians as a supplementary tool, especially during teleconsultation.​
2. Possible further expansion can also incorporate chatbots that can analyze the conversation with patients to help doctors get insights of their condition before the appointment.
