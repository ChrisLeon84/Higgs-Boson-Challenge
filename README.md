# Higgs-Boson-Challenge
Kaggle competition to find Higgs boson

Competiton details can be found on Kaggle:
https://www.kaggle.com/c/higgs-boson

The competition was closed when I tried, but subsmissions were still possible. This was done for a statistics course. To avoid cheating, I did not read 
the forum at the Kaggle page (allowed in the competition, although I considered it cheating for the class).

I was new to machine learning then, so at beginning I just used the scikit learn library. 

My approach was:
* Use the simplest methods first, set it as baseline. If I can't don't better than this, something is wrong.
* Data exploration 
* Discard irrelevant features, come up with new relevant ones
* Test different algorithms and features
* Hyperparameter tuning

I was able to see gradual improvement, and got the best results with an ensemble of 5 machine learning methods with majority voting. 
The hyperparameter tuning was definitely the most computationally expensive and time-consuming part of the process. Training could take a while too.

Later, after I presenting to the class, I read the forum for tips. Took suggestions for features I hadn't considered and saw that the
XGBoost library was recommendeded. Using this there was drastic improvement, with my best submission in the top 11%. 
