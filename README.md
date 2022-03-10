# Assignment 2: Data Bias

### Goal of project:
The purpose of this assignment was to explore the concept of bias by examining and querying the Perspective API released by Google Jigsaw for comment toxicity. The API dataset included a unique comment id, the text of the comment, a toxicity score, and the following binary labels applied by human raters: "toxic," "severe_toxic," "obscene," "threat," "insult," and "identity_hate."

### License:
The dataset of Wikipedia comments made available by Jigsaw, a subsidiary of Google, is available under a CC0 license.

### Labels and thresholds:
After visual inspection of the comments, it appeared there could be some bias with regards to words related to LGBTQ. Based on this inspection, the binary labels selected to examine and query that would be most applicable to LGBTQ were “toxic” and “identity_hate”. Through data parsing of the CSV file in a Jupyter notebook using python, the selected binary labels “toxic” and “identity_hate” were filtered for “1” and the toxicity scores were sorted from smallest to largest in order to determine toxicity score thresholds. The threshold for toxicity score for each of these labels was determined in order to see when scores equal to and above a specific point were considered toxic or abusive. The threshold of the selected labels in the model are as follows:

* toxic:		      0.05439934
* identity_hate:	0.31089434

### Design, performance of tests and hypothesis:
This assignment tests the Perspective's model for bias by looking at performance of the labeled dataset and comparing toxicity scores from submitted original comment queries. Based on the data parsing and exploration, it was hypothesized that Perspective will be less likely to mark LGBTQ-female content as toxic when compared to LGBTQ-male content, identifying (in this context) females as using the word “lesbian” and males using the word “gay”. Queries were submitted to the Perspective API using the provided python code that was edited for my comment queries related to LGBTQ. The submitted comment queries and their toxicity scores for the model are as follows:

![image](https://user-images.githubusercontent.com/99284940/157593513-23dcd9ba-e59c-405e-b683-49573b977b68.png)

### Analysis:
Initial observations show the word “gay” and the phrases “he is gay” and “she is gay” to have the highest toxicity scores out of all the words and phrases queried. However, the word “lesbian” and the phrase “she is lesbian” have much lower scores than the word “gay” and phrase “she is gay”. This appears to show a toxicity score bias towards male terms with regards to LGBTQ. These toxicity scores provided a dataset to compare my own small test set to(Instead of comparing to a small data set just simply what i visually saw in the provided csv file, then expand using evidence from the csv fil). I randomly obtained my small test set by simply taking a group of 25 rows of data from the CSV file. I applied the following subset of my original comment queries to my small dataset and obtained the following scores:

* Gay:            0.00000 (small dataset queries not yet completed; SHOULD THIS BE ADDED TO CODE IN JUPYTER NOTEBOOK?)
* Lesbian:        0.00000
* He is gay:      0.00000  
* She is lesbian: 0.00000  
