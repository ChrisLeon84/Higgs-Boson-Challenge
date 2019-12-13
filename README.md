# Higgs-Boson-Challenge
Kaggle competition to find Higgs boson

Full details can be found on Kaggle: https://www.kaggle.com/c/higgs-boson


## Goal
The goal was to be able to create a particle identifier that accurately classifies events as Higgs or background. 

## Background
The reaction sought was H to tau/anti-tau (which subseuently decays to leptons + hadrons + neutrinos). The specific metric used was called approximate median significance (AMS) and comes from assuming a Poisson distribution, getting a p value and turning the p-value into number of sigma for a Gaussian (e.g, 1.96 for p=0.05). There were 30 features given, some raw quantities and some 'derived'. Most were kinematic variables.    

The data given came from simulation. The training data consisted of 250,000 events, with information about whether the event was 
Higgs or background. The testing data consisted of 550,000 events and only disclosed features. The task was too classify the testing data to maximize AMS.

### Challenges
* Higgs mass similiar to Z boson (91 vs 125 GeV)
* Neutrinos not measured (no data from them) 
* Many missing values from existing features

## Methods
The competition was closed when I tried, but subsmissions were still possible. This was done for a statistics course in the Spring of 2018. To avoid cheating, I did not read 
the forum at the Kaggle page (allowed in the competition, although I considered it cheating for the class). I was new to machine learning then, so at the beginning I just used the scikit-learn library. 

My approach was:
* Use the simplest methods first, set it as baseline. If I can't don't better than this, something is wrong.
* Data exploration 
* Discard irrelevant features, come up with new relevant ones
* Test different algorithms and features
* Hyperparameter tuning

I was able to see gradual improvement, and got the best results with an ensemble of 5 machine learning algorithms (neural network, gradient boosted decision trees, random forest, KNN, SVMs) with majority voting. 
The hyperparameter tuning was definitely the most computationally expensive and time-consuming part of the process. Training of the individual algorithms could take a while too.

Later, after I presenting to the class, I read the forum for tips. Took suggestions for features I hadn't considered and saw that the
XGBoost library was being recommendeded. Using this, there was drastic improvement with my best submission ending in the top 13%. 
