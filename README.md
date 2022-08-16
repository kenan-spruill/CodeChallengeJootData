# CodeChallengeJootData

## About Joot
Joot is a company that builds predictive models for Instagram, specifically a model that helps the user select the most engaging instagram images. 

By analyzing the engagement levels of past instagram post, extracting metadata, and performing feature generation using Computer Vision; Joot is able to generate models for businesses so they can always post the best image on their company social media pages. 

## The Challenge
The following is a coding challenge using real world data, where you are tasked with dianosing what is going wrong with the predictive  processes, and figure out why the model is returning bad outputs. 

You will be comparing the input dataset to the predictive dataset, and see if there are significant differences in any of the columns. There are generally around 4000 columns, but every column has a prefix and there are only a handful of prefixes, if something is going wrong it is probably happening at the prefix level and affecting all of the columns in that prefix (although that isn't guaranteed)

You will likely find the most success comparing and contrasting the data from the training set to the data from the predictive set, and seeing if there is any data that is **sparse** or **minimal variance** in one of the datasets, **but not both**. 

I will provide some EDA input below representing how I would begin to approach the project. 

## The Use Case





Loyal Stricklin is a Joot client and a leather goods retail company based in Nashville, Tennessee

They have input into the Joot interface that they would like to build an image model based on a conglamarate of the following accounts.
 
*   loyal_stricklin (their own account)
*   tannergoods
*   missionworkshop
*   trakkebags
*   treesizeverse
*   vermilyeapelle
*   bradleymountain

These accounts are also leather goods retailers/influencers. 


## Dataset Description

(Rank ordered roughly by importance)



1.   **train_data.csv**

The data that is used to build the sagemaker model. These are the images that have already been posted across the 7 accounts that have been designated. 


2.   **Folder:** Loyal_Stricklin_Market_Image_Score_Training_Sets

The data from new images after being scored, featuring the inputs and outputs. This is combined into a single dataframe below 

3. **model.tar.gz**

tar.gz file for the XGBoost model that is used for scoring inputs. 

4. **Data Column Info.txt**

Contains information about what the different prefixes stand for in the dataset.


### Less important datasets, but useful for context
A) **loyal_stricklin_model_record.csv**

Metadata information about the sagemaker model. 

The only important thing here is that the "columns" column of the data contains the order in which the columns are expected during scoring. However, that order should already be reflected in the data as it stands 

B) **loyal_stricklin_market_scores.csv**

Contextual data that is the combination of the score column from #2 and the stoplight function, this is what the data looks like on the backend. 

There is a difference between this file and the score column in #2, because the #2 data was scored a few days later 

Unfortunately there is no mapping to the index from #2

C) **loyal_stricklin_market_all_accouts_batch_score_results.csv**

Un-universalized Scoring results for all posts from all accounts. 


D) **loyal_striicklini_market_images.json**

The data before it is converted into a matrix to create a predictive model for the uploaded images.


E) **Account JSONS**

-- treesizeverse.json

-- missionworkshop.json

-- bradleymountain.json

-- tannergoods.json

-- trakkebags.json

-- loyalstricklin.json

-- vermilyeapelle.json

Raw data before it is converted into a matrix to create a predictive model for the analyzed instagram posts. (Separated by IG account)

E is fundamentally the same data as D, except it is the raw image data + metadata used as inputs into the model vs. the unseen image data which is scored by the model. 




