# Text-as-Data Coursework 
Download this report in [PDF](https://github.com/fferegrino/tad-discourse-classification/releases/download/1.0/Coursework.pdf) or [DOCX](https://github.com/fferegrino/tad-discourse-classification/releases/download/1.0/Coursework.docx)

## Q1. Experimenting with Thread Subreddit Classification

After running several experiments with a combination of text vectorizers and classifiers, the values summarised in Table 1 were found. To my surprise, the difference between any of the combinations involving the Logistic Regression classifier performed tremendously better than any of the others, including the SVC classifier, which in certain conditions performed as bad as one of the dummy classifiers.

| **Classifier** | **Vectorizer** | **Accuracy** | **Precision** | **Recall** | **F-1** |
| --- | --- | --- | --- | --- | --- |
| LogisticRegression | CountVectorizer | 0.6959 | 0.5824 | 0.7596 | 0.6238 |
| LogisticRegression | TfidfVectorizer | 0.5068 | 0.2848 | 0.5975 | 0.3115 |
| Stratified | TfidfVectorizer | 0.1014 | 0.0542 | 0.0594 | 0.0548 |
| SVC | CountVectorizer | 0.2795 | 0.0743 | 0.0551 | 0.0507 |
| Stratified | CountVectorizer | 0.0904 | 0.0528 | 0.0458 | 0.0478 |
| Most frequent | CountVectorizer | 0.2301 | 0.0500 | 0.0115 | 0.0187 |
| Most frequent | TfidfVectorizer | 0.2301 | 0.0500 | 0.0115 | 0.0187 |
| SVC | TfidfVectorizer | 0.2301 | 0.0500 | 0.0115 | 0.0187 |

Table 1. Macro classifier performances

| subreddit | **askreddit** | **atheism** | **buildapc** | **electronic\_cigarette** | **explainlikeimfive** | **gaming** | **hearthstone** | **jailbreak** | **leagueoflegends** | **movies** | **pcmasterrace** | **personalfinance** | **reddit.com** | **relationships** | **starcraft** | **summonerschool** | **techsupport** | **tipofmytongue** | **trees** | **whowouldwin** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **askreddit** | 76 | 7 | 1 | 1 | 4 | 2 | 1 | 1 | 4 | 3 | 3 | 1 | 5 | 0 | 2 | 0 | 2 | 1 | 8 | 4 |
| **atheism** | 1 | 5 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 2 |
| **buildapc** | 0 | 0 | 30 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 6 | 0 | 0 | 0 | 1 | 0 | 2 | 0 | 0 | 0 |
| **electronic\_cigarette** | 0 | 0 | 0 | 7 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| **explainlikeimfive** | 1 | 0 | 0 | 0 | 10 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **gaming** | 4 | 0 | 1 | 0 | 0 | 8 | 1 | 1 | 2 | 0 | 2 | 0 | 0 | 0 | 2 | 0 | 1 | 0 | 1 | 0 |
| **hearthstone** | 0 | 0 | 0 | 0 | 0 | 0 | 9 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **jailbreak** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 8 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **leagueoflegends** | 1 | 0 | 1 | 0 | 0 | 3 | 1 | 1 | 41 | 0 | 2 | 0 | 1 | 0 | 0 | 4 | 0 | 0 | 0 | 0 |
| **movies** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **pcmasterrace** | 0 | 0 | 2 | 1 | 0 | 3 | 1 | 0 | 0 | 0 | 9 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **personalfinance** | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 8 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **reddit.com** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **relationships** | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 1 | 0 | 6 | 0 | 0 | 0 | 0 | 0 | 0 |
| **starcraft** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 4 | 0 | 0 | 0 | 0 | 0 |
| **summonerschool** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 2 | 0 | 0 | 0 | 0 |
| **techsupport** | 0 | 0 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 7 | 0 | 0 | 0 |
| **tipofmytongue** | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 10 | 0 | 0 |
| **trees** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 11 | 0 |
| **whowouldwin** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 2 |

Table 2. Confusion matrix for the combination LogisticRegression-CountVectorizer

![Table 3](https://i.imgur.com/LlPA7HS.png)   
Table 3. F-1 scores for each subreddit under the combination LogisticResgession-CountVectorizer

An idea I have about why the CountVectorizer outperformed the rest of the document is that there some words that are words that are useful and lose influence when they are vectorised using the TfidfVectorizer, and thus, this represents a degradation in the classifier performance.

## Q2. Parameter tunning

After creating a grid search that takes into consideration several parameters (mainly for the text vectorizers) the best combination is displayed in Table 3:

| **Classifier** | **Vectorizer** | **Accuracy** | **Precision** | **Recall** | **F-1** |
| --- | --- | --- | --- | --- | --- |
| LinearRegression | TfidfVectorizer | 0.7671 | 0.6902 | 0.7906 | 0.7183 |

Table 4. Results of the best performing classification model

The parameters under which the above results were obtained are:

For LogisticRegression:

- `C = 100`

For TfidfVectorizer:

- `max\_features = 5000`
- `ngram\_range = (1, 1)`
- `sublinear\_tf = True`

It may be the case that there is no need to involve a lot of features for this text classification task. The vectorizer also requires the sublinear parameter to be set to true, and this causes highly frequent words to decrease their influence.  

## Q3. Comment Discourse Classification

The performance of the discourse type classification is generally bad, as shown in Table 6. When it comes to classifying, one may think that a single vector representing a post is not enough to generate predictions, and it may be necessary to add more features to this task.

| **Accuracy** | **F1** | **Precision** | **Recall** |
| --- | --- | --- | --- |
| 0.4480 | 0.2545 | 0.2350 | 0.3853 |

Table 5. Accuracy, F1, Precision and Recall at Macro level

| **Subreddit** | **Precision** | **Recall** | **F1-score** | **Support** |
| --- | --- | --- | --- | --- |
| agreement | 0.26 | 0.45 | 0.33 | 575 |
| announcement | 0.05 | 0.47 | 0.1 | 43 |
| answer | 0.71 | 0.47 | 0.56 | 12065 |
| appreciation | 0.62 | 0.7 | 0.66 | 1465 |
| disagreement | 0.06 | 0.2 | 0.09 | 187 |
| elaboration | 0.2 | 0.26 | 0.23 | 2827 |
| humor | 0.03 | 0.25 | 0.05 | 48 |
| negativereaction | 0.04 | 0.25 | 0.07 | 53 |
| other | 0.05 | 0.37 | 0.08 | 49 |
| question | 0.34 | 0.44 | 0.38 | 2721 |

Table 6. Macro F1, Precision and Recall at a class level  for the combination LogisticRegression – TfidfVectorizer

## Q4. Adding features

To improve the performance of the classifier six additional features were taken into account and fed into the LogisticRegression classifier. I have chosen these features due to my experience using the website with the hope that the classifier will be able to pick up the data and will be able to gain meaningful insights from it:

- **Content + Punctuation** : Including punctuation as tokens. This is one of the easiest choices. In English, punctuation is one of the best indicators of what type of discourse we are dealing with, by removing signs (such as &quot;?&quot;) we had to rely on other features to discover if the text we are analysing is a question or other type of discourse. In this case, a custom stop word set was used, such set does not contain words like &quot;who&quot;, &quot;where&quot;, &quot;I&quot; and negative contractions.

- **Structure** : Depth of the comment. While browsing subreddits you can realize that most of the times the comments that are a direct response are highly related to the post in question, being those answers or opinions, while the comments that are a response to other comments tend to vary in nature, with disagreement, agreement, elaboration appreciation being the most common. For the depth of the comment I&#39;m just considering the raw depth, without normalisation as in my experience the depth of the thread usually does not go above 10 posts.

- **Author** : Is this the author of the original post? An author is likely to post in its own post to clarify something via an elaboration, agree or disagree or even to appreciate an answer to something they have posted, the information can be used to improve our classification task. This is just a binary flag that is set to 1 when the post&#39;s author is the same as the original thread author.

- **Thread features** : The number of comments in a discussion. The number of the comments can also be an indicator of a post being of a certain type, posts that are questions usually get a relatively small number of answers than an announcement, may get. In this case, the total length of the thread is considered as an integer value.

- **Community** : Where did this post come from? The subreddit for a given post may be one of the most important factors to consider when classifying. The first post in a subreddit like _explainlikeimfive_ and _jailbreak_ are most likely to be questions, whereas the first level posts tend to be answers. On the other hand, posts in subreddits like _atheism_ or _relationships_ are most likely elaboration.  To input this feature into the model the values were one-hot encoded.  

- **Word2Vec / NLP** : Parts of the speech. The structure of the contents of a post can be used to determine what kind of discourse is. For example, an appreciation post may contain more adjectives while a question may have more wh-determiners or wh-pronouns to name a few characteristics. To consider this feature, first I converted the body of each post into its POS representation, then a TfidfVectorizer was used to obtain a vector representation of these POS sentences.

The results of running several classification experiments are summarised in Table 6, in there it is possible to see that the huge improvement in the classification (in terms of the F1 score) is provided by the use of the previously mentioned &quot;Content + Punctuation&quot; features. It is possible to say this as there is a significant decrease when we remove it from the classification.  

On the other hand, it is also possible to see that some of the features help in increasing the overall F1 score but decrease either recall or precision. As a final note, I can conclude that the use of all six features contributed to increasing the performance of the classifier.

| **Model** | **Accuracy** | **F1** | **Precision** | **Recall** |
| --- | --- | --- | --- | --- |
| **w/o additional content features** | 0.4810 | 0.2300 | 0.2187 | 0.4455 |
| **w/o Structure features** | 0.5443 | 0.3144 | 0.2903 | 0.4572 |
| **w/o Community features** | 0.5959 | 0.3338 | 0.3106 | 0.5341 |
| **w/o Author features** | 0.5792 | 0.3342 | 0.3083 | 0.5024 |
| **w/o Word2Vec features** | 0.5898 | 0.3383 | 0.3148 | 0.5119 |
| **w/o Thread features** | 0.5927 | 0.3486 | 0.3246 | 0.4984 |
| **All features** | 0.5951 | 0.3558 | 0.3323 | 0.4985 |

Table 7. Comparative Accuracy, F1, Precision and Recall when leaving-one-out
