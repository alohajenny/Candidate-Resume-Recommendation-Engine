# The Ultimate Resume Screening Tool That Recruiters Should Know About
Using Natural Language Processing to recommend candidate resumes based on your job listing

## Context 

In 2014, Google had 7,000 job openings and with these job openings, the company also received 3 million resumes that year. There’s no doubt that hiring is labor-intensive, and the larger the candidate pool gets, the harder it is to sift through to find the most qualified candidates. As the company expands and grows, it can become inefficient and expensive as the recruiting team grows at the same speed as the company. How do we optimize this labor intensive process of drowning in these countless resumes?

## Objective
We can create a recommender system that recommends the best-matched resume based on the job description! 

## Approach
1. Data Collection 
    - The dataset was found on [Kaggle](https://www.kaggle.com/kandij/job-recommendation-datasets).
    - I chose to only include one feature, which is the concatenated text for every experience listed in the resume/applicant dataset. Resumes with incomplete job title/experience were removed to ensure there are enough text to be modeled later. 
    - I've also set aside the text data of job descriptions. 
2. Text Preprocessing
    - Resumes and job description are then pre-processed with the following:
        - stop words removal
        - part-of-speech tagging
        - lemmatized
        - alpha characters only
    - Since after pre-processing, resumes with short length got even shorter, i.e., less than 20 words. I've decided to remove resumes that are less than 23 words, which ended up with approximately 1,000 resumes. 
3. Topic Modeling with LDA
4. Recommendation System Based on Cosine Similarity

## Results
- We were able to extract a total of 8 topics: HR, Sales, Admin, Marketing, Customer Service, Business, Restaurant, Security, and Sales
- Each topic is mostly evenly distributed across the documents and the topics have terms that are unique to them, meaning that terms in the topic have little overlapping with other topics. 
- It’s still inevitable that topics have very few terms overlapping with each other, and that’s because people can have various levels of experience, i.e., going from being an admin to data scientist after 3 years. 

# Future Work
Given more time and the access to company data, I would love to do the following to improve the recommendation engine. 
- Obtain company data on job description, candidate resumes, and additional internal information, i.e., What job level is this role? Is this a People Manager role? 
- Work with Recruiters to apply supervised learning techniques, using screened-in resumes as an indicator that this resume is a good recommendation
- Work with Engineering to apply user feedback loop to continuously improve the recommendation engine

## Workflow
Follow the jupyter notebooks in the order below:
- 00 Download the dataset from [Kaggle](https://www.kaggle.com/kandij/job-recommendation-datasets)
- 01 Simple EDA.ipynb
- 02 Data Preprocessing.ipynb
- 03 Topic Modeling & Recommendation Engine.ipynb
