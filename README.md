# Netflix-and-Index

This repo contains the files associated with the development of the ImDb Information Retrieval System, Netflix & Index. The project provides users with custom movie recommendations following a user entry 

Here's the deployed project demonstrating the recommender system: https://netflix-and-index.herokuapp.com/

**Data Life Cycle Steps**

**(A) Data Extraction**

- The data set for the project was from the imDb dataset found here: https://www.imdb.com/interfaces/ 
- Files being used are as follows: title.akas.tsv.gz, title.basics.tsv.gz, title.crew.tsv.gz, title.principals.tsv.gz, title.ratings.tsv.gz, name.basics.tsv.gz.

**(B) Data Pre-processing/Transformation**

One technical challenge arised from the data being excessively messy, it involved alot of pre-processing. This phase consisted of the following

(i) Filter non-English movies

(ii) Remove duplicate movie IDs from the dataframe

(iii) Delete null movie ID records

(iv) Filter out old movies that are redundant

(v) Retain only relevant data fields for recommendation class

Despite some of these filtering steps, we still had to quite a few records slipping the cracks and we had to address those cases as well.

The data set was first cleaned and filtered to include movie title, titleId, genre, average rating, runtime, and year. Our data was loaded into a dictionary which will be then introduced into our KNN classification system.

**(C) Data Loading**

The fields that are being considered: movie title, titleId, genre, average rating, runtime, and year

The data was then loaded into a dictionary with the movie name as key to introduce to the ranking algorithm.

**(D) Ranking Function**

There were design choices related to which features that had to be integrated into the ranking algorithm. The recommender system utilizes a Vector Space Model (VSM) i.e an altered KNN algorithm for ranking the top 3 movies alike to the user's movie query entered into the search engine.

The strong features are: Genre

The weak features are: Startyear, Runtime, Ratings

**(E) Information Retrieval Evaluation**

The model evaluation was performed by applying numerous individual queries and assessing the quality of the recommendation. Integrating features like plot/content of the movie would better the performance.


Images of UI on the platform

![image](https://user-images.githubusercontent.com/55374010/197109769-cdae7e9f-af9b-4aff-af03-f50e30b104b8.png)

![image](https://user-images.githubusercontent.com/55374010/197109922-d36ad58e-d835-45fc-97be-6819d6c2ccac.png)

Team Members: Hariharan Sivakumar, Akash Gajendra, Aarish Brohi, Keith Adams, Stephen Ndubueze
