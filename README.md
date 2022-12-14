# EMAIL SPAM CLASSIFIER USING NAIVE BAYES

The objective of this project is to build an email spam classifier using Naive Bayes and clustering methods. The data consist of raw unstructured text email messages that have been pre-classified as either spam or not spam (referred to as ham).

For our exploratory analysis, we built out binary features to form a more traditional structured dataframe. This allowed us to create clear visual distinctions between features of ham and spam emails. Some of these key differences that indicated an email may be spam included the presence of an all capitalized subject line, a generally longer text document, the designation of reply or not, and the presence of uncommon punctuation.

Following our preliminary analysis, we prepared both the structured and unstructured dataframes for modeling. Categorical variables were onehot encoded, while continuous variables were scaled. The text was stripped of punctuation, unnecessary lines and capitalization, although ultimately we chose to use the unprocessed data because these things are actually important in this use case.

We split the data using a type of stratified shuffle split to keep the proportion of spam to ham in our train and test splits similar. We explored the use of a Kmeans cluster to reduce the dimensionality of the original data, and while it was useful for exploratory analysis and visualization, it resulted in poor performance when used in conjunction with our Naive Bayes model. We chose to use our original Naive Bayes model with no preprocessing of the text data, resulting in an accuracy of 96%. While this is pretty good, this means an employee would still receive on average 2-3 spam emails into their inbox per 100 emails, and about 1 important message per 100 emails could be misclassified as spam.

The cost of devoting additional resources to improving the accuracy should be weighed against the potential benefit of having no important emails going to spam and only 1-2 spam emails per 100. Further work to clean the text files by removing meta data from the beginning of each email would perhaps improve accuracy further.
