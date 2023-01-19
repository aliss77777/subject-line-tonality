# subject-line-tonality
Pipeline to classify email subject lines with HuggingFace and personalize them by audience to improve response rates. Originally created for fundraising in the non-profit space, could be adapted for different verticals. Built off Arpan Goshal's EmoRoBERTa repo on HuggingFace: https://huggingface.co/arpanghoshal/EmoRoBERTa.

<b>Challenge</b><br>
Recent economic conditions have reduced donor acquisition rates and increased churn. Non-profits need ways to:
1) Improve engagement with existing donors between fundraising asks
2) Increase donation rates during matched giving tentpole moments 
3) Re-engage lapsed audiences

<b>Solution</b><br>
This model delivers an 8-category classification of email subject lines for non-profit fundraising that covers a broad scope of situations and audiences. A deep learning model is used for feature engineering and then through dimensionality reduction (factor analysis) the 8-tonalities were created to capture the nuance and tonality of various type of emails. The initial factor analysis generalized into a classification model with 95.7% accuracy to to score future incremental data against the original classification schema. Finally, as the final test of model validity, various predictive modeling scenarios were tested, using tonality as an predictable variable on response rate, and found to be predict the desired response for audience and objective with 80-90% accuracy. While not perfect this indicates a solid baseline to drive business results with some minor manual tuning. 

The intended audience for this repo is both technical and strategic. Once the data science team has developed the initial pipeline, the intention is the the email team can easily consume and apply the results to planning new campaigns. This is the reason for the emphasis on explanability and self-service visualization through such tools as Looker Studio.  

Assume source data file ingestion from an email marketing platform into the analysis environment. In this demo CSV's are used but for a live use case this should be ported to a data warehouse connection in the cloud. 

<b>Workflow</b><br>
1) Data Ingestion and Pre-processing: Calculates response rate metrics for email campaigns and uses SpaCy text processing on subject lines. Provides the key terms from each subject line which is important for explanability and socialization later.
2) Deep Learning model for feature engineering: uses the EmoRoBERTA model to add prediction columns for 28 emotion features with a numeric score for each.
- note: this step is isolated in a separate notebook to run in Google Collab to avoid challenges of installing TensorFlow locally 
3a) Develop Classification Schema: use factor analysis to identify and name 8 emotional tones relevant to non-profit fundraising. 
3b) Apply Labelling via Classification Schema: contains modules for both applying the factor analysis results initially as well as building a classification model from these results for incremental data updates
4) Modeling for Prescriptive Optimization: a validation step to use tonality as a predictor of response for a given audience and objective. Not perfect but demonstrates the validitiy of the technique, and how tonality can be combined with content and message selection to improve response rates.

<b>Final Thoughts</b><br>
Any thoughts / feedback is welcome.


<img src="https://user-images.githubusercontent.com/4154159/213568943-cb322f14-da53-4e6e-baa6-f9fb374d2b19.jpg" alt="data and model flow diagram" title="Modeling Pipeline">

Many thanks to Arpan Goshal for developing EmoRoBERTa, used in step 2. 
