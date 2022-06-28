# Album Art Genre Classification

### Introduction
Music is a major part of our daily lives and culture, and album art sets the tone for songs and merchandise. We wanted to see if we could predict an album's genre using album cover art. We wanted to do this because it has not been researched much. Album genre classification has mostly been done in research with audio, album name, and lyrics. Very few people have researched if you can predict the album genre based on album art alone. We were inspired to do this work when we noticed that many large artists such as Lady Gaga and Taylor Swift have progressions in album art corresponding to a shift in music genre.

### Main Idea
We want to create a Convolutional Neural Network to predict which genre of music an album belongs to based on an image of its album art.

### Data Used
We used RGB Images from MuMu: MultiModal Music Dataset (2017). This data can be found in this repository under MuMu_dataset. Within this we used the single label genre dataset. This dataset can be found in the MuMu_dataset folder and is called MuMu_dataset_single-label.csv.
You can find the data here: https://github.com/msaifyan/album_art_genre_classification/tree/master/MuMu_dataset

### Pre-Processing
First, we needed to create a dataframe that correctly maps images and their file path to the appropriate genre label. We did this by joining the amazon_id from the MuMu single genre label dataset with the Amazon metadata dataset, which includes the url for album covers. We will then take all unique album covers and create a dataframe consisting of the unique album covers of the top 12 genres in the dataset.

### Downloading Images
This part was difficult for us; we had to actually download the data using the URLs given by the DataFrame in order to build a proper dataset for our convolutional neural networks. We iterated through each row and downloaded the album art locally. We built a dataframe to track where this file is downloaded and the genre label associated with that file path so that we can iterate through each file individually in our dataset.

### Models
We created two different models. The first was our baseline convolutional neural network. This model has 5 convolutional layers. We trained this model for 5 epochs and ended up with a training accuracy of 24% and a validation accuracy of 21%. The second model we created was a pre-trained VGG-16 model. For this model we used pre-trained weights, and it was partially frozen. We only trained this for 2 epochs, due to a lack of computing power. This model had a training accuracy of 51% and a validation accuracy of 24%.

Here is a visual representative of what the VGG-16 structure looks like:
![image](https://user-images.githubusercontent.com/47399887/176247533-f3f727cb-de7c-4bd6-bb4e-657a3a70be7c.png)

The code for the pre-processing, downloading images, and model creation can be found here:
https://github.com/msaifyan/album_art_genre_classification/blob/master/Album_Art_Genre_Classification.ipynb


### Results
As stated above, we only got a validation accuracy of 24%. The model did pretty well at predicting genre for albums that belonged to the most popular genre (Dance & Electronic). We had a very imbalanced dataset. We had too many observations with the Dance & Electronic label, for this to perform better we would need to balance our dataset. We also did not have the computing power to effectively train the VGG. Here is an example of the model correctly predicting Dance & Electronic:

<img width="341" alt="Screen Shot 2022-06-28 at 10 43 43 AM" src="https://user-images.githubusercontent.com/47399887/176248323-9a6dfeef-217b-4906-bfd2-954e22bd7573.png">

### Future Work
To continue this project, we would want to train the VGG for more epochs, as well as gather more data to balance our dataset. I think doing both of these things as next steps would make the model perform significantly better. 



