<h1> Movie-Recommendation-System </h1>
<br>

## Table of Contents
1. [Requirement Analysis](#1)
2. [Application Design](#2)
3. [Takeaways](#3)

## 1. <span id="1">Requirement Analysis</span>
(1)Database Planning <br>
Our movie recommender system needs four parts data information, including movie, user, rating and similarity information. We will use data from Movielens 1M dataset (![1M db](https://grouplens.org/datasets/movielens/1m/)) to achieve the features of movie recommender system.

(2)System Definition:<br>
(Main users for recommendation system are current users and new users. )
- New users can register new accounts;
- Users can be recommended other movies they may like; 
- Users can see the movies’ information and rate new movies.

(3) Requirements collection and analysis<br> 
- In terms of system functions
  - User account: add
  - Movie information: add/change
  - Rating: add/ change
  - Movie similarity: add/change

(4)Database Design
<img src="https://raw.githubusercontent.com/QiZhang79/Movie-Recommendation-System/master/readmeimg/Database%20Design.png" style="width: 30%">
<p><center>ERD</center></p>

(5)We will use HTML, CSS and JavaScript as web programming language; Use MySQL as
 relational database; Use Apache HTTP server as web server.

## 2. <span id="2">Application Design</span>
(1) Users are people who want to rate movies and receive new recommendations.<br>

(2) There are not different kinds of users using this recommendation system, users have same rights to operate in this system except the register function for brand new users.<br>

(3)Components:<br>
- Login,register and loginout 
- Browse movie information 
- Rate movies
- Receive recommendations

(4)Data manipulations
- Useraccount:add
- Movieinformation:add/change 
- Rating:add/change
- Moviesimilarity:add/change

(5) Inputs and outputs
- Summary:<br>
After users login in(orregister),user will receivea list of high rating movies and
see their recent rated movies. When users move their cursors to any specific movie, they will receive three new movies recommendation. Also, users can browse movie’s information and rate. Apart from the former features, users can see all of their rating histories in a new page.
- MainApproach:WeusethedatasetfromMovielenstoprocessthesimilaritybetween movies and recommend high ones according to **Item-Based-Collaborative-Filtering**.
  - Pre-processing
    - Reduce the sparsity of the original dataset. (Delete several ineffective users data) 
    - Split the train/test data.
  - Compute item-to-item similarities
    - Define a function to compute common user support.
    - Define a function to use Pearson's r to compute similarity.
    - Build a Database in MySQL to store the item-to-item similarity matrix.
  - Find the K nearest items
    - Use a 'regularization' parameter to control the effect of small common user support. 
    - Define a function to find k items nearest to the given item.
    - Recommend top three items (movies).
  - Prototypesofeachwebpages.
  <img src="https://github.com/QiZhang79/Movie-Recommendation-System/blob/master/readmeimg/1.png" style="width: 30%">
  <img src="https://github.com/QiZhang79/Movie-Recommendation-System/blob/master/readmeimg/2.png" style="width: 30%">
   <p><center>Login and Register</center></p>
  <img src="https://github.com/QiZhang79/Movie-Recommendation-System/blob/master/readmeimg/4.png" style="width: 30%">
   <p><center>Home</center></p>
  <img src="https://github.com/QiZhang79/Movie-Recommendation-System/blob/master/readmeimg/5.png" style="width: 30%">
   <p><center>Movie</center></p>
  <img src="https://github.com/QiZhang79/Movie-Recommendation-System/blob/master/readmeimg/3.png" style="width: 30%">
   <p><center>History</center></p>
