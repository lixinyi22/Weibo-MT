# Weibo-MT
This repository is the open source for the multi-topic social media dataset collected from Sina Weibo.
# **A Multi-topic Social Media Data Collection**

## 1. Introduction

This dataset is a multi-topic social media dataset collected from Sina Weibo, consists of 7,705 original posts, 202,238 comments, and 54,401 user profiles, encompassing both post publishers and commenters. The collected posts span an average of 2,771 days for each topic.

**•** **Topics Covered** : Travel, Movies, Psychology and Cars

## 2. Dataset Structure

-	**File Format** : csv

-	**topic_post.csv**:

-	**post_id** : Unique identifier for the post. The **post_id** remains consistent across other files in the dataset.

-	**user_id** : Unique identifier for the user who published the post. The **user_id** remains consistent across other files in the dataset.

-	**publish_time** : The time when the post was published.

-	**comment_count** : The total number of comments received by the post.

-	**like_count** : The total number of likes received by the post.

-	**post_content** : The content of the post.

-	**post_hashtags** : The list of hashtags included in the post.

-	**topic_comments.csv**:

-	**comment_id** : A unique identifier for the comment. The **comment_id** remains consistent across other files in the dataset.

-	**post_id** : The unique identifier of the post that the comment replies to.

-	**user_id** : The unique identifier of the user who posted the comment.

-	**publish_time** : The timestamp when the comment was published.

-	**like_count** : The total number of likes received by the comment.

-	**comment_count** : The total number of replies received by the comment.

-	**sentiment** : The sentiment label for the comment’s content, categorized into five levels:  *Very Negative* ,  *Negative* ,  *Neutral* ,  *Positive* , and  *Very Positive* .

-	**topic_user_with_post.csv & topic_user_with_comment.csv**

-	**user_id** : The unique identifier of the user.

-	**gender** : The gender category of the user.

-	**followee_count** : The number of accounts the user is following.

-	**followers_count** : The number of followers (accounts following the user).

-	**location** : The geographic location category based on the user’s IP address.

-	**birthday** : The user’s date of birth represented in relative time.

-	**registry_time** : The user’s account registration date represented in relative time.

-	**certification** : Indicates whether the user’s identity is verified by the platform.

-	**credit** : The user’s credit record category.

-	**constellation** : The user’s constellation category.

-	**comment_count** : The total number of comments posted by the user.

-	**repost_count** : The total number of reposts by the user.

-	**like_count** : The total number of likes given by the user.

-	**post_count** : The total number of posts published by the user.

## 3. Data Preprocessing

-	**Collection** : We collected the original posts from Sina Weibo platform using the official API by searching related hashtags and keywords. Specifically, we selected the ’20 Minute Park Theory’ as the focal topic within the domain of psychology.
Subsequently, we identified hashtags with a high degree of relevance to the subject and filtered these posts, thereby guaranteeing a more concentrated topical relevance. 

-	**Cleaning**: To maintain a dataset devoid of discriminatory content, we employed the OpenAI GPT-4o-mini API for the textual screening of each post. Additionally, an analysis of post lengths revealed that all posts contain a minimum of five characters, negating the need for further filtering. 

- **Anonymization**: We replaced all post IDs, comment IDs, and user IDs with anonymized identifiers. Second, we converted all timestamps into relative times based on a randomly assigned reference time. Lastly, all non-numerical attributes in user profiles were transformed into categorical representations. Since original posts cannot be accurately retrieved on Sina Weibo based solely on the natural text content, the natural text included in our dataset does not pose risk of exposing user
privacy.

- **Sentiment Analysis**: we utilized the DistilBERT-based Multilingual Sentiment Classification Model2 accessible through the Hugging Face platform to conduct sentiment analysis on the natural language text contained within user comments. The comments were systematically classified into five sentiment categories: Very Negative,Negative, Neutral, Positive, and Very Positive.
