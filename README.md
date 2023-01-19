# subject-line-tonality
Pipeline to classify email subject lines with HuggingFace and personalize them by audience to improve response rates. Originally created for fundraising in the non-profit space, could be adapted for different verticals. Built off Arpan Goshal's EmoRoberta repo on HuggingFace: https://huggingface.co/arpanghoshal/EmoRoBERTa.

<b>Challenge</b><br>
Recent economic conditions have reduced donor acquisition rates and increased churn. Non-profits need ways to:
1) Improve engagement with existing donors between fundraising asks
2) Increase donation rates during matched giving tentpole moments 
3) Re-engage lapsed audiences

<b>Solution</b><br>
This model delivers an 8-category classification of email subject lines for non-profit fundraising that covers a broad scope of situations and audiences. 

Assume source data file ingestion from an email marketing platform into the analysis environment. In this demo CSV's are used but for a live use case this should be ported to a data warehouse connection in the cloud. 

<b>Workflow</b><br>
1) Data Ingestion and Pre-processing: Calculates response rate metrics for email campaigns and uses SpaCy text processing on subject lines. Provides the key terms from each subject line which is important for explanability and socialization later.
2) d
- note: this can be run in Google Collab to avoid challenges of installing TensorFlow locally 
3) d
4) d

<b>Final Thoughts</b><br>
All clients looking to 


<img src="https://user-images.githubusercontent.com/4154159/213568943-cb322f14-da53-4e6e-baa6-f9fb374d2b19.jpg" alt="data and model flow diagram" title="Modeling Pipeline">

Many thanks to Arpan Goshal for developing the deeplearning model in step 2. 
