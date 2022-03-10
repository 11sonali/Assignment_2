# Assignment_2
## Data Bias

#### Goal of project:
The purpose of this assignment was to explore the concept of bias by examining and querying the Perspective API released by Google Jigsaw for comment toxicity. After visual inspection of the comments, it appeared there could be some bias with regards to words related to LGBTQ. 

#### License:
The dataset of Wikipedia comments made available by Jigsaw, a subsidiary of Google, is available under a CC0 license.



Based on this inspection, the binary labels selected that would be most applicable to LGBTQ were “toxic”, “severe_toxic”, and “identity_hate”. Through data parsing of the CSV file into an excel format, the selected binary labels “toxic”, “severe_toxic”, and “identity_hate” were filtered for “1” and the toxicity scores were sorted from smallest to largest in order to determine toxicity score thresholds. The threshold for toxicity score for each of these labels was determined to see when scores equal to and above a specific point were considered toxic or abusive. The threshold of the selected labels in the model are as follows:

toxic:		0.05439934
identity_hate:	0.31089434
