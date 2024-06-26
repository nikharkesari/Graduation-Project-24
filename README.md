# User Interest Based Video Summarization Using Machine Learning

## Abstract
Video summarization plays a crucial role in efficiently extracting key information from lengthy videos. However, traditional methods often lack 
consideration for user intent, resulting in summaries that may not align with user preferences. In this paper, we propose a novel approach for video 
summarization that takes into account the user's query to generate personalized summaries tailored to their interests. Our method leverages a combination of 
state-of-the-art machine learning techniques. We utilize OpenCV for image processing, EfficientDet for object detection to extract features from each 
frame, NLTK for word processing, and Spacy for comparing features and user queries to select key frames. 
To capture user intent, we preprocess the user query by removing stop words and lemmatizing the text, forming a list of relevant words. We then compare 
this list to the list of features detected in each frame, calculating a similarity score using Spacy.For evaluation, we employ several datasets including 
TVSum, YouTube videos, and our own Real Time Videos (RTV) dataset. RTV comprises videos captured by phone cameras, ranging from short clips to 
several minutes, capturing everyday household objects and activities. Our experiments demonstrate the effectiveness of our approach in generating 
user-centric video summaries, outperforming traditional methods by considering user intent. This work contributes to the advancement of video summarization 
techniques, paving the way for personalized video content consumption experiences. 

## Methodology  
### 1. Introduction 
In the realm of digital multimedia content, the exponential growth of online video platforms has led to an overwhelming abundance of video content. 
However, the effectiveness of traditional methods for video summarization is challenged by the lack of descriptive metadata and the inability to incorporate 
user queries into the summarization process. Addressing this challenge, we propose a method as shown in the Fig. 2 for generating video summaries that 
are tailored to user interests, leveraging machine learning techniques and content analysis. 

### 2. Dataset 
To facilitate the development and evaluation of our proposed method, we curated and utilized three distinct datasets: 
TVSum Dataset: A widely-adopted benchmark dataset in the field of video summarization, comprising a diverse collection of professionally-produced 
videos across various domains. 
YouTube Dataset: An eclectic selection of videos sourced from the popular online video-sharing platform, encompassing a broad spectrum of content types 
and genres. 
RTV (Realtime Video) Dataset: A novel dataset created specifically for this research, featuring videos captured by smartphone cameras depicting everyday 
objects and scenarios encountered in real-life situations. 
 
### 3. Feature Extraction 
Central to our approach is the extraction of salient features from video frames, 
which serve as the basis for summarization. We employed the state-of-the-art 
EfficientDet model for feature extraction, retaining features with a confidence 
level exceeding 0.3. These extracted features are then subjected to further 
processing to determine their relevance to user queries. 
 
### 4. Machine Learning Model 
In our pursuit of an effective video summarization model, we conducted comparative experiments with several popular deep learning architectures, 
including ResNet50 and InceptionV3. However, our empirical findings demonstrated that EfficientDet yielded the most accurate results in terms of 
relevance to user queries, thus serving as the primary model for our methodology. 
 
### 5. Evaluation Metrics 
The evaluation of our proposed video summarization method entails the assessment of its performance against established metrics, including Precision, 
Recall, and F-score. To facilitate the evaluation process, we have initiated a crowdsourcing effort for manual annotation, wherein human annotators provide 
ground truth summaries for comparison with our generated summaries.

### 6. Experimental Setup 
The implementation of our methodology was realized within a Python programming environment, leveraging a suite of libraries tailored to image 
processing, natural language processing (NLP), and video analysis. Notably, OpenCV was utilized for video frame extraction and processing, EfficientDet 
for feature extraction, and NLTK and Spacy for text preprocessing and semantic analysis. 
 
### 7. Methodology Overview  
Our methodology comprises several key steps, outlined as follows: 

Frame Extraction: In this figure as we can see video frames are extracted at a 
predefined frames-per-second (fps) rate using OpenCV, ensuring comprehensive coverage of temporal information. 
![image](https://github.com/nikharkesari/User-Interest-Based-Video-Summarization-Using-Machine-Learning/assets/64958174/0a2bd9a6-b71f-4168-9374-caef1f34fccb)


Preprocessing: Extracted frames undergo preprocessing, including scaling down and noise reduction, to enhance computational efficiency and feature 
extraction accuracy. The preprocessing is depicted in the figure below.
![image](https://github.com/nikharkesari/User-Interest-Based-Video-Summarization-Using-Machine-Learning/assets/64958174/162bcb93-5f03-4822-9271-c3708eb7985a)

Query Processing: User queries are preprocessed using NLTK to remove stop words and tokenize the query into meaningful components, facilitating semantic 
analysis and comparison with extracted features as shown in figure.
![image](https://github.com/nikharkesari/User-Interest-Based-Video-Summarization-Using-Machine-Learning/assets/64958174/039e61f5-a998-4073-8743-add58aa796ac)

Feature Comparison: In the fig. 6 as we can see the processed user queries are compared with extracted video features using Spacy, a natural language 
processing library, to compute relevance scores indicative of feature-query alignment. The figure below shows comparing the similarities between lists of objects. 
![image](https://github.com/nikharkesari/User-Interest-Based-Video-Summarization-Using-Machine-Learning/assets/64958174/cce78282-3fca-4db7-8e80-f8fe4bb3337b)

Key Frame Selection: Key frames, representing the most relevant segments of the video content with respect to the user query, are selected based on the 
computed relevance scores as shown in Fig. 7. These key frames are subsequently stitched together to form the final video summary using OpenCV's image manipulation capabilities. 
![image](https://github.com/nikharkesari/User-Interest-Based-Video-Summarization-Using-Machine-Learning/assets/64958174/7312e092-2872-43ca-a61c-8efb223d535b)



