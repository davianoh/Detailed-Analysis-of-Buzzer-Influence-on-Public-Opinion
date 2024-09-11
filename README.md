# Analyzing the Impact of Buzzers on Public Opinion Using IndoBERTweet and XGBoost Based on Graph and Tweet Features
<h2>Case Study: 2024 Indonesian Presidential Election</h2>

### Introduction
In the 2024 Indonesian Presidential Election, social media platform X was heavily used, with buzzers—paid individuals—spreading misleading information, making it hard for the public to identify genuine content. This highlights the need for an effective method to detect buzzers. 
<div align="center">
<img src="https://github.com/user-attachments/assets/2f2aa177-caea-4e44-94b4-a5a7adbe6bdd" alt="berita-buzzer" style="width: 55%;" />
</div>
This research focuses on detecting buzzers at the tweet level, unlike previous studies that analyzed user-level data. The goal is to develop a method to accurately identify buzzers and analyze their influence on public opinion regarding the election. The findings could help the public get reliable information, assist candidates in understanding real public sentiment, and improve survey analysis accuracy, while also serving as a reference for future research.

### Proposed Methods
This research will follow an analytical process that combines methods from various sub-tasks, including buzzer detection to filter tweets from buzzers; sentiment classification and topic modeling to understand public opinion on topics related to specific candidates.
<div align="center">
<img src="https://github.com/user-attachments/assets/7ab864f6-3ecd-4e05-9965-f6ef67e673bb" alt="main-problems" style="width: 55%;" />
</div>

#### 1. Buzzer Detection
Buzzer detection aims to classify tweets from buzzers who often have few followers but high activity and unusual usernames. Patterns from previous research guide this process. The training dataset is created by filtering tweets based on features like the number of posts and followers, as well as account usernames. 
<div align="center">
<img src="https://github.com/user-attachments/assets/7dd494c5-b43a-4c8b-83f0-54ef618890e1" alt="main-problems" style="width: 80%;" />
</div>
Features are extracted from tweet text, non-text attributes, and tweet relationships using graph-based methods. Key features include tweet content, user activity, and centrality measures in the tweet graph. The final model combines IndoBERTweet for text analysis with XGBoost and AdaBoost for other features. Predictions are merged using unanimous or soft voting to determine the best results for detecting buzzers.

#### 2. Sentiment Classification

#### 3. Topic Modeling

