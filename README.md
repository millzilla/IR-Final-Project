IR Final Project
================

- E-mail classification system for final Information Retrieval project.
- As a proof-of-concept design, we will choose the 4 categories corresponding to the types of emails used in the test set:
  - Social
  - Shopping
  - Spam
  - Other
- Each group will consist of (hopefully) at least 200-300 emails of each category to make the classifier as effective as possible.
- Each email will be associated with a unique number (its index in the output list, discussed below).
- Train and test two types of Naive Bayes classifiers on a collection of e-mails:
  - Multinomial (Mills)
  - Multivariate Bernoulli (Hougs)
  - Algorithms can be found on slides 42 and 43 here: https://www.cs.mtsu.edu/~cen/6600ir/private/lectures/lecture10-textcat-nbayes.pdf
  - note: the classifier code should work as a module/method that can be called from the validation code.
- Each classifier will provide a standard output: a list of classifications (an integer 1-4) corresponding to one of the classification groups. The index of an item in this list is the identifier for one of the documents (from above) in the training set.
- After building the two classifiers, they will each be tested/evaluated using the "Ten-fold Cross Validation" method:
  - for an overview, just google; it's not in the slides
  - the document set will be segmented into 10 distinct groups; alternating between each of the 10 groups, a single group will be used for testing the classifier trained with the other 9 groups (by calling the classifier's method with the other 9 groups merged as one).
    - For each of these iterations, the percentage of documents that were correctly classified will be remembered
    - After all 10 groups have been used to test, the percentages will be averaged to produce the overall effectiveness of the classifier
- I think the Rand Index value could be calculated as well
  - Found on slide 49 here: https://www.cs.mtsu.edu/~cen/6600ir/private/lectures/12-clustering-full.pdf
  - After all classifications are made, do it across all of the documents;
  - It's a pair-wise comparison/count followed by a single calculation.
- This way, each of us can do a Classifier and an Evaluator
