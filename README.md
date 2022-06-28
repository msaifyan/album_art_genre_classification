# album_art_genre_classification

### Introduction
Music is a major part of our daily lives and culture, and album art sets the tone for songs and merchandise. We wanted to see if we could predict an album's genre using album cover art. We wanted to do this because it has not been researched much. Album genre classification has mostly been done in research with audio, album name, and lyrics. Very few people have researched if you can predict the album genre based on album art alone. We were inspired to do this work when we noticed that many large artists such as Lady Gaga and Taylor Swift have progressions in album art corresponding to a shift in music genre.

## Main Idea 
We want to create a Convolutional Neural Network to predict which genre of music an album belongs to based on an image of its album art. 

## Data Used
We used RGB Images from MuMu: MultiModal Music Dataset (2017). This data can be found in this repository under MuMu_dataset. Within this we used the single label genre dataset. This dataset can be found in the MuMu_dataset folder and is called MuMu_dataset_single-label.csv.

[https://github.com/msaifyan/album_art_genre_classification/tree/master/MuMu_dataset]

### Pre-Processing
First, we needed to create a dataframe that correctly maps images and their file path to the appropriate genre label. We did this by joining the amazon_id from the MuMu single genre label dataset with the Amazon metadata dataset, which includes the url for album covers. We will then take all unique album covers and create a dataframe consisting of the unique album covers of the top 12 genres in the dataset.

## Downloading Images
This part was difficult for us; we had to actually download the data using the URLs given by the DataFrame in order to build a proper dataset for our convolutional neural networks. We iterated through each row and downloaded the album art locally. We built a dataframe to track where this file is downloaded and the genre label associated with that file path so that we can iterate through each file individually in our dataset.

### Models

### Results
