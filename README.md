# SQLZoo-Exercise
Save code place for each exercise
https://sqlzoo.net/wiki/SELECT_from_WORLD_Tutorial

SELECT basics 
 
1/ The example uses a WHERE clause to show the population of 'France'. Note that strings (pieces of text that are data) should be in 'single quotes';
Modify it to show the population of Germany
Answer : select population from world where name = 'Germany'

2/ Checking a list The word IN allows us to check if an item is in a list. The example shows the name and population for the countries 'Brazil', 'Russia', 'India' and 'China'.
Show the name and the population for 'Sweden', 'Norway' and 'Denmark'.
Answer : SELECT name, population FROM world WHERE name in ('Sweden','Norway','Denmark')

3/Which countries are not too small and not too big? BETWEEN allows range checking (range specified is inclusive of boundary values). The example below shows countries with an area of 250,000-300,000 sq. km. Modify it to show the country and the area for countries with an area between 200,000 and 250,000.
Answer : SELECT name, area FROM world WHERE area BETWEEN 200000 AND 250000






Quiz

1/ 
 
Answer : SELECT name, population
  FROM world
 WHERE population BETWEEN 1000000 AND 1250000

2/ Pick the result you would obtain from this code: 
     SELECT name, population
      FROM world
      WHERE name LIKE "Al%"

Answer : 
Albania	3200000
Algeria	32900000
3. Select the code which shows the countries that end in A or L
Answer :SELECT name FROM world
 WHERE name LIKE '%a' OR name LIKE '%l'

4. Pick the result from the query
SELECT name,length(name)
FROM world
WHERE length(name)=5 and region='Europe'
Answer : 
name	length(name)
Italy	5
Malta	5
Spain	5

5. Here are the first few rows of the world table:
name	region	area	population	gdp
Afghanistan	South Asia	652225	26000000	
Albania	Europe	28728	3200000	6656000000
Algeria	Middle East	2400000	32900000	75012000000
Andorra	Europe	468	64000	
...
Pick the result you would obtain from this code: 
SELECT name, area*2 FROM world WHERE population = 64000
Answer : 
Andorra	936

6. Select the code that would show the countries with an area larger than 50000 and a population smaller than 10000000
Answer : SELECT name, area, population
  FROM world
 WHERE area > 50000 AND population < 10000000

7. Select the code that shows the population density of China, Australia, Nigeria and France
Answer : SELECT name, population/area
  FROM world
 WHERE name IN ('China', 'Nigeria', 'France', 'Australia')

 
SELECT from world
 
1/ Read the notes about this table. Observe the result of running this SQL command to show the name, continent and population of all countries.
 Answer : SELECT name, continent, population FROM world

2/ How to use WHERE to filter records. Show the name for the countries that have a population of at least 200 million. 200 million is 200000000, there are eight zeros.
Answer : SELECT name FROM world
WHERE population >= 200000000

3/ Give the name and the per capita GDP for those countries with a population of at least 200 million. 
HELP:How to calculate per capita GDP
Answer : SELECT name, GDP/population FROM world WHERE population >= 200000000

4/ Show the name and population in millions for the countries of the continent'South America'. Divide the population by 1000000 to get population in millions.
Answer : SELECT name, population/1000000 FROM world WHERE continent ='South America'

5/ Show the name and population for France, Germany, Italy
Answer : SELECT name, population FROM world WHERE name IN ('France','Germany','Italy')

6/ Show the countries which have a name that includes the word 'United'
Answer : SELECT name FROM world WHERE name like 'United%'

7/ Two ways to be big: A country is big if it has an area of more than 3 million sq km or it has a population of more than 250 million.
Show the countries that are big by area or big by population. Show name, population and area.
Answer : SELECT name, population, area FROM world WHERE area > 3000000 OR population > 250000000

8/ Exclusive OR (XOR). Show the countries that are big by area or big by population but not both. Show name, population and area.
●	Australia has a big area but a small population, it should be included.
●	Indonesia has a big population but a small area, it should be included.
●	China has a big population and big area, it should be excluded.
●	United Kingdom has a small population and a small area, it should be excluded.
Answer : SELECT name, population,area FROM world WHERE area > 3000000 XOR population > 250000000

9/ Show the name and population in millions and the GDP in billions for the countries of the continent 'South America'. Use the ROUND function to show the values to two decimal places.
For South America show population in millions and GDP in billions both to 2 decimal places.
Millions and billions
Answer : SELECT name, ROUND(population/1000000,2), ROUND(gdp/1000000000,2) FROM world WHERE continent like 'South America'
10/ Show the name and per-capita GDP for those countries with a GDP of at least one trillion (1000000000000; that is 12 zeros). Round this value to the nearest 1000.
Show per-capita GDP for the trillion dollar countries to the nearest $1000.
Answer : SELECT name, ROUND(gdp/population,-3) FROM world WHERE gdp>1000000000000

11/  Greece has capital Athens.
Each of the strings 'Greece', and 'Athens' has 6 characters.
Show the name and capital where the name and the capital have the same number of characters.
●	You can use the LENGTH function to find the number of characters in a string
Answer : SELECT name, capital FROM world WHERE LENGTH(name)=LENGTH(capital)

12/ The capital of Sweden is Stockholm. Both words start with the letter 'S'.
Show the name and the capital where the first letters of each match. Don't include countries where the name and the capital are the same word.
●	You can use the function LEFT to isolate the first character.
●	You can use <> as the NOT EQUALS operator.
Answer : SELECT name, capital
FROM world
WHERE LEFT(name,1) like LEFT(capital,1) AND name <> capital

13/Equatorial Guinea and Dominican Republic have all of the vowels (a e i o u) in the name. They don't count because they have more than one word in the name.
Find the country that has all the vowels and no spaces in its name.
●	You can use the phrase name NOT LIKE '%a%' to exclude characters from your results.
●	The query shown misses countries like Bahamas and Belarus because they contain at least one 'a'
Answer : SELECT name
   FROM world
WHERE name LIKE ('_o_a%i%e') 
name
Mozambique

 
1. Select the code which gives the name of countries beginning with U
Answer : SELECT name
  FROM world
 WHERE name
 BEGIN with U
2. Select the code which shows just the population of United Kingdom?
Answer : SELECT population
  FROM world
 WHERE name = 'United Kingdom'

3. Select the answer which shows the problem with this SQL code - the intended result should be the continent of France:
SELECT continent 
   FROM world 
  WHERE 'name' = 'France'
Answer : 'name' should be name

4. Select the result that would be obtained from the following code: 
SELECT name, population / 10 
  FROM world 
 WHERE population < 10000
Answer : 
Nauru	990

5. Select the code which would reveal the name and population of countries in Europe and Asia
Answer: SELECT name, population
  FROM world
 WHERE continent IN ('Europe', 'Asia')

6. Select the code which would give two rows
Answer : SELECT name FROM world
 WHERE name IN ('Cuba', 'Togo')

7. Select the result that would be obtained from this code: 
SELECT name FROM world
 WHERE continent = 'South America'
   AND population > 40000000
Answer : 
Brazil
Colombia

SELECT from nobel
Language:
English  • 中文

yr	subject	winner		
1960	Chemistry	Willard F. Libby		
1960	Literature	Saint-John Perse		
1960	Medicine	Sir Frank Macfarlane Burnet		
1960	Medicine	Peter Madawar		
...
Contents
 [hide] 
1nobel Nobel Laureates
2Winners from 1950
31962 Literature
4Albert Einstein
5Recent Peace Prizes
6Literature in the 1980's
7Only Presidents
8John
9Chemistry and Physics from different years
10Exclude Chemists and Medics
11Early Medicine, Late Literature
12Harder Questions
13Umlaut
14Apostrophe
15Knights of the realm
16Chemistry and Physics last
nobel Nobel Laureates
We continue practicing simple SQL queries on a single table.
This tutorial is concerned with a table of Nobel prize winners:
nobel(yr, subject, winner)
Using the SELECT statement.
1/ Change the query shown so that it displays Nobel prizes for 1950
Answer : SELECT *
FROM nobel
WHERE yr=1950

2/ Show who won the 1962 prize for Literature.
Answer : SELECT winner
FROM nobel
WHERE yr=1962 AND subject ='Literature'

3/ Show the year and subject that won 'Albert Einstein' his prize.
Answer : SELECT yr, subject
FROM nobel
WHERE winner = 'Albert Einstein'

4/ Give the name of the 'Peace' winners since the year 2000, including 2000.
Answer : SELECT winner
FROM nobel
WHERE yr >= 2000 AND subject = 'Peace'

5/ Show all details (yr, subject, winner) of the Literature prize winners for 1980 to 1989 inclusive.
Answer : SELECT *
FROM nobel
WHERE subject = 'Literature' AND yr BETWEEN 1980 AND 1989

6/ Show all details of the presidential winners:
●	Theodore Roosevelt
●	Woodrow Wilson
●	Jimmy Carter
●	Barack Obama
Answer : SELECT *
FROM nobel
WHERE winner IN ('Theodore Roosevelt','Woodrow Wilson','Jimmy Carter','Barack Obama')

7/ Show the winners with first name John
Answer : SELECT winner
FROM nobel
WHERE winner LIKE ('John%')
8/ Show the year, subject, and name of Physics winners for 1980 together with the Chemistry winners for 1984.
Answer : SELECT *
FROM nobel
WHERE (subject = 'Physics' AND yr=1980) OR (subject ='Chemistry' AND yr=1984)

9/ Show the year, subject, and name of winners for 1980 excluding Chemistry and Medicine
Answer : SELECT *
FROM nobel
WHERE yr=1980 AND subject NOT LIKE ('Chemistry') AND subject NOT LIKE ('Medicine')

10/ Show year, subject, and name of people who won a 'Medicine' prize in an early year (before 1910, not including 1910) together with winners of a 'Literature' prize in a later year (after 2004, including 2004)
Answer : SELECT *
FROM nobel
WHERE (subject = 'Medicine' AND yr < 1910) OR (subject = 'Literature' AND yr >= 2004)

11/ Find all details of the prize won by PETER GRÜNBERG
Non-ASCII characters
Answer : SELECT *
FROM nobel
WHERE winner = 'PETER GRÜNBERG'

12/ Find all details of the prize won by EUGENE O'NEILL
Escaping single quotes
Answer : SELECT *
FROM nobel
WHERE winner LIKE 'EUGENE%' AND winner LIKE '%NEILL'

13/ Knights in order
List the winners, year and subject where the winner starts with Sir. Show the the most recent first, then by name order.
Answer : SELECT winner, yr, subject
FROM nobel
WHERE winner LIKE ('Sir%')
ORDER BY yr DESC, winner ASC

14/ The expression subject IN ('Chemistry','Physics') can be used as a value - it will be 0 or 1.
Show the 1984 winners and subject ordered by subject and winner name; but list Chemistry and Physics last.
Answer :
SELECT winner, subject
  FROM nobel
 WHERE yr=1984
ORDER BY subject IN ('Chemistry','Physics'), subject, winner
Quiz
 
1. Pick the code which shows the name of winner's names beginning with C and ending in n
Answer : SELECT winner FROM nobel
 WHERE winner LIKE 'C%' AND winner LIKE '%n'

2. Select the code that shows how many Chemistry awards were given between 1950 and 1960
Answer : SELECT COUNT(subject) FROM nobel
 WHERE subject = 'Chemistry'
   AND yr BETWEEN 1950 and 1960

3. Pick the code that shows the amount of years where no Medicine awards were given
Answer : SELECT COUNT(DISTINCT yr) FROM nobel
 WHERE yr NOT IN (SELECT DISTINCT yr FROM nobel WHERE subject = 'Medicine')

4. Select the result that would be obtained from the following code:
SELECT subject, winner FROM nobel WHERE winner LIKE 'Sir%' AND yr LIKE '196%'
Answer : 
Medicine	Sir John Eccles
Medicine	Sir Frank Macfarlane Burnet

5. Select the code which would show the year when neither a Physics or Chemistry award was given
Answer : SELECT yr FROM nobel
 WHERE yr NOT IN(SELECT yr 
                   FROM nobel
                 WHERE subject IN ('Chemistry','Physics'))

6. Select the code which shows the years when a Medicine award was given but no Peace or Literature award was
Answer : SELECT DISTINCT yr
  FROM nobel
 WHERE subject='Medicine' 
   AND yr NOT IN(SELECT yr FROM nobel 
                  WHERE subject='Literature')
   AND yr NOT IN (SELECT yr FROM nobel
                   WHERE subject='Peace')

7. Pick the result that would be obtained from the following code:
SELECT subject, COUNT(subject) 
   FROM nobel 
  WHERE yr ='1960' 
  GROUP BY subject
Answer : 
Chemistry	1
Literature	1
Medicine	2
Peace	1
Physics	1

SELECT in SELECT
 
Using nested SELECT
Summary
Contents
 [hide] 
1Exercises
2Bigger than Russia
3Richer than UK
4Neighbours of Argentina and Australia
5Between Canada and Poland
6Percentages of Germany
7Bigger than every country in Europe
8Largest in each continent
9First country of each continent (alphabetically)
10Difficult Questions That Utilize Techniques Not Covered In Prior Sections
1. List each country name where the population is larger than that of 'Russia'.
world(name, continent, area, population, gdp)
Answer : SELECT name
FROM world
WHERE population > ( SELECT population FROM world WHERE name LIKE 'Russia')

2. Show the countries in Europe with a per capita GDP greater than 'United Kingdom'.Per Capita GDP
The per capita GDP is the gdp/population
Answer : SELECT name
FROM world
WHERE gdp/population > (SELECT gdp/population FROM world WHERE name ='United Kingdom') AND continent = 'Europe'

3. List the name and continent of countries in the continents containing either Argentina or Australia. Order by name of the country.
Answer : 
Step 1: Run this script to search continent of 2 countries (Argentina and Australia)
SELECT name, continent
FROM world
WHERE name IN ('Argentina’,’Australia’)
Step 2 : Get result which is helpful to get all countries of 2 continents
SELECT name, continent
FROM world
WHERE continent IN ('South America','Oceania')
ORDER BY name

4. Which country has a population that is more than Canada but less than Poland? Show the name and the population.
Answer : SELECT name, population
FROM world
WHERE population > (SELECT population FROM world WHERE name ='Canada')
AND population < (SELECT population FROM world WHERE name = 'Poland')

5.Germany (population 80 million) has the largest population of the countries in Europe. Austria (population 8.5 million) has 11% of the population of Germany.
Show the name and the population of each country in Europe. Show the population as a percentage of the population of Germany.
Decimal places
You can use the function ROUND to remove the decimal places.
Percent symbol %
You can use the function CONCAT to add the percentage symbol.
Answer : We need to divide into 3 steps
First, get population of Germany to compare
SELECT name,population
FROM world
WHERE name = ‘Germany'
Second, try with ROUND to get percent of population/ population of germany
SELECT name,ROUND(population/80716000*100,0)
FROM world
WHERE continent = 'Europe'
Third, try more with CONCAT
SELECT name, CONCAT(ROUND(population/80716000*100,0),'%')
FROM world
WHERE continent = 'Europe'

6. Which countries have a GDP greater than every country in Europe? [Give the nameonly.] (Some countries may have NULL gdp values)
We can refer to values in the outer SELECT within the inner SELECT. We can name the tables so that we can tell the difference between the inner and outer versions.
https://www.essentialsql.com/what-is-the-difference-between-an-inner-and-outer-join/
Answer : 
Step 1: Find which maximum of gdp in Europe. 
SELECT name, gdp
FROM world
WHERE comtinent = ‘Europe'
ORDER BY gdp
Get max[gdp] = 3425956000000
Step 2: Find countries has gdp, without NULL value for gdp
SELECT name
FROM world
WHERE gdp > 3425956000000 AND gdp NOT LIKE ‘NULL'

We can refer to values in the outer SELECT within the inner SELECT. We can name the tables so that we can tell the difference between the inner and outer versions.
7. Find the largest country (by area) in each continent, show the continent, the nameand the area:
Answer :
SELECT x.continent, x.name, x.area
FROM world AS x
WHERE x.area = (
  SELECT MAX(y.area)
  FROM world AS y
  WHERE x.continent = y.continent)

8. List each continent and the name of the country that comes first alphabetically.
Answer :
SELECT continent, name
FROM world x
WHERE name <= ALL(SELECT name FROM world y WHERE x.continent = y.continent);

9. Difficult Questions That Utilize Techniques Not Covered In Prior Sections
Find the continents where all countries have a population <= 25000000. Then find the names of the countries associated with these continents. Show name, continentand population.
Answer :
SELECT name, continent, population FROM world WHERE continent IN (SELECT continent FROM world  x WHERE 25000000 >= (SELECT MAX(population) FROM world y WHERE x.continent = y.continent));
10. Some countries have populations more than three times that of any of their neighbours (in the same continent). Give the countries and continents.
Answer : 

quiz
Nested SELECT quiz
name	region	area	population	gdp
Afghanistan	South Asia	652225	26000000	
Albania	Europe	28728	3200000	6656000000
Algeria	Middle East	2400000	32900000	75012000000
Andorra	Europe	468	64000	
Bangladesh	South Asia	143998	152600000	67144000000
United Kingdom	Europe	242514	59600000	2022824000000
...
1. Select the code that shows the name, region and population of the smallest country in each region
Answer : SELECT region, name, population FROM bbc x WHERE population <= ALL (SELECT population FROM bbc y WHERE y.region=x.region AND population>0)
2. Select the code that shows the countries belonging to regions with all populations over 50000
Answer : SELECT name,region,population FROM bbc x WHERE 50000 < ALL (SELECT population FROM bbc y WHERE x.region=y.region AND y.population>0)
3. Select the code that shows the countries with a less than a third of the population of the countries around it
Answer : SELECT name, region FROM bbc x
 WHERE population < ALL (SELECT population/3 FROM bbc y WHERE y.region = x.region AND y.name != x.name)
4. Select the result that would be obtained from the following code: 
SELECT name FROM bbc
 WHERE population >
       (SELECT population
          FROM bbc
         WHERE name='United Kingdom')
   AND region IN
       (SELECT region
          FROM bbc
         WHERE name = 'United Kingdom')
Answer : 
France
Germany
Russia
Turkey

5. Select the code that would show the countries with a greater GDP than any country in Africa (some countries may have NULL gdp values)
Answer : SELECT name FROM bbc
 WHERE gdp > (SELECT MAX(gdp) FROM bbc WHERE region = 'Africa')
6. Select the code that shows the countries with population smaller than Russia but bigger than Denmark
Answer : SELECT name FROM bbc
 WHERE population < (SELECT population FROM bbc WHERE name='Russia')
   AND population > (SELECT population FROM bbc WHERE name='Denmark')
7. >Select the result that would be obtained from the following code: 
SELECT name FROM bbc
 WHERE population > ALL
       (SELECT MAX(population)
          FROM bbc
         WHERE region = 'Europe')
   AND region = 'South Asia'
Answer :
Bangladesh
India
Pakistan

SUM and COUNT
Contents
1World Country Profile: Aggregate functions
2You might want to look at these examples first
3Total world population
4List of continents
5GDP of Africa
6Count the big countries
7Baltic states population
8Using GROUP BY and HAVING
9Counting the countries of each continent
10Counting big countries in each continent
11Counting big continents
World Country Profile: Aggregate functions
This tutorial is about aggregate functions such as COUNT, SUM and AVG. An aggregate function takes many values and delivers just one value. For example the function SUM would aggregate the values 2, 4 and 5 to deliver the single value 11.
name	continent	area	population	gdp
Afghanistan	Asia	652230	25500100	20343000000
Albania	Europe	28748		2831741		12960000000	
Algeria	Africa	2381741		37100000		188681000000	
Andorra	Europe	468	78115		3712000000	
Angola	Africa	1246700		20609294		100990000000	
...
You might want to look at these examples first
Using SUM, Count, MAX, DISTINCT and ORDER BY.
Total world population
1.Show the total population of the world.
world(name, continent, area, population, gdp)
Answer :
SELECT SUM(population)
FROM world

2. List all the continents - just once each.
Answer :
SELECT DISTINCT continent
FROM world

3.Give the total GDP of Africa
Answer : SELECT SUM(gdp)
FROM world
WHERE continent LIKE 'Africa'

4. How many countries have an area of at least 1000000
Answer : SELECT COUNT(name)
FROM world
WHERE area >= 1000000

5. What is the total population of ('Estonia', 'Latvia', 'Lithuania')
Answer : SELECT SUM(population)
FROM world
WHERE name IN ('Estonia', 'Latvia', 'Lithuania')

6. Using GROUP BY and HAVING
You may want to look at these examples: Using GROUP BY and HAVING.
Counting the countries of each continent
Answer : SELECT continent, COUNT(name)
FROM world
GROUP BY continent

7. For each continent show the continent and number of countries with populations of at least 10 million.
Answer : SELECT continent, COUNT(name)
FROM world
WHERE population >=10000000
GROUP BY continent

8. List the continents that have a total population of at least 100 million.
Answer : SELECT continent
FROM world
GROUP BY continent
HAVING SUM(population) >= 100000000;

SUM and COUNT Quiz
The nobel table can be used to practice more SUM and COUNT functions.
The next tutorial looks at the Table Tennis database. It shows how queries may use records from two related tables.
Quiz
SUM and COUNT QUIZ

name	region	area	population	gdp
Afghanistan	South Asia	652225	26000000	
Albania	Europe	28728	3200000	6656000000
Algeria	Middle East	2400000	32900000	75012000000
Andorra	Europe	468	64000	

1. Select the statement that shows the sum of population of all countries in 'Europe'
Answer : SELECT SUM(population) FROM bbc WHERE region = 'Europe'

2. Select the statement that shows the number of countries with population smaller than 150000
Answer :SELECT COUNT(name) FROM bbc WHERE population < 150000

3. Select the list of core SQL aggregate functions
Answer : AVG(), COUNT(), MAX(), MIN(), SUM()

4. Select the result that would be obtained from the following code:
SELECT region, SUM(area)
   FROM bbc 
  WHERE SUM(area) > 15000000 
  GROUP BY region
Answer : No result due to invalid use of the WHERE function

5. Select the statement that shows the average population of 'Poland', 'Germany' and 'Denmark'
Answer : SELECT AVG(population) FROM bbc WHERE name IN ('Poland', 'Germany', 'Denmark')

6. Select the statement that shows the medium population density of each region
Answer : SELECT region, SUM(population)/SUM(area) AS density FROM bbc GROUP BY region

7. Select the statement that shows the name and population density of the country with the largest population
Answer : SELECT name, population/area AS density FROM bbc WHERE population = (SELECT MAX(population) FROM bbc)

8. Pick the result that would be obtained from the following code: 
SELECT region, SUM(area) 
   FROM bbc 
  GROUP BY region 
  HAVING SUM(area)<= 20000000
Answer : 
Americas	732240
Middle East	13403102
South America	17740392
South Asia	9437710

JOIN
The JOIN operation
 

id	mdate	stadium	team1	team2
1001	8 June 2012	National Stadium, Warsaw	POL	GRE
1002	8 June 2012	Stadion Miejski (Wroclaw)	RUS	CZE
1003	12 June 2012	Stadion Miejski (Wroclaw)	GRE	CZE
1004	12 June 2012	National Stadium, Warsaw	POL	RUS
...

matchid	teamid	player	gtime	
1001	POL	Robert Lewandowski	17	
1001	GRE	Dimitris Salpingidis	51	
1002	RUS	Alan Dzagoev	15	
1002	RUS	Roman Pavlyuchenko	82	
...

id	teamname	coach		
POL	Poland	Franciszek Smuda		
RUS	Russia	Dick Advocaat		
CZE	Czech Republic	Michal Bilek		
GRE	Greece	Fernando Santos		
...

JOIN and UEFA EURO 2012
This tutorial introduces JOIN which allows you to use data from two or more tables. The tables contain all matches and goals from UEFA EURO 2012 Football Championship in Poland and Ukraine.
The data is available (mysql format) at http://sqlzoo.net/euro2012.sql
Summary
1 . The first example shows the goal scored by a player with the last name 'Bender'. The *says to list all the columns in the table - a shorter way of saying matchid, teamid, player, gtime
Modify it to show the matchid and player name for all goals scored by Germany. To identify German players, check for: teamid = 'GER'
Answer : SELECT matchid, player FROM goal
  WHERE teamid='GER'
2. From the previous query you can see that Lars Bender's scored a goal in game 1012. Now we want to know what teams were playing in that match.
Notice in the that the column matchid in the goal table corresponds to the idcolumn in the game table. We can look up information about game 1012 by finding that row in the game table.
Show id, stadium, team1, team2 for just game 1012
Answer : SELECT id,stadium,team1,team2
  FROM game
WHERE id=1012
3. You can combine the two steps into a single query with a JOIN. 
SELECT *
  FROM game JOIN goal ON (id=matchid)

The FROM clause says to merge data from the goal table with that from the game table. The ON says how to figure out which rows in game go with which rows in goal - the idfrom goal must match matchid from game. (If we wanted to be more clear/specific we could say 
ON (game.id=goal.matchid)
The code below shows the player (from the goal) and stadium name (from the game table) for every goal scored.
Modify it to show the player, teamid, stadium and mdate for every German goal.
Answer :SELECT player, teamid, stadium, mdate
  FROM game JOIN goal ON (game.id=goal.matchid)
WHERE teamid='GER'
4. Use the same JOIN as in the previous question.
Show the team1, team2 and player for every goal scored by a player called Mario player LIKE 'Mario%'
Answer : SELECT team1, team2, player
FROM game JOIN goal ON (game.id=goal.matchid)
WHERE player LIKE 'Mario%'
5. The table eteam gives details of every national team including the coach. You can JOIN goal to eteam using the phrase goal JOIN eteam on teamid=id
Show player, teamid, coach, gtime for all goals scored in the first 10 minutes gtime<=10
Answer : SELECT player, teamid,coach,gtime
FROM goal JOIN eteam ON teamid=id
WHERE gtime <=10
6. To JOIN game with eteam you could use either
game JOIN eteam ON (team1=eteam.id) or game JOIN eteam ON (team2=eteam.id)
Notice that because id is a column name in both game and eteam you must specify eteam.id instead of just id
List the the dates of the matches and the name of the team in which 'Fernando Santos' was the team1 coach.
Answer: SELECT mdate, teamname
FROM game JOIN eteam ON (team1=eteam.id)
WHERE coach LIKE 'Fernando Santos'
7. List the player for every goal scored in a game where the stadium was 'National Stadium, Warsaw'
Answer : SELECT player
FROM game JOIN goal ON (game.id=goal.matchid)
WHERE stadium = 'National Stadium, Warsaw'
8. The example query shows all goals scored in the Germany-Greece quarterfinal.
Instead show the name of all players who scored a goal against Germany.
HINT
Select goals scored only by non-German players in matches where GER was the id of either team1 or team2.
You can use teamid!='GER' to prevent listing German players.
You can use DISTINCT to stop players being listed twice.
Answer : SELECT DISTINCT player # Get player name isn't duplicate
FROM game
JOIN goal ON goal.matchid = game.id # Get information from both 2 tables game and goal (usd keys matchid in goal and id in game to murge)
WHERE (team1 = 'GER' OR team2 = 'GER') # 
AND teamid <> 'GER'
Explain more for this question. Who scored a goal for GER team in Team1 & Team2 but who isn't German
9. Show teamname and the total number of goals scored.
COUNT and GROUP BY
You should COUNT(*) in the SELECT line and GROUP BY teamname
Answer : SELECT teamname, COUNT(teamid)
  FROM eteam JOIN goal ON id=teamid
GROUP BY teamname
10. Show the stadium and the number of goals scored in each stadium.
Answer : SELECT stadium, COUNT(player)
FROM game JOIN goal ON matchid=id
GROUP BY stadium
# Count player who scored a goal each stadium to define amount of goal for each stadium
11. For every match involving 'POL', show the matchid, date and the number of goals scored.
Answer : SELECT matchid, COUNT(player)
FROM game
JOIN goal ON goal.matchid = game.id
WHERE (team1 = 'POL' OR team2 = 'POL')
GROUP BY matchid
⇒ 
 
IF 
SELECT matchid, COUNT(player), mdate
FROM game
JOIN goal ON goal.matchid = game.id
WHERE (team1 = 'POL' OR team2 = 'POL')
GROUP BY matchid
⇒ ERROR answer
'gisq.game.mdate' isn't in GROUP BY
IF
SELECT matchid,mdate, team1, team2,teamid
  FROM game JOIN goal ON matchid = id
 WHERE (team1 = 'POL' OR team2 = 'POL')
⇒
 
SELECT matchid,mdate, COUNT(player)
  FROM game JOIN goal ON matchid = id
 WHERE (team1 = 'POL' OR team2 = 'POL')
GROUP BY matchid, mdate
12. For every match where 'GER' scored, show matchid, match date and the number of goals scored by 'GER'
Answer : 
IF
SELECT matchid, COUNT(player)
FROM game
JOIN goal ON game.id = goal.matchid
WHERE teamid = 'GER'
GROUP BY matchid
⇒  
Answer should be :
 
SELECT matchid, mdate, COUNT(player)
FROM game
JOIN goal ON game.id = goal.matchid
WHERE teamid = 'GER'
GROUP BY matchid, mdate
# How to resolve error variable in SELECT isn’t in GROUP BY
We can GROUP BY more one group, this problem is same as ORDER by with more variable
SELECT var1, var2, …
FROM table1 JOIN table 2 ON table1.key = table2.key 
WHERE condition to filter
GROUP BY var1, var2,...
13. List every match with the goals scored by each team as shown. This will use "CASE WHEN" which has not been explained in any previous exercises.
mdate	team1	score1	team2	score2
1 July 2012	ESP	4	ITA 	0
10 June 2012	ESP	1	ITA	1
10 June 2012	IRL	1	CRO	3
...
Notice in the query given every goal is listed. If it was a team1 goal then a 1 appears in score1, otherwise there is a 0. You could SUM this column to get a count of the goals scored by team1. Sort your result by mdate, matchid, team1 and team2.
Example : CASE
CASE WHEN b1 THEN v1 END
Engine	OK	Alternative
ingres	Yes	
mysql	Yes	
oracle	Yes	
postgres	Yes	
sqlserver	Yes	

CASE allows you to return different values under different conditions. 
If there no conditions match (and there is not ELSE) then NULL is returned.
 CASE WHEN condition1 THEN value1 
       WHEN condition2 THEN value2  
       ELSE def_value 
  END
Answer : SELECT mdate,
  team1,
  SUM(CASE WHEN teamid=team1 THEN 1 ELSE 0 END) score1,
  team2,
  SUM(CASE WHEN teamid=team2 THEN 1 ELSE 0 END) score2
FROM game JOIN goal ON goal.matchid = game.id
GROUP BY game.id, mdate, team1, team2
ORDER BY mdate, matchid, team1, team2
Quiz
 
1. You want to find the stadium where player 'Dimitris Salpingidis' scored. Select the JOIN condition to use:
Answer : game  JOIN goal ON (id=matchid)
2. You JOIN the tables goal and eteam in an SQL statement. Indicate the list of column names that may be used in the SELECT line:
Answer : matchid, teamid, player, gtime, id, teamname, coach
3. Select the code which shows players, their team and the amount of goals they scored against Greece(GRE).
Answer : SELECT player, teamid, COUNT(*)
  FROM game JOIN goal ON matchid = id
 WHERE (team1 = "GRE" OR team2 = "GRE")
   AND teamid != 'GRE'
 GROUP BY player, teamid
4. Select the result that would be obtained from this code: 
SELECT DISTINCT teamid, mdate
  FROM goal JOIN game on (matchid=id)
 WHERE mdate = '9 June 2012'
Answer : 
DEN	9 June 2012
GER	9 June 2012

5. Select the code which would show the player and their team for those who have scored against Poland(POL) in National Stadium, Warsaw.
Answer : SELECT DISTINCT player, teamid 
   FROM game JOIN goal ON matchid = id 
  WHERE stadium = 'National Stadium, Warsaw' 
 AND (team1 = 'POL' OR team2 = 'POL')
   AND teamid != 'POL'

6. Select the code which shows the player, their team and the time they scored, for players who have played in Stadion Miejski (Wroclaw) but not against Italy(ITA).
Answer : SELECT DISTINCT player, teamid, gtime
  FROM game JOIN goal ON matchid = id
 WHERE stadium = 'Stadion Miejski (Wroclaw)'
   AND (( teamid = team2 AND team1 != 'ITA') OR ( teamid = team1 AND team2 != 'ITA'))

7. Select the result that would be obtained from this code: 
SELECT teamname, COUNT(*)
  FROM eteam JOIN goal ON teamid = id
 GROUP BY teamname
HAVING COUNT(*) < 3
Answer : 
Netherlands	2
Poland	2
Republic of Ireland	1
Ukraine	2

More JOIN
 
http://sqlzoo.net/wiki/More_details_about_the_database.
Summary
Contents
 [hide] 
11962 movies
2When was Citizen Kane released?
3Star Trek movies
4id for actor Glenn Close
5id for Casablanca
6Cast list for Casablanca
7Alien cast list
8Harrison Ford movies
9Harrison Ford as a supporting actor
10Lead actors in 1962 movies
11Busy years for John Travolta
12Lead actor in Julie Andrews movies
13Actors with 30 leading roles
1.List the films where the yr is 1962 [Show id, title]
Answer : SELECT id, title
 FROM movie
 WHERE yr=1962
2. Give year of 'Citizen Kane'.
Answer : SELECT yr
FROM movie
WHERE title = 'Citizen Kane'
3. List all of the Star Trek movies, include the id, title and yr (all of these movies include the words Star Trek in the title). Order results by year.
Answer : SELECT id, title, yr
FROM movie
WHERE title LIKE 'Star Trek%'
ORDER BY yr
4.What id number does the actor 'Glenn Close' have?
Answer : SELECT id
FROM actor
WHERE name LIKE 'Glenn Close'
5.What is the id of the film 'Casablanca'
Answer : SELECT id
FROM movie
WHERE title LIKE 'Casablanca'
Get to the point
6.Obtain the cast list for 'Casablanca'.
what is a cast list?
The cast list is the names of the actors who were in the movie.
Use movieid=11768, (or whatever value you got from the previous question)
Answer : SELECT name
FROM casting JOIN movie ON casting.movieid = movie.id
JOIN actor ON actor.id=casting.actorid
WHERE movieid=11768 OR title='Casablanca'
7.Obtain the cast list for the film 'Alien'
Answer : SELECT name
FROM casting JOIN movie ON casting.movieid = movie.id
JOIN actor ON actor.id=casting.actorid
WHERE title='Alien'
8. List the films in which 'Harrison Ford' has appeared
Answer :
SELECT title
FROM casting JOIN movie ON casting.movieid = movie.id
JOIN actor ON actor.id=casting.actorid
WHERE name='Harrison Ford'
9.List the films where 'Harrison Ford' has appeared - but not in the starring role. [Note: the ord field of casting gives the position of the actor. If ord=1 then this actor is in the starring role]
Answer : SELECT title
FROM casting JOIN movie ON casting.movieid = movie.id
JOIN actor ON actor.id=casting.actorid
WHERE name='Harrison Ford' AND ord NOT LIKE 1
10. List the films together with the leading star for all 1962 films.
Answer : Spread this issue into more steps
Step 1: Get movieid which are released in 1962 ( use DISTINCT statement to remove duplication movieid in result)
SELECT DISTINCT movieid
FROM casting JOIN movie ON casting.movieid = movie.id
WHERE yr=1962
→ Result
movieid
10212
10329
10347
10648
10868
11006
11053
11199
11230
11234
11242
11373
11391
11439
11692
11735
11753
12368
12384
12710
12817
12967
12992
13010
13484
13534
13641
13727
13741
13798
14317
14454
14550
14718
14860
14873
14972
15088
15173
15182
15247
15297
15397
15564
15752
15779
15840
16203
16295
16367
Results truncated. Only the first 50 rows have been shown
Step 2: Get movie title for each movieid and name of actors list ( JOIN to actor table) and ord = 1 to filter leading actor of them.
SELECT DISTINCT movieid, title, name
FROM casting JOIN movie ON casting.movieid = movie.id
                    	JOIN actor ON actorid=actor.id
WHERE yr=1962 AND ord =1
→ Result :

movieid	title	name
10212	A Kind of Loving	Alan Bates
10329	A Symposium on Popular Songs	Paul Frees
10347	A Very Private Affair (Vie PrivÃ©e)	Brigitte Bardot
10648	An Autumn Afternoon	Chishu Ryu
10868	Atraco a las tres	JosÃ© Luis LÃ³pez VÃ¡zquez
11006	Barabbas	Anthony Quinn
11053	Battle Beyond the Sun (ÐÐµÐ±Ð¾ Ð·Ð¾Ð²ÐµÑ‚)	Aleksandr Shvorin
11199	Big and Little Wong Tin Bar	Jackie Chan
11230	Billy Budd	Terence Stamp
11234	Billy Rose's Jumbo	Doris Day
11242	Birdman of Alcatraz	Burt Lancaster
11373	Boccaccio '70	Anita Ekberg
11391	Bon Voyage!	Fred MacMurray
11439	Boys' Night Out	Kim Novak
11692	Cape Fear	Gregory Peck
11735	Carnival of Souls	Candace Hilligoss
11753	Carry On Cruising	Sid James
12368	David and Lisa	Keir Dullea
12384	Days of Wine and Roses	Jack Lemmon
12710	Dr. No	Sean Connery
12817	L'Eclisse	Alain Delon
12967	Tutti a casa	Alberto Sordi
12992	Experiment in Terror	Glenn Ford
13010	Eyes Without a Face	Pierre Brasseur
13484	Gay Purr-ee	Judy Garland
13534	Gigot	Jackie Gleason
13641	Gorath	Ryo Ikebe
13727	Gypsy	Rosalind Russell
13741	Half Ticket	Kishore Kumar
13798	Harakiri	Tatsuya Nakadai
14317	In Search of the Castaways	Hayley Mills
14454	It's Only Money	Jerry Lewis
14550	Jigsaw	Jack Warner
14718	Kid Galahad	Elvis Presley
14860	La commare secca	Marisa Solinas
14873	La notte	Marcello Mastroianni
15088	Life for Ruth	Michael Craig
15173	Lolita	James Mason
15182	Long Day's Journey into Night	Katharine Hepburn
15247	Love at Twenty	Jean-Pierre LÃ©aud
15297	Lycanthropus	Barbara Lass
15397	Mamma Roma	Anna Magnani
15564	Merrill's Marauders	Jeff Chandler
15752	Mother Joan of the Angels	Lucyna Winnicka
15779	Mr. Hobbs Takes a Vacation	James Stewart
15840	Mutiny on the Bounty	Marlon Brando
16203	On the Beat	Norman Wisdom
16295	Os Cafajestes	Daniel Filho
16367	Panic in Year Zero!	Ray Milland
16462	Period of Adjustment	Anthony Franciosa
Results truncated. Only the first 50 rows have been shown.

Step 3: Remove movieid from SELECT syntax to get correct answer 
SELECT title, name
FROM casting JOIN movie ON casting.movieid = movie.id
                    	JOIN actor ON actorid=actor.id
WHERE yr=1962 AND ord =1

11.Which were the busiest years for 'John Travolta', show the year and the number of movies he made each year for any year in which he made more than 2 movies.
Answer : SELECT yr,COUNT(title) FROM
  movie JOIN casting ON movie.id=movieid
     	JOIN actor   ON actorid=actor.id
where name='John Travolta'
GROUP BY yr
HAVING COUNT(title)=(SELECT MAX(c) FROM
(SELECT yr,COUNT(title) AS c FROM
   movie JOIN casting ON movie.id=movieid
     	JOIN actor   ON actorid=actor.id
 where name='John Travolta'
 GROUP BY yr) AS t
)
12. List the film title and the leading actor for all of the films 'Julie Andrews' played in.
Did you get "Little Miss Marker twice"?
Julie Andrews starred in the 1980 remake of Little Miss Marker and not the original(1934).
Title is not a unique field, create a table of IDs in your subquery
Answer : Spread this issue into more steps
Step 1: Filter movieid film list which 'Julie Andrews' joined 
SELECT movieid
FROM casting JOIN actor ON actor.id=actorid
WHERE name = 'Julie Andrews'
→ Submit 

movieid
10016
12354
12497
12766
13846
15145
15476
16870
17117
17445
17765
18270
20136
20136
20180
20181
20509
20627
21023
21154
21171
21483

Click answer should be to get correct answer 
title	name
10	Dudley Moore
Darling Lili	Julie Andrews
Despicable Me	Steve Carell
Duet for One	Julie Andrews
Hawaii	Julie Andrews
Little Miss Marker	Walter Matthau
Mary Poppins	Julie Andrews
Relative Values	Julie Andrews
S.O.B.	Julie Andrews
Shrek the Third	Mike Myers
Star!	Julie Andrews
The Americanization of Emily	James Garner
The Pink Panther Strikes Again	Peter Sellers
The Princess Diaries	Anne Hathaway
The Princess Diaries 2: Royal Engagement	Anne Hathaway
The Sound of Music	Julie Andrews
The Tamarind Seed	Julie Andrews
Thoroughly Modern Millie	Julie Andrews
Tooth Fairy	Dwayne Johnson
Torn Curtain	Paul Newman
Victor Victoria	Julie Andrews

Step 2 : Change format for movieid list from 
Movieid_number1 → enter
Movieid_number2 → enter
….
Into 
Movieid_number1, Movieid_number2, …
To input for IN (Movieid_number1, Movieid_number2, …) to get film title for movie list (get first column for correct answer)
Method : copy list in code editor such textwrangler or sublime text, add (,) after movieid_number
 

Step 3 : run script to get title list 
SELECT title 
FROM movie JOIN casting ON movieid=movie.id
WHERE id IN (10016,
12354,
12497,
12766,
13846,
15145,
15476,
16870,
17117,
17445,
17765,
18270,
20136,
20136,
20180,
20181,
20509,
20627,
21023,
21154,
21171,
21483)
→ Get result this :
title
10
10
10
10
10
10
10
Darling Lili
Darling Lili
Darling Lili
Darling Lili
Darling Lili
Darling Lili
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Despicable Me
Duet for One
Duet for One
Duet for One
Hawaii
Hawaii
Hawaii
Hawaii
Hawaii
Hawaii
Hawaii
Hawaii
Hawaii
Hawaii
Hawaii
Hawaii
Little Miss Marker
Little Miss Marker
Little Miss Marker
Little Miss Marker
Little Miss Marker
Results truncated. Only the first 50 rows have been shown.

Step 4:  Show ord, actorid column for each movieid and actorid
SELECT title, actorid, ord
FROM movie JOIN casting ON movieid=movie.id
                 JOIN actor ON actorid=actor.id #use JOIN statement to get ord value for each actor/ movie title
WHERE movie.id IN (10016,
12354,
12497,
12766,
13846,
15145,
15476,
16870,
17117,
17445,
17765,
18270,
20136,
20136,
20180,
20181,
20509,
20627,
21023,
21154,
21171,
21483)
Step 5 : Filter ord = 1
SELECT title, actorid, ord
FROM movie JOIN casting ON movieid=movie.id
                 	JOIN actor ON actorid=actor.id
WHERE movie.id IN (10016,
12354,
12497,
12766,
13846,
15145,
15476,
16870,
17117,
17445,
17765,
18270,
20136,
20136,
20180,
20181,
20509,
20627,
21023,
21154,
21171,
21483)
AND ord = 1
→ Result 

title	actorid	ord
10	178	1
Darling Lili	179	1
Despicable Me	6512	1
Duet for One	179	1
Hawaii	179	1
Little Miss Marker	1928	1
Mary Poppins	179	1
Relative Values	179	1
S.O.B.	179	1
Shrek the Third	1089	1
Star!	179	1
The Americanization of Emily	7895	1
The Pink Panther Strikes Again	3116	1
The Princess Diaries	5254	1
The Princess Diaries 2: Royal Engagement	5254	1
The Sound of Music	179	1
The Tamarind Seed	179	1
Thoroughly Modern Millie	179	1
Tooth Fairy	9291	1
Torn Curtain	2697	1
Victor Victoria	179	1
 Step 6 : Use actorid to get name of leading actor for each movie title
SELECT title, actorid, ord, name
FROM movie JOIN casting ON movieid=movie.id
                 	JOIN actor ON actorid=actor.id
WHERE movie.id IN (10016,
12354,
12497,
12766,
13846,
15145,
15476,
16870,
17117,
17445,
17765,
18270,
20136,
20136,
20180,
20181,
20509,
20627,
21023,
21154,
21171,
21483)
AND ord = 1
→ Result

title	actorid	ord	name
10	178	1	Dudley Moore
Darling Lili	179	1	Julie Andrews
Despicable Me	6512	1	Steve Carell
Duet for One	179	1	Julie Andrews
Hawaii	179	1	Julie Andrews
Little Miss Marker	1928	1	Walter Matthau
Mary Poppins	179	1	Julie Andrews
Relative Values	179	1	Julie Andrews
S.O.B.	179	1	Julie Andrews
Shrek the Third	1089	1	Mike Myers
Star!	179	1	Julie Andrews
The Americanization of Emily	7895	1	James Garner
The Pink Panther Strikes Again	3116	1	Peter Sellers
The Princess Diaries	5254	1	Anne Hathaway
The Princess Diaries 2: Royal Engagement	5254	1	Anne Hathaway
The Sound of Music	179	1	Julie Andrews
The Tamarind Seed	179	1	Julie Andrews
Thoroughly Modern Millie	179	1	Julie Andrews
Tooth Fairy	9291	1	Dwayne Johnson
Torn Curtain	2697	1	Paul Newman
Victor Victoria	179	1	Julie Andrews
 Step 7 : Removed column which isn’t include in correct answer by remove (actorid and ord feilds on SELECT syntax)
SELECT title, name
FROM movie JOIN casting ON movieid=movie.id
                 	JOIN actor ON actorid=actor.id
WHERE movie.id IN (10016,
12354,
12497,
12766,
13846,
15145,
15476,
16870,
17117,
17445,
17765,
18270,
20136,
20136,
20180,
20181,
20509,
20627,
21023,
21154,
21171,
21483)
AND ord = 1

13. Obtain a list, in alphabetical order, of actors who've had at least 30 starring roles.
Answer : SELECT name
FROM actor
  JOIN casting ON (id = actorid AND (SELECT COUNT(ord) FROM casting WHERE actorid = actor.id AND ord=1)>=30)
GROUP BY name

14. List the films released in the year 1978 ordered by the number of actors in the cast, then by title.
Answer : SELECT title, COUNT(actorid)
FROM casting JOIN movie ON movie.id=casting.movieid
JOIN actor ON actor.id=casting.actorid
WHERE yr = 1978
GROUP BY title
ORDER BY COUNT(actorid) DESC , title
15.List all the people who have worked with 'Art Garfunkel'.
Answer : Spread big question into 2 Steps
15.1 Which film did Art Garfunkel joined ?
SELECT film
FROM casting JOIN movie ON casting.movieid = movie.id
JOIN actor ON actor.id=casting.actorid
WHERE name LIKE 'Art Garfunkel'
15.2 Find actor list who joined the films (Got from 15.1) without ‘Art Garfunkel’
SELECT DISTINCT name
FROM casting JOIN movie ON casting.movieid = movie.id
JOIN actor ON actor.id=casting.actorid
WHERE title IN ('54','Boxing Helena','Good to Go') AND name NOT LIKE 'Art Garfunkel'
Clear your results
JOIN Quiz 2
That is definitely enough. Students should, under no circumstances look at the next tutorial, concerning outer joins.
Quiz
1. Select the statement which lists the unfortunate directors of the movies which have caused financial loses (gross < budget)
Answer : SELECT name
  FROM actor INNER JOIN movie ON actor.id = director
 WHERE gross < budget
2. Select the correct example of JOINing three tables
Answer : SELECT *
  FROM actor JOIN casting ON actor.id = actorid
  JOIN movie ON movie.id = movieid
3. Select the statement that shows the list of actors called 'John' by order of number of movies in which they acted
Answer : SELECT name, COUNT(movieid)
  FROM casting JOIN actor ON actorid=actor.id
 WHERE name LIKE 'John %'
 GROUP BY name ORDER BY 2 DESC
4. Select the result that would be obtained from the following code:
Answer : 
"Crocodile" Dundee
Crocodile Dundee in Los Angeles
Flipper
Lightning Jack

5. Select the statement that lists all the actors that starred in movies directed by Ridley Scott who has id 351
Answer : SELECT name
  FROM movie JOIN casting ON movie.id = movieid
  JOIN actor ON actor.id = actorid
WHERE ord = 1 AND director = 351
6. There are two sensible ways to connect movie and actor. They are:
Answer : link the director column in movies with the primary key in actor
●	connect the primary keys of movie and actor via the casting table
7. Select the result that would be obtained from the following code: 
SELECT title, yr 
   FROM movie, casting, actor 
  WHERE name='Robert De Niro' AND movieid=movie.id AND actorid=actor.id AND ord = 3
Answer : 
A Bronx Tale	1993
Bang the Drum Slowly	1973
Limitless	2011

Using NULL
Using Null
id	dept	name	phone	mobile
101	1	Shrivell	2753	07986 555 1234
102	1	Throd	2754	07122 555 1920
103	1	Splint	2293	
104		Spiregrain	3287	
105	2	Cutflower	3212	07996 555 6574
106		Deadyawn	3345	
...

id	name
1	Computing
2	Design
3	Engineering
...
Teachers and Departments
The school includes many departments. Most teachers work exclusively for a single department. Some teachers have no department.
Selecting NULL values.
Summary
NULL, INNER JOIN, LEFT JOIN, RIGHT JOIN
1.List the teachers who have NULL for their department.
Why we cannot use =
You might think that the phrase dept=NULL would work here but it doesn't - you can use the phrase dept IS NULL
That's not a proper explanation.
No it's not, but you can read a better explanation at Wikipedia:NULL.
Answer : SELECT name
FROM teacher
WHERE dept IS NULL
2.Note the INNER JOIN misses the teachers with no department and the departments with no teacher.
Answer : SELECT teacher.name, dept.name
 FROM teacher INNER JOIN dept
       	ON (teacher.dept=dept.id)
# INNER JOIN to get values which aren't different NULL
3. Use a different JOIN so that all teachers are listed.
Answer : SELECT teacher.name, dept.name
FROM teacher LEFT JOIN dept ON dept.id=teacher.dept
# LEFT JOIN to get values which includes NULL value
4. Use a different JOIN so that all departments are listed.
Answer : SELECT  teacher.name, dept.name
FROM dept LEFT JOIN teacher ON dept.id=teacher.dept
5. Using the COALESCE function
Use COALESCE to print the mobile number. Use the number '07986 444 2266' if there is no number given.Show teacher name and mobile number or '07986 444 2266'
Answer : SELECT teacher.name, COALESCE(mobile,'07986 444 2266')
FROM teacher
6. Use the COALESCE function and a LEFT JOIN to print the teacher name and department name. Use the string 'None' where there is no department.
Answer : SELECT teacher.name, COALESCE(dept.name,'None')
FROM dept RIGHT JOIN teacher ON dept.id=teacher.dept
OR use LEFT JOIN
SELECT teacher.name, COALESCE(dept.name,'None')
FROM teacher LEFT JOIN dept ON dept.id=teacher.dept
7. Use COUNT to show the number of teachers and the number of mobile phones.
Answer : SELECT COUNT(name), COUNT(mobile)
FROM teacher
8. Use COUNT and GROUP BY dept.name to show each department and the number of staff. Use a RIGHT JOIN to ensure that the Engineering department is listed.
Answer : SELECT dept.name, COUNT(teacher.name)
FROM teacher RIGHT JOIN dept ON dept.id=teacher.dept
GROUP BY dept.name
#How to use INNER JOIN/ LEFT JOIN/ RIGHT JOIN
https://123doc.org/document/406373-su-khac-biet-giua-left-join-right-join-innerjoin.htm
Using CASE
9. Use CASE to show the name of each teacher followed by 'Sci' if the teacher is in dept 1 or 2 and 'Art' otherwise.
Answer : SELECT name
  	,CASE WHEN dept =1
   	THEN 'Sci'
   	WHEN dept =2
   	THEN 'Sci'
   	ELSE 'Art'
  	END
FROM teacher
10. Use CASE to show the name of each teacher followed by 'Sci' if the teacher is in dept 1 or 2, show 'Art' if the teacher's dept is 3 and 'None' otherwise.
Answer :
SELECT name,
CASE WHEN dept =1
THEN 'Sci'
WHEN dept =2
THEN 'Sci'
WHEN dept = 3
THEN 'Art'
ELSE 'None'
END
FROM teacher
Clear your results
Using Null Quiz
Quiz
Test your understanding of the NULL value
id	dept	name	phone
101	1	Shrivell	2753
102	1	Throd	2754
103	1	Splint	
104		Spiregrain	
105	2	Cutflower 	3212
106		Deadyawn	


id	name
1	Computing
2	Design
3	Engineering

1. Select the code which uses a JOIN correctly.
Answer :SELECT teacher.name, dept.name FROM teacher LEFT OUTER JOIN dept ON (teacher.dept > dept.id)
2. Select the correct statement that shows the name of department which employs Cutflower -
Answer : SELECT dept.name FROM teacher JOIN dept ON (dept.id = teacher.dept) WHERE teacher.name = 'Cutflower'
3. Select out of following the code which uses a JOIN to show a list of all the departments and number of employed teachers
Answer : SELECT dept.name, COUNT(teacher.name) FROM teacher RIGHT JOIN dept ON dept.id = teacher.dept GROUP BY dept.name
4. Using SELECT name, dept, COALESCE(dept, 0) AS result FROM teacher on teacher table will:
Answer : display 0 in result column for all teachers without department
5. Query:
SELECT name,
       CASE WHEN phone = 2752 THEN 'two'
            WHEN phone = 2753 THEN 'three'
            WHEN phone = 2754 THEN 'four'
            END AS digit
  FROM teacher

shows following 'digit':
Answer : 'four' for Throd
6. Select the result that would be obtained from the following code:
SELECT name, 
      CASE 
       WHEN dept 
        IN (1) 
        THEN 'Computing' 
       ELSE 'Other' 
      END 
  FROM teacher
Answer : 
Shrivell	Computing
Throd	Computing
Splint	Computing
Spiregrain	Other
Cutflower	Other
Deadyawn	Other

Self JOIN
Self join
Edinburgh Buses
Details of the database Looking at the data
stops(id, name)
route(num,company,pos, stop)

stops	route
id	num
name	company
	pos
	stop

	
1.How many stops are in the database.
Answer : SELECT COUNT(name)
FROM stops
2.Find the id value for the stop 'Craiglockhart'
Answer : SELECT id
FROM stops
WHERE name LIKE 'Craiglockhart'
3. Give the id and the name for the stops on the '4' 'LRT' service.
Answer : SELECT stops.id, stops.name
FROM stops JOIN route ON id=stop
WHERE num=4 AND company LIKE 'LRT'
4.The query shown gives the number of routes that visit either London Road (149) or Craiglockhart (53). Run the query and notice the two services that link these stops have a count of 2. Add a HAVING clause to restrict the output to these two routes.
Answer : SELECT company, num, COUNT(*)
FROM route
WHERE stop = 149 OR stop = 53
GROUP BY num, company
HAVING COUNT(*) = 2
5.Execute the self join shown and observe that b.stop gives all the places you can get to from Craiglockhart, without changing routes. Change the query so that it shows the services from Craiglockhart to London Road.
Answer : SELECT a.company, a.num, a.stop, b.stop
FROM route a JOIN route b ON
  (a.company=b.company AND a.num=b.num)
WHERE a.stop=53 AND b.stop=149
#Explain more for this issue 
Think a table as route and b table as stops. Use JOIN from a table to b table belong to company & num which are same on both a table and b table, but from a.stop=id(Start stop) to b.stop=id (finish stop)
6. The query shown is similar to the previous one, however by joining two copies of the stops table we can refer to stops by name rather than by number. Change the query so that the services between 'Craiglockhart' and 'London Road' are shown. If you are tired of these places try 'Fairmilehead' against 'Tollcross'
Answer : SELECT a.company, a.num, stopa.name, stopb.name
FROM route a JOIN route b ON
  (a.company=b.company AND a.num=b.num)
  JOIN stops stopa ON (a.stop=stopa.id)
  JOIN stops stopb ON (b.stop=stopb.id)
WHERE stopa.name='Craiglockhart' AND stopb.name='London Road'
Using a self join

7. Give a list of all the services which connect stops 115 and 137 ('Haymarket' and 'Leith')
Answer : SELECT DISTINCT a.company, a.num
FROM route a
JOIN route b ON a.num = b.num
WHERE a.stop = 115
AND b.stop = 137
8. Give a list of the services which connect the stops 'Craiglockhart' and 'Tollcross'
Answer : SELECT a.company, a.num
FROM route a JOIN route b ON (a.num = b.num)
JOIN stops stopa ON (a.stop = stopa.id)
JOIN stops stopb ON (b.stop = stopb.id)
WHERE stopa.name = 'Craiglockhart'
AND stopb.name = 'Tollcross'
9. Give a distinct list of the stops which may be reached from 'Craiglockhart' by taking one bus, including 'Craiglockhart' itself, offered by the LRT company. Include the company and bus no. of the relevant services
Answer : SELECT a.company, stopb.name,a.num
FROM route a JOIN route b ON (a.num=b.num AND a.company=b.company)
JOIN stops stopa ON (a.stop = stopa.id)
JOIN stops stopb ON (b.stop = stopb.id)
WHERE stopa.name ='Craiglockhart'  AND a.company='LRT'
10.Find the routes involving two buses that can go from Craiglockhart to Sighthill.
Show the bus no. and company for the first bus, the name of the stop for the transfer,
and the bus no. and company for the second bus.
Answer :
SELECT DISTINCT an, ac, stops.name, dn, dc
FROM
  -- all lines going from Craiglockahart to somewhere
  (SELECT a.num as an, a.company as ac, b.stop as bstop
   FROM
   route a JOIN route b JOIN stops s
   ON a.num=b.num AND s.id=a.stop
   WHERE s.name='Craiglockhart') T1
 JOIN
  -- all lines going from somewhere to Sighthill
  (SELECT d.num as dn, d.company as dc, c.stop as cstop
   FROM
   route c JOIN route d JOIN stops s
   ON c.num=d.num AND c.company=d.company AND s.id=d.stop
   WHERE s.name='Sighthill') T2
 JOIN stops
 ON bstop=cstop AND bstop=stops.id
Quiz
SELF JOIN quiz
stops	route
id	num
name	company
	pos
	stop
	

1. Select the code that would show it is possible to get from Craiglockhart to Haymarket
Answer : SELECT DISTINCT a.name, b.name
  FROM stops a JOIN route z ON a.id=z.stop
  JOIN route y ON y.num = z.num
  JOIN stops b ON y.stop=b.id
 WHERE a.name='Craiglockhart' AND b.name ='Haymarket'

2. Select the code that shows the stops that are on route.num '2A' which can be reached with one bus from Haymarket?
Answer : SELECT S2.id, S2.name, R2.company, R2.num
  FROM stops S1, stops S2, route R1, route R2
 WHERE S1.name='Haymarket' AND S1.id=R1.stop
   AND R1.company=R2.company AND R1.num=R2.num
   AND R2.stop=S2.id AND R2.num='2A'

3. Select the code that shows the services available from Tollcross?
Answer : SELECT a.company, a.num, stopa.name, stopb.name
  FROM route a JOIN route b ON (a.company=b.company AND a.num=b.num)
  JOIN stops stopa ON (a.stop=stopa.id)
  JOIN stops stopb ON (b.stop=stopb.id)
 WHERE stopa.name='Tollcross'


