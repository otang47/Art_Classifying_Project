# Classifying art project
Classifying images of paintings using neural networks and identifying the genre they belong to.

This project is my final project for the Ironhack data analytics bootcamp of March 2020 and was presented during the Hackshow.

The presentation can be accessed here:

[![Image](/Media/Presentation_Ironhack.png)](https://docs.google.com/presentation/d/1s2mUsGaCcwdTqDGJHlKax6a9dQOGwq8KLAL7dgJcW_w/edit?usp=sharing)

## Overview
From a dataset containing images of paintings, the goal is to create a machine learning model that will identify their genre (e.g. impressionism). 

## Process followed

### Librairies used
* pandas
* numpy
* os
* matplotlib.pyplot
* seaborn
* sklearn
* PIL
* keras

### Steps
<b>1. Data collection</b>
<p>Dataset imported from : https://www.kaggle.com/ikarus777/best-artworks-of-all-time</p>
  
<b>3. Data exploration and data cleaning: </b>
<div>The dataset contains information about 50 painters, more than 8000 images of paintings,  their genre and is classified per painter.</div>

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/1.%20Paintings.png?raw=true)

* Ranking painters per number of paintings 
<div>On the 50 represented painters, the 3 painters with the most paintings in this dataset are Vincent Van Gogh, Edgar Degas and Pablo Picasso, all of them having more than 400 paintings. </div>

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/3.%20Painters.png?raw=true)

* Nationalities of painters
<div>The dataset contains 17 different nationalities. French, Dutch and Spanish having the most paintings on this dataset. </div>

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/2.%20Nationalities.png?raw=true)

* Genres of painters
<div>There are a lot of different genres in this dataset, some painters being associated to several genres.</div>
<div>E.g. Impressionism and Post-Impressionism</div>

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/4.%20Genres%20before%20cleaning.png?raw=true)

<div>After cleaning the dataset and attributing unique genres to each painter, 16 genres represent all artists and paintings.</div>

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/5.%20Genres%20after%20cleaning.png?raw=true)

<b> 4. Image transformation </b>
All the images were resized and converted to numpy arrays. The genres (impressionism, baroque) were also converted to numpy arrays.

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/9.%20Resizing%20images.png?raw=true)

<b> 5. Model building </b>

* 1st model
A first model was built using only one random genre, Baroque, to test the keras library. The accuracy obtained was of 100% since the paintings could only be baroque.

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/6.%20Model%201.png?raw=true)

* 2nd model
From the 1st model, a new model was built using all 16 genres with the same structure. However, the first results for this model were really low, with only 22% accuracy.

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/7.%20Model%202.png?raw=true)

* Final model:
A few improvements were made for the final model:

  * Only the top 5 genres (per number of paintings) were selected, i.e. Impressionism, Renaissance, Post-Impressionism, Symbolism and Baroque
  
  ![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/8.%20Model%203.png?raw=true)
  
  * Some transformations were performed on training images and added to the set. They consist of 90 degree rotation, random horizontal and vertical flips, and random zoom on overall 1000+ images.
  
  ![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/9b.%20Transforming%20images.png?raw=true)
  
  * Finally, parameters from the keras.Sequential model were modified, including: adding layers, modifying parameters, and adding a validation split. 
  
![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/10.%20Model%203%20summary.png?raw=true)

## Results
The result of this last model were improved, with 57% accuracy rate. 

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/11.%20Model%203%20results.png?raw=true)

![](https://github.com/Camillelib/Art_Classifying_Project/blob/master/Media/12.%20Model%203%20confusion%20matrix.png?raw=true)

<div>Test:</div>

[![Image](/Media/13.Youtube_video.png)](https://www.youtube.com/watch?v=RbJoAtRr6hY&feature=youtu.be)


## Conclusion
Learnings:
* How to work with images in data analysis
* How to build neural network for image classification

Future improvements:
* Add  images,  painters,  new genres
* Work on a new dataset where images are already classified per genre (and not painters)
* Test other machine learning models on this dataset

