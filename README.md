Download Link: https://assignmentchef.com/product/solved-ece232ee-project-4-imdb-mining
<br>
In this project, we will study the various properties of Internet Movie Database (IMDb). In the first part of the project, we will explore the properties of a directed actor/actress network. In the second part of the project, we will explore the properties of an undirected movie network.

<h1>1      Actor/Actress network</h1>

In this part of the project, we will create the network using the data from the following text files:

<ul>

 <li><strong>actor_movies.txt</strong></li>

</ul>

<h2>• actress_movies.txt</h2>

The text files can be downloaded from the following link: <a href="https://ucla.box.com/s/z45q3g5zrpay8b8gtbql6ojaecb7kj2u">https:// </a><a href="https://ucla.box.com/s/z45q3g5zrpay8b8gtbql6ojaecb7kj2u">ucla.box.com/s/z45q3g5zrpay8b8gtbql6ojaecb7kj2u </a>In order to create the network in a consistent manner, you will need to do some data preprocessing. The preprocessing consists of 2 parts:

<ol>

 <li>Merging the two text files into one and then removing the actor/actress who has acted in less than 10 movies</li>

 <li>Cleaning the merged text file</li>

</ol>

The cleaning part is necessary to avoid inconsistency in the network creation. If you analyze the merged text file, then you will observe that same movie might be counted multiple times due to the role of the actor/actress in that movie. For example, we might have

<ul>

 <li>Movie X (voice)</li>

 <li>Movie X (as uncredited)</li>

</ul>

If you don’t clean the merged text file, then Movie X (voice) and Movie X (as uncredited) will be considered as different movies. Therefore, you will need to perform some cleaning operations to remove inconsistencies of various types.

Question 1: Perform the preprocessing on the two text files and report the total number of actors and actresses and total number of unique movies that these actors and actresses have acted in.

<h2>1.1     Directed actor/actress network creation</h2>

We will use the processed text file to create the directed actor/actress network. The nodes of the network are the actor/actress and there are weighted edges between the nodes in the network. The weights of the edges are given by equation 1

(1)

where <em>S<sub>i </sub></em>is the set of movies in which actor/actress <em>v<sub>i </sub></em>has acted in and <em>S<sub>j </sub></em>is the set of movies in which actor/actress <em>v<sub>j </sub></em>has acted in.

Question 2: Create a weighted directed actor/actress network using the processed text file and equation 1. Plot the in-degree distribution of the actor/actress network. Briefly comment on the in-degree distribution.

<h2>1.2     Actor pairings</h2>

In this section, we will try to find the pairings between actors. We will consider the following 10 actors:

<ul>

 <li>Tom Cruise</li>

 <li>Emma Watson (II)</li>

 <li>George Clooney</li>

 <li>Tom Hanks</li>

 <li>Dwayne Johnson (I)</li>

 <li>Johnny Depp</li>

 <li>Will Smith (I)</li>

 <li>Meryl Streep</li>

 <li>Leonardo DiCaprio</li>

 <li>Brad Pitt</li>

</ul>

Question 3: Design a simple algorithm to find the actor pairings. To be specific, your algorithm should take as input one of the actors listed above and should return the name of the actor with whom the input actor prefers to work the most. Run your algorithm for the actors listed above and report the actor names returned by your algorithm. Also for each pair, report the (input actor, output actor) edge weight. Does all the actor pairing make sense?

<h2>1.3     Actor rankings</h2>

In this section, we will extract the top 10 actor/actress from the network.

Question 4: Use the google’s pagerank algorithm to find the top 10 actor/actress in the network. Report the top 10 actor/actress and also the number of movies and the in-degree of each of the actor/actress in the top 10 list. Does the top 10 list have any actor/actress listed in the previous section? If it does not have any of the actor/actress listed in the previous section, please provide an explanation for this phenomenon.

Question 5: Report the pagerank scores of the actor/actress listed in the previous section. Also, report the number of movies each of these actor/actress have acted in and also their in-degree.

<h1>2      Movie network</h1>

In this part, we will create an undirected movie network and then explore the various structural properties of the network.

<h2>2.1     Undirected movie network creation</h2>

We will use the processed text files from the previous section to create the movie network. The nodes of the network are the movies and there are weighted edges between the nodes in the network. To reduce the size of the network, we will only consider movies that has at least 5 actor/actress in it. The weights of the edges are given by equation 2

(2)

where <em>A<sub>i </sub></em>is the set of actors in movie <em>v<sub>i </sub></em>and <em>A<sub>j </sub></em>is the set of actors in movie <em>v<sub>j</sub></em>. Since,

<em>w<sub>i</sub></em>→<em>j </em>= <em>w<sub>j</sub></em>→<em>i</em>

so we have an undirected network.

Question 6: Create a weighted undirected movie network using equation 2. Plot the degree distribution of the movie network. Briefly comment on the degree distribution.

<h2>2.2     Communities in the movie network</h2>

In this part, we will extract the communities in the movie network and explore their relationship with the movie genre. For this part you will need to load the <strong>movie_genre.txt </strong>file.

Question 7: Use the Fast Greedy community detection algorithm to find the communities in the movie network. Pick 10 communities and for each community plot the distribution of the genres of the movies in the community.

Question 8(a): In each community determine the most dominant genre based simply on frequency counts. Which generes tend to be the most frequent dominant ones across communities and why?

Question 8(b): In each community, for the <em>i<sup>th </sup></em>genre assign a score of  where: <em>c</em>(<em>i</em>) is the number of movies belonging to genre <em>i </em>in

the community; <em>p</em>(<em>i</em>) is the fraction of genre <em>i </em>movies in the community, and <em>q</em>(<em>i</em>) is the fraction of genre <em>i </em>movies in the entire data set. Now determine the most dominant genre in each communitiy based on the modified scores. What are your findings and how do they differ from the results in 8(a).

Question 8(c): Find a community of movies that has size between 10 and 20. Determine all the actors who acted in these movies and plot the corresponding bipartite graph (i.e. restricted to these particular movies and actors). Determine three most important actors and explain how they help form the community. Is there a correlation between these actors and the dominant genres you found for this community in 8(a) and 8(b).

<h2>2.3     Neighborhood analysis of movies</h2>

In this part of the project, you will need to load the <strong>movie_rating.txt </strong>file and we will explore the neighborhood of the following 3 movies:

<ul>

 <li>Batman v Superman: Dawn of Justice (2016); Rating: 6.6</li>

 <li>Mission: Impossible – Rogue Nation (2015); Rating: 7.4</li>

 <li>Minions (2015); Rating: 6.4</li>

</ul>

Question 9: For each of the movies listed above, extract it’s neighbors and plot the distribution of the available ratings of the movies in the neighborhood. Is the average rating of the movies in the neighborhood similar to the rating of the movie whose neighbors have been extracted? In this question, you should have 3 plots.

Question 10: Repeat question 10, but now restrict the neighborhood to consist of movies from the same community. Is there a better match between the average rating of the movies in the restricted neighborhood and the rating of the movie whose neighbors have been extracted. In this question, you should have 3 plots.

Question 11: For each of the movies listed above, extract it’s top 5 neighbors and also report the community membership of the top 5 neighbors.

In this question, the sorting is done based on the edge weights.

<h2>2.4     Predicting ratings of movies</h2>

In this part of the project, we will explore various rating prediction techniques to predict the ratings of the following 3 movies:

<ul>

 <li>Batman v Superman: Dawn of Justice (2016)</li>

 <li>Mission: Impossible – Rogue Nation (2015)</li>

 <li>Minions (2015)</li>

</ul>

Question 12: Train a regression model to predict the ratings of movies: for the training set you can pick any subset of movies with available ratings as the target variables; you have to specify the exact feature set that you use to train the regression model and report the root mean squared error (RMSE). Now use this trained model to predict the ratings of the 3 movies listed above (which obviously should not be included in your training data).

We will now predict the ratings of the movies using a different approach. To be specific, we will use a bipartite graph approach for rating prediction. In a bipartite graph, <em>G </em>= (<em>V,E</em>), we have a partition of the vertex set such that

<em>V</em><sub>1 </sub>∪ <em>V</em><sub>2 </sub>= <em>V V</em><sub>1 </sub>∩ <em>V</em><sub>2 </sub>= ∅

and

<em>e</em><em>ij </em>= (<em>v</em><em>i</em><em>,v</em><em>j</em>)

where <em>v<sub>i </sub></em>∈ <em>V</em><sub>1 </sub>and <em>v<sub>j </sub></em>∈ <em>V</em><sub>2</sub>. In a bipartite graph, vertices belonging to the same partitioned set are non-adjacent.

In this project, we will create a bipartite graph in the following manner:

<ul>

 <li><em>V</em><sub>1 </sub>represents the set of actor/actresses</li>

 <li><em>V</em><sub>2 </sub>represents the set of movies</li>

 <li>There is an edge <em>e<sub>ij </sub></em>between a node in <em>V</em><sub>1 </sub>and <em>V</em><sub>2 </sub>if the actor <em>i </em>has acted in movie <em>j</em></li>

</ul>

Question 13: Create a bipartite graph following the procedure described above. Determine and justify a metric for assigning a weight to each actor. Then, predict the ratings of the 3 movies using the weights of the actors in the bipartite graph. Report the RMSE. Is this rating mechanism better than the one in question 12? Justify your answer.