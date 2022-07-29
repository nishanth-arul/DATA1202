# DATA1202
#Import Python Libraries
import numpy as np
import scipy as sp
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
# define variables for the csv files, this step is not mandatory but it will help to understand the importing data step in Python
File_1 = "youtube_dataset.csv"
# Read the csv file 
raw_df = pd.read_csv(File_1)
raw_df.head()
# selecting only important columns from the original dataframe
subset_raw_df=raw_df[['userID','subscribers','videoviews','channeltype','grade','MonthlyEarnings','YearlyEarnings']]
subset_raw_df.head()
#Sorting the data frame by videoviews to create a new data frame
subset_raw_df_sorted = subset_raw_df.sort_values(by = 'videoviews',ascending = False )
subset_raw_df_sorted.head(4000)
#to select only the required data
df_filtered = subset_raw_df_sorted.iloc[:1000,:]
# To see what the data set looks like, we'll use the head() method.
df_filtered.head(2000)
#saving the sorted dataframe to a new csv file
df_filtered.to_csv('youtube_sorted_Final.csv', index=False)
df_filtered.head()
# Read the csv file 
F3 = "youtube_sorted_Final.csv"
raw_dataframe = pd.read_csv(F3)
raw_dataframe.head()
raw_dataframe.tail()
raw_dataframe1 = raw_dataframe.sort_values(by = 'channeltype', ascending = True)
raw_dataframe1.head(1000)
raw_dataframe1.head()
#counting the number of categories
raw_dataframe1.channeltype.value_counts()
