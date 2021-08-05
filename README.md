# lichess-ratings-to-openings-analysis

When looking for a new opening to play, the first thing I did was to search for the opening which is statisically the best. Unfortunately, the only
[results](https://thechessworld.com/articles/openings/chess-statistics-top-10-best-openings-for-white-and-black/) I could 
find were based on GMs. Unfortunately, [I](https://lichess.org/@/jhadden04) am not a GM, so this advice didn't really apply to me, so I had to go back to the drawing board.

The solution was to use the [lichess database](https://database.lichess.org/) and parse 5,000,000 games and their openings and find the win percentage
of each opening for each rating band.

### What is it?
This is a series of graphs that illustrate the win rates of the most successful openings for various different Lichess ratings. Also, there is information on the 
most used openings for the various rating bands and their win rates. As well as this, there is info on the most popular openings for the rating bands
The X axis show the rating bands, the Y axis show the win rate of the opening.

# Results

*To see the axis: turn on light mode or click on the graphs and view them in another tab*
*[Reddit post](https://www.reddit.com/r/chess/comments/oy11q4/i_looked_at_5_million_games_to_see_which_were_the/)*
*To see all the graphs as well as the raw data, look at the .ipynb*

  
## Most Successful Openings in Each Rating Band
Bar Graphs of Win Rate of most successful openings for each rating band| Line Graphs of Win rate of most successful openings for all rating bands
-----------|------------
![image](https://user-images.githubusercontent.com/59323260/128209082-e01b29d0-dea0-43d3-ad35-b7c3ce614eaa.png)|![image](https://user-images.githubusercontent.com/59323260/128210063-20165b35-65cc-4c53-a519-c8c254f29c56.png)
![image](https://user-images.githubusercontent.com/59323260/128209164-b29d00ca-ae5d-47c7-9163-7629524f46eb.png)|![image](https://user-images.githubusercontent.com/59323260/128210078-d341093c-65f7-4d42-b005-2ebfe41e600d.png)
![image](https://user-images.githubusercontent.com/59323260/128209190-d84d4355-eced-4e40-b04d-d90e6c1a967a.png)|![image](https://user-images.githubusercontent.com/59323260/128210089-2fb6464e-2804-4432-a03b-508321c9756c.png)
![image](https://user-images.githubusercontent.com/59323260/128209223-a0c2080a-8dd4-480f-aefd-1a6de0f8477b.png)|![image](https://user-images.githubusercontent.com/59323260/128210104-693f03cf-5f8a-40b2-bc36-1050cdf60946.png)

Some interesting things to discuss here:

### Left hand side graphs
* The Queen's, King's and Danish Gambits are all very successful, in the lower two bands, but as you reach the higher two bands, especially with the King's gambit, the negative of the lost pawn outweigh the initiative advantages, due to the higher level of gameplay. This suggests if you are in one of these lowers levels you should have one of these
openings in your repertoire.
* However, it is slightly misleading, as "Queen's Gambit" refers to a series of moves that aren't really in the opening book, so it doesn't go to "Declined" or "Accepted", which shows why it could be extra successful. Furthermore, The Queen's Gambit isn't that successful, as you are discounting that most of the time you will go to the less successful declined variation.
* It is interesting to see that the two extreme bands have decidedly more simple and complex openings than the middle two.
* The average win rate of the openings on each rating band are pretty similar throughout: broadly staying between 0.5 and 0.54.

### Right hand side graphs
* For the top rating band, the average win rate of the openings seem to trend upwards, showing these openings are only effective with a higher level of skill. In addition, the lower rating band's opening's win rate seems to trend down and the middle two bands form more of an arch.
* The movement of the opening win rate lines in the top rating bands are much less sporadic.
  
## Most Popular Openings in Each Rating Band
Line Graphs of Most Popular openings for each rating band | Line Graphs of win rate of most popular openings for all rating bands
------------ | -------------
![image](https://user-images.githubusercontent.com/59323260/128211807-00660d0c-fa53-4aa4-99a0-fd81600caf1e.png) |![image](https://user-images.githubusercontent.com/59323260/128212424-e1d44e33-cfa8-4998-a7f7-cc8346437dfd.png)
![image](https://user-images.githubusercontent.com/59323260/128211880-5dc7729b-8fef-4447-9a52-db3e98f3dd98.png) |![image](https://user-images.githubusercontent.com/59323260/128212450-b7ad25a7-2fa6-4c74-9bfe-4c38a6616462.png)
![image](https://user-images.githubusercontent.com/59323260/128211939-787a1cd1-3f46-4d4f-8e84-a56c2519475c.png) |![image](https://user-images.githubusercontent.com/59323260/128212472-23fd7d06-9cf1-43ef-ab2f-2aefa8ae6723.png)
![image](https://user-images.githubusercontent.com/59323260/128211967-94c6c035-666e-4e94-abf8-de7db5a17257.png) |![image](https://user-images.githubusercontent.com/59323260/128212489-709b5a3f-0fa7-42d5-8770-71a7c3e797d5.png)

Some more intriguing things to discuss:

### Left hand side graphs
* Apart from the lowest rating band, the most popular openings overall are Sicilian, French and Scandinavian. This isn't surprising, as these openings are defined by the first move, whereas, something like Ruy Lopez has to wait until the third until Lichess defines it as the game's opening.
* The Van't Kruijs e3, which leaves white with 0.0 engine eval, rather than e4's 0.3, is broadly thought of as unusual and pointless. This shows that at the low level rating, with a small knowledge of opening theory, why the lowest rating band plays the Van't Kruijs
* The Caro-Kann is only played at the higher rating bands, suggesting it has a higher skill level to be played effectively
* Openings like Ruy Lopez, QGD, English Opening, Italian Game, Bishop's Opening, Scotch Game and Four Knights are continuously popular white openings in all rating bands.

### Right hand side graphs
*It should be noted that these graphs are on the most popular overall ratings and aren't related to the rating bands*
*Also, the popularity of each opening is ordered from top to bottom on the legends*
* The Caro-Kann was primarily used by the higher rating bands and is more successful in the higher rating bands.
* These openings average at more like 50% win rate for white, showing they aren't as successful.
* The Sicilian and The French are similarly effective for black, but The Scandinavian is less successful until the highest rating bands.
* On the bottom graph, QGD is a bit of an anomaly for 600-1000, as it is much higher than normal. This is because in the 600-1000 rating band, much less games are played and there are much less players, meaning the results are less reliable as there is a smaller dataset.

## How does it work?

I downloaded 5,000,000 games (in pgn form) from the [Lichess database](https://database.lichess.org/), extracted them using bz2 and then wrote a program to go through these games and filter them for unecessary things like the moves and took the important things like the opening information and the game result and put it onto a JSON file, which was many magnitudes smaller than the original download, meaning when I did the actual parsing, it was much more efficient, finishing in mere seconds. 

The basic premise of the script was to count how many wins and losses each opening got in each opening band, but before this, I had to define what was an opening? Due to the complicated nature of chess, you can get very complex openings like "Queen's Gambit Accepted: Central Variation, Greco Variation", which I got in a recent game. This is a problem, as this opening isn't going to occur thousands of times in each rating band to get the reliabilty we need. The solution was to cut the variations away from the opening,  meaning that rare opening was now the popular "Queen's Gambit Accepted. 

From there, it was just the simple matter of organising openings into their respective rating bands, finding their win ratios and finally organising the data into graphs using matplotlib.

## Limitiations
* Google Colabatory

I decided to use ipynb in Google Colab as I like the freedom and simplicity it provides. Unfortunately, there were some downsides. Firstly, to import a file into Google Colab, it has to be from your Google drive, which means space was limited. This meant I only ended up using one month's worth of games from 2017, as that was a managable size, due to there being less games played. This leads to a smaller dataset and less reliable results. Furthermore, Google Colab has a timeout after 8ish hours, so if you want to parse a very large original download, you may end up being timed-out, meaning you lose your progress
 

## Looking Forward
* Speed

This was never a particularly optimised script and there are lots of improvements possible, for example using a database rather than a crude textfile
* Opening Variations

As I mentioned earlier, I had to ignore any opening variations for reliability's sake, but this would be an interesting avenue to explore, especially in openings like the Sicilian where, there are many variations which have been extensively studied.

* Working with Black's openings

I have tried cloning the code to work with black, but unfortunately, it isn't that simple, as it is much trickier to differentiate the best openings for black from the worst openings for white, whereas vice-versa, it was quite simple and easy. A possible solution, which also applies to the variations, is to use the ECO categorisation.
