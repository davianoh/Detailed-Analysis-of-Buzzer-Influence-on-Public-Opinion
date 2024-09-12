# Analyzing the Impact of Buzzers on Public Opinion Using IndoBERTweet and XGBoost Based on Graph and Tweet Features
<h2>Case Study: 2024 Indonesian Presidential Election</h2>

### Introduction
In the 2024 Indonesian Presidential Election, social media platform X was heavily used, with buzzers—paid individuals—spreading misleading information, making it hard for the public to identify genuine content. This highlights the need for an effective method to detect buzzers. 
<div align="center">
<img src="https://github.com/user-attachments/assets/2f2aa177-caea-4e44-94b4-a5a7adbe6bdd" alt="berita-buzzer" style="width: 55%;" />
</div>
This research focuses on detecting buzzers at the tweet level, unlike previous studies that analyzed user-level data. The goal is to develop a method to accurately identify buzzers and analyze their influence on public opinion regarding the election. The findings could help the public get reliable information, assist candidates in understanding real public sentiment, and improve survey analysis accuracy.

### Proposed Methods
This research will follow an analytical process that combines methods from various sub-tasks, including buzzer detection to filter tweets from buzzers; sentiment classification and topic modeling to understand public opinion on topics related to specific candidates.
<div align="center">
<img src="https://github.com/user-attachments/assets/7ab864f6-3ecd-4e05-9965-f6ef67e673bb" alt="main-problems" style="width: 55%;" />
</div>

#### 1. Buzzer Detection
Buzzer detection aims to classify tweets from buzzers who often have few followers but high activity and unusual usernames. The training dataset is created by filtering tweets based on features like the number of posts and followers, as well as account usernames. 
<div align="center">
<img src="https://github.com/user-attachments/assets/7dd494c5-b43a-4c8b-83f0-54ef618890e1" alt="main-problems" style="width: 80%;" />
</div>
Features are extracted from tweet text, non-text attributes, and tweet relationships using graph-based methods. Key features include tweet content, user activity, and centrality measures in the tweet graph. The final model combines IndoBERTweet for text analysis with XGBoost and AdaBoost for other features. Predictions are merged using unanimous or soft voting to determine the best results for detecting buzzers.

##### Result
The resulted training data for buzzer detection included 6,000 tweets with balanced labels. Text, non-text, and graph features were extracted, with the graph having over 2 million nodes and 1.9 million edges. The IndoBERTweet model (batch size 32, learning rate 1e-5) achieved the best accuracy for text features at 0.8294. The XGBoost model (max depth 2, with graph features) performed best for non-text and graph features at 0.9241. 
<div align="center">
<img src="https://github.com/user-attachments/assets/578e7a40-5d3f-4788-ad64-fb81f147dfbe" alt="buzzer-detection-result" style="width: 55%;" />
</div>
Combining both models with soft voting resulted in the highest accuracy of 0.9436. The buzzer detection identified over 4 million buzzer tweets from 9.8 million total tweets.

#### 2. Sentiment Classification
The next step is classifying tweet sentiment for each candidate. Tweets are grouped by candidate key terms to avoid confusion when a tweet mentions multiple candidates. Training data is created by using hashtags to identify tweet sentiment, with manual checks for accuracy. Tweets containing relevant hashtags are labeled accordingly. Once the training dataset is ready, each candidate's sentiment classification model is trained using IndoBERTweet, and the trained models are used to predict sentiment for tweets related to each candidate.

##### Result
The resulted sentiment dataset included 3,000 positive and negative labeled tweets for each candidate. The IndoBERTweet model was trained with optimal parameters (batch size 32, learning rate 1e-5). The sentiment predictions for each candidate's tweets were generated, and the results are shown
<div align="center">
<img src="https://github.com/user-attachments/assets/75731c24-cf63-49da-b54e-3220f9e158ed" alt="sentiment-classification-result" style="width: 55%;" />
</div>

#### 3. Topic Modeling
The next step is identifying topics in tweet data using Latent Dirichlet Allocation (LDA). LDA is a statistical method used to discover various topics from a collection of documents. This method performs well and efficiently handles large volumes of text data, making it suitable for this task. LDA generates key terms for each identified topic, which reflect the issues present in the related tweet data.

##### Result
The LDA algorithm identified 14 key topics in the tweet data, with a c_v score of 0.5343 and a u_mass score of -4.7826. The most discussed topics were youth and national development, public reactions and emotions, and national defense and achievements. Some topic clusters overlapped, but the main themes were still distinguishable.
<div align="center">
<img src="https://github.com/user-attachments/assets/f2926e32-32e8-48d9-b0dd-3d6fe03645db" alt="topic-modeling-result" style="width: 55%;" />
</div>

### Analysis Discussion
The analysis revealed that 35% of tweets about candidates 1 and 2 were from buzzers, while 54.9% of tweets about candidate 3 were from buzzers, indicating a strong buzzer trend for candidate 3. In the case of wanting to obtain organic tweet data, buzzer tweets need to be removed. Further analysis of buzzer tweets can also be conducted by selecting them. 
<div align="center">
<img src="https://github.com/user-attachments/assets/0cbce583-62df-4110-94c6-03d7382700b0" alt="analisis-1" style="width: 55%;" />
</div>
Sentiment analysis showed that buzzer tweets were used to influence positive sentiment, with some also creating negative sentiment. For candidates 1 and 3, buzzers mostly increased positive sentiment, while for candidate 2, buzzers were used more to spread negative sentiment, reflecting campaign attacks.
<div align="center">
<img src="https://github.com/user-attachments/assets/a5baff67-0c30-467c-ae60-3d9efa9b8e12" alt="analisis-2" style="width: 55%;" />
</div>
Topic modeling of negative buzzer tweets about candidate 2 identified frequent topics: public reactions and emotions, national defense and achievements, and political competition and social media.
<div align="center">
<img src="https://github.com/user-attachments/assets/0de617c5-b967-43c6-a57b-03624eaff506" alt="analisis-3" style="width: 55%;" />
</div>

### Conclusion
This research found that detecting buzzers at the tweet level can be effectively achieved using text, non-text, and graph features. The IndoBERTweet model was utilized for text features, while XGBoost was used for non-text and graph features. Combining the results of both models with a soft voting method yielded the best prediction accuracy of 0.9436. The study found that 41.30% of tweets were identified as buzzer tweets. Removing these buzzer tweets resulted in more representative sentiment values. The combination of buzzer detection and LDA for topic modeling provided insights into the focus of topics and issues that were either used for attacks or to strengthen each candidate's position. <br><br>
Note: All resources used in this research, including the full scientific paper PDF and presentation file, can be accessed through this repository.
