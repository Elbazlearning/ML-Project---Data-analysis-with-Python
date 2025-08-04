I think you had an interesting research question, but you've fundamental errors in how you have represented your problem.  As a result, there are numerous sources of data leakage:

- You have multiple rows for the same target value - when setting up a supervised ML problem, you need to have one row per observation of a target variable.

- Your biodiesel data is for the same year as corn production; biodiesel prices are going to be strongly correlated with production levels, so it's not surprising this variable is so strongly correlated. 

Whenever you see a model performing an explaining nearly all variance, you need to work extra hard to make sure that you do not have data leakage. 

15/20
