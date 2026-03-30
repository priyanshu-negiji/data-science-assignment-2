## Movie Data Analysis
**Introduction**
This notebook performs an exploratory data analysis on a movie dataset to uncover insights related to movie profitability, language performance, genre distribution, key personnel (producers, directors), and actors' impact.

**Data Source**
The analysis is based on the imdb_data.csv dataset, which contains various attributes of movies including budget, revenue, genres, cast, crew, and more.

## Analysis and Key Findings

### 1. Movie with Highest Profit, Director, Producer, and Actors
**Question:** Which movie made the highest profit? Who were its producer and director? Identify the actors in that film.

**Method:**
1. Filtered movies with a budget greater than 0.
2. Calculated `profit` as `revenue - budget`.
3. Defined helper functions to extract director, producer, and actors from the 'crew' and 'cast' columns, which contain string representations of lists of dictionaries.
4. Identified the movie with the maximum profit using `idxmax()`.

**Key Finding:**
- **Movie:** Furious 7
- **Director:** James Wan
- **Producer:** Vin Diesel
- **Actors:** Vin Diesel, Paul Walker, Dwayne Johnson, Michelle Rodriguez, Tyrese Gibson, Ludacris, Jordana Brewster, Djimon Hounsou, Tony Jaa, Ronda Rousey, Nathalie Emmanuel, Kurt Russell, Jason Statham, Sung Kang, Gal Gadot, Lucas Black, Elsa Pataky, Noel Gugliemi, John Brotherton, Luke Evans, Ali Fazal, Miller Kimsey, Charlie Kimsey, Eden Estrella, Gentry White, Iggy Azalea, Jon Lee Brody, Levy Tran, Anna Colwell, Viktor Hernandez, Steve Coulter, Robert Pralgo, Antwan Mills, J.J. Phillips, Jorge Ferragut, Sara Sohn, Benjamin Blankenship, D.J. Hapa, T-Pain, Brian Mahoney, Brittney Alger, Romeo Santos, Jocelin Donahue, Stephanie Langston, Jorge-Luis Pallo, Tego Calderón, Nathalie Kelley, Shad Moss, Don Omar, Klement Tinaj, Caleb Walker, Cody Walker
- **Profit:** 1,316,249,360 USD

### 2. Language with the Highest Average ROI
**Question:** Which language has the highest average ROI (return on investment)?

**Method:**
1. Calculated `ROI` as `profit / budget`.
2. Grouped the DataFrame by `original_language` and calculated the mean `ROI`.
3. Sorted the results in descending order.

**Key Finding:**
- The language with the highest average ROI is **Korean (ko)**, with an average ROI of approximately 381,794.1.

### 3. Unique Movie Genres
**Question:** Find out the unique genres of movies in this dataset.

**Method:**
1. Iterated through the 'genres' column, which contains string representations of lists of dictionaries.
2. Used `ast.literal_eval` to safely parse these strings into lists.
3. Extracted the 'name' of each genre and added it to a set to ensure uniqueness.

**Key Finding:**
- The unique genres found in the dataset are: {'Comedy', 'TV Movie', 'Family', 'Horror', 'Fantasy', 'Music', 'Drama', 'Foreign', 'Mystery', 'War', 'Documentary', 'Thriller', 'Adventure', 'Romance', 'History', 'Animation', 'Action', 'Crime', 'Western', 'Science Fiction'}.

### 4. Top 3 Producers by Average ROI
**Question:** Make a table of all the producers and directors of each movie. Find the top 3 producers who have produced movies with the highest average RoI?

**Method:**
1. Extracted director and producer names using the previously defined helper functions.
2. Grouped the DataFrame by `producer` and calculated the mean `ROI`.
3. Sorted the results in descending order and selected the top 3.

**Key Finding:**
- The top 3 producers by average ROI are:
  - **Jang Jin:** 4,197,475.625
  - **Charlie Chaplin:** 2,833,337.500
  - **Marc Bienstock:** 999,999.000

### 5. Actor in Most Movies and Their Corresponding Movie Profits
**Question:** Which actor has acted in the most number of movies? Deep dive into the movies, genres and profits corresponding to this actor.

**Method:**
1. Used `explode()` on the 'actors' column to get a series of all individual actors.
2. Counted the occurrences of each actor to find the one with the most movie appearances.
3. Filtered the DataFrame to show movies featuring this top actor and displayed their titles and profits.

**Key Finding:**
- The actor who has acted in the most movies is **Samuel L. Jackson**.
- His movies and their profits include:
  - Changing Lanes: 49,935,764
  - The Hateful Eight: 111,760,117
  - Coming to America: 249,752,301
  - Star Wars: Episode III - Revenge of the Sith: 737,000,000
  - The Avengers: 1,299,557,910
  - Jumper: 137,231,186
  - Shaft: 61,196,498
  - Snakes on a Plane: 29,022,014
  - RoboCop: 122,688,965
  - Jurassic Park: 857,100,000
  - Star Wars: Episode II - Attack of the Clones: 529,398,328
  - Captain America: The Winter Soldier: 544,766,572
  - Jackie Brown: 27,673,162
  - Big Game: -1,000,000
  - Black Snake Moan: -4,096,154
  - Sea of Love: 91,879,513
  - Deep Blue Sea: 13,648,228
  - Basic: -7,207,439
  - The Incredibles: 539,442,092
  - Avengers: Age of Ultron: 1,125,403,694
  - Out of Sight: 29,745,568
  - Patriot Games: 133,051,587
  - S.W.A.T.: 36,643,346
  - Freedomland: -23,009,372
  - The Long Kiss Goodnight: 24,456,761

### 6. Top 3 Directors' Preferred Actors
**Question:** Top 3 directors prefer which actors the most?

**Method:**
1. Identified the top 3 directors based on the count of movies they directed.
2. For each of these directors, filtered their movies.
3. Exploded the 'actors' column for their movies and counted the appearances of each actor.
4. Displayed the top actor for each director.

**Key Finding:**
- **Steven Spielberg's** most frequent actor: Harrison Ford (3 movies)
- **Clint Eastwood's** most frequent actor: Clint Eastwood (6 movies)
- **Ron Howard's** most frequent actor: Clint Howard (4 movies)

## by
priyanshu negi

