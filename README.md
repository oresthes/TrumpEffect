# TrumpEffect
Kaggle Project associated to Data Mining Principles Class at The University of Chicago

This study has been carried out and presented by *Orest Allickoli* and *Hussam Almuayad* as the final project in the Data Mining class at the MScA program at the University of Chicago, taught by Prof. Anil Chaturvedi.

The aim of this analysis is to try and predict populous tendencies in Europe.  
The dataset has been acquired from kaggle https://www.kaggle.com/daliaresearch/trump-effect  
The study has not been published on Kaggle because its engine was not capable of running this low intensity code from beginning to end uninterrupted.    
In our possession are two sets of data, one for the US and one for EU.  
The US data contains a question about the candidate elected in the Nov 2016 election whether that was Donald Trump, Hilary Clinton, another candidate or abstinence from voting.  
In the EU dataset the subset of the *GB* Great Britain referred to as UK_set (with name variations) contains a question about the 2016 EU referendum whether an individual voted to leave, stay or abstain from voting.  
The analysis is based on a number of assumption that individuals who voted for Donald Trump are similar or mimic those who voted for leaving EU.  
The study is carried out in 6 steps overall with the first 4 steps pertaining to data homogenization and cleaning and the last two steps pertaining to the actual analysis and results.  
Important Notes:   
1- There are three major sets throughout the analysis. The UK_set, US_set and EU_set (containing EU countries except the UK).   
2- all sets are subsetted so that only individuals who reported being residents are included in the study.  
3- In the US set individuals who voted for Hilary are lumped with individuals who voted "Other candidate" for two reasons:
  a- we only care if the vote is for a populist or not.    
b- this makes the number levels match the UK levels of the vote on the referendum. 
4- Variable selection: At step 4 we perform variable selection where we remove variables that 1) contain many **NA** values, 2) have different levels between the US_set and the EU_set or 3) that we thought are redundant.  This reduces the set from 68 variable to 44 and 48 (explained in item 5, next).    
5- At step 4 we chose to divided the EU subest into two groups to be analyzed separately. The first containing only the 5 largest countries (in terms of number of observations). Those are 'DE','FR','ES','PL','IT'. The second set contains all EU countries with more than 100 observations in the survey. **The analysis is carried out ONLY for the 5 large countries** however the datasets are processed and ready for anyone who wishes to carry out further analysis.     
It is important to understand the difference the difference between the sets with suffix **set_5c** and suffix **set_all**. The variables (columns, or questions) between those two sets are different. sets US_set_5c, UK_set_5c, and EU_set_5c contain 48 variables and are to be studied together, whereas sets US_set_all, UK_set_all and EU_set_all contain 44 variables are are to be studied together.   
The reason for this dichotomy is due the fact that many questions from the survey remain unanswered for many of the smaller countries and those are reported as **NAs**. This is not true for the larger countries which have answered those questions. Hence the 5 countries have 48 columns vs 44 with the larger EU_set_all.    
6- In step 5 **The analysis is carried out ONLY for the 5 large countries** using "US_set_5c", "UK_set_5c" and "EU_set_5c". Multinomial regression is estimated for the US and UK set and the predictive power of each set is assessed internally. The US model based on election is used to predict UK results of referendum and vice versa. Afterwards both the UK and US model are used to predict the populous tendencies in the 5 countries 'DE','FR','ES','PL','IT'. Details of model validation are included in the comments along with the code chunks.  
In addition in this step we split the votes who abstained from voting into two groups to add a level of granularity that shows whether a no-vote has the tendency to vote populist or non-populist. The results are displayed in the same proportion tables.   
7- In step 6 we carry out Classificataion tree models for the US set and the UK in an attempt to take a closer look at the factors that affected the vote selection.
