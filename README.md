# Audio transcription streaming analytics
TrendMarketPlace_Group8

This project repository is created in partial fulfillment of the requirements for the Big Data Analytics course offered by the Master of Science in Business Analytics program at the Carlson School of Management, University of Minnesota.

## Topic of Interest
As one of uncontroversial data types, audio data has been recognized as valuable but expensive and difficult to be processed and explored. The obstacles include data processing difficulty. Incomplete data architecture can bring data processing difficulties such as audio transcription and translation. This will also bring high manual cost if the company hires workers to manually transcribe the audio data. Besides, the time gap from data preparation to final result delivery may result in delayed response to unsatisfied customers and unable to grasp market trending in time.

To tackle this problem, we introduce a streamlining voice message transcription system using the AWS tool 'Transcribe', create a data pipeline workflow to analyze the transcribed audio files, and then visually represent the analysis result. Based on the tool, we can take timely measures in reacting to customer requests.

## Introduction of Amazon Transcribe
### What is Amazon Transcribe?
Amazon Transcribe is an AWS service that makes it easy for customers to convert speech-to-text. Using Automatic Speech Recognition (ASR) technology, customers can choose to use Amazon Transcribe for a variety of business applications, including transcription of voice-based customer service calls, generation of subtitles on audio/video content, and conduct (text based) content analysis on audio/video content.  

### How does Amazon Transcribe interact with other AWS products?

![image](https://github.com/aloks95/msba6330_trends_market_place/blob/main/architecture.png)

### Use Case
1. Call Center Analytics
2. Subtitling
3. Medical Transcription

### Demo
We use the example audio as an example to show how the whole pipeline works. We use S3 to store the audio dataset, use transcribe to automatically convert audio to text, and then use Amazon comprehend to detect sentiments for each customer. Finally, we use Quick-Sight to create a dashboard to show the count of various sentiments so that the business can understand their customer common emotions.

#### Set Up Requirements
Before running the code provided, you need to set up authentication credentials for your AWS account using either the IAM Console or the AWS CLI. There are two ways to set up the configuration.

1. If you have the AWS CLI installed, then use the 'aws configure' command in the terminal to configure your credentials. Follow the guidance to set access key id and secret access key.
2. When using boto3.client() function to set AWS tools we use, you should declare two keys:  
    - aws_access_key_id = YOUR_ACCESS_KEY  
    - aws_secret_access_key = YOUR_SECRET_KEY  

In the code provided, we have already used first way to set up authentication credentials and connect to the AWS account we use. 

#### Results
Using the pipeline (S3 -> Transcribe -> Comprehend), we get the sentiments of each customers. Using Amazon QuickSight, we create a dashboard to visualize the result. For business use, this pipeline can be set to run every day to automatically provide customer emotion to the company.
![image](https://github.com/aloks95/msba6330_trends_market_place/blob/main/Dashboard.png)


## Video Presentation
Link: https://youtu.be/XVKejsdpkpI

## Reference
data source: https://github.com/jim-schwoebel/sample_voice_data 
