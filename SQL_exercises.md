# SQL Exercises
### DB Data
|         name        |   continent   | population |
|:-------------------:|:-------------:|:----------:|
| Afghanistan         | Asia          | 32225560   |
| Albania             | Europe        | 2845955    |
| Algeria             | Africa        | 43000000   |
| Andorra             | Europe        | 77543      |
| Angola              | Africa        | 31127674   |
| Antigua and Barbuda | Caribbean     | 96453      |
| Argentina           | South America | 44938712   |
| Armenia             | Eurasia       | 2957500    |
| Australia           | Oceania       | 25690023   |
| Austria             | Europe        | 8902600    |
| Azerbaijan          | Asia          | 10067108   |

Results truncated. Only the first 10 rows have been shown.

## 1) Displaying all data in table
>SELECT name, continent, population FROM world  
___
  
## 2) Display all countries with population of over 200m
How to use WHERE to filter records. Show the name for the countries that have a population of at least 200 million.  200 million is 200000000, there are eight zeros.
>SELECT name FROM world  
>WHERE population >= 200000000
___

## 3) Display per capita GDP (GDP/population) with population of over 200m
Give the name and the per capita GDP for those countries with a population of at least 200 million.
>SELECT name, (GDP/population) FROM world  
>WHERE population >= 200000000
___

## 4) Display S.American country population in millions
Show the name and population in millions for the countries of the continent 'South America'. Divide the population by 1000000 to get population in millions.
>SELECT name, (population/1000000) FROM world  
>WHERE continent = 'South America'
___

## 5) Name and population for France, Germany and Italy
Show the name and population for France, Germany, Italy
>SELECT name, population FROM world  
>WHERE name in ('France', 'Germany', 'Italy')
___

## 6) Display countries that have 'United' in the name
Show the countries which have a name that includes the word 'United'
>SELECT name FROM world  
>WHERE name LIKE '%United%'
___

## 7) Display "big" countries
Two ways to be big: A country is big if it has an area of more than 3 million sq km or it has a population of more than 250 million.
> SELECT name, population, area FROM world
> WHERE area > 3000000 OR population > 250000000
___

## 8) Display "big" countries by population OR area
Exclusive OR (XOR). Show the countries that are big by area (more than 3 million) or big by population (more than 250 million) but not both. Show name, population and area.

Australia has a big area but a small population, it should be included.
Indonesia has a big population but a small area, it should be included.
China has a big population and big area, it should be excluded.
United Kingdom has a small population and a small area, it should be excluded.
>SELECT name, population, area FROM world
>WHERE area > 3000000 XOR population > 250000000
___

## 9) Rounding to decimal places
Show the name and population in millions and the GDP in billions for the countries of the continent 'South America'. Use the ROUND function to show the values to two decimal places.

For South America show population in millions and GDP in billions both to 2 decimal places.
Millions and billions
>SELECT name, ROUND(population/1000000, 2),ROUND(GDP/1000000000, 2) FROM world  
>WHERE continent = 'South America'
___

## 10) Trillion dollar economy filter
Show the name and per-capita GDP for those countries with a GDP of at least one trillion (1000000000000; that is 12 zeros). Round this value to the nearest 1000.

Show per-capita GDP for the trillion dollar countries to the nearest $1000.
>SELECT name, ROUND(GDP/population, -3) FROM world  
>WHERE GDP > 1000000000000
____

## 11) Name and capital have te same length
Greece has capital Athens.

Each of the strings 'Greece', and 'Athens' has 6 characters.

Show the name and capital where the name and the capital have the same number of characters.

You can use the LENGTH function to find the number of characters in a string

### Shows countries beginning with 'G' with length or country and capital with length
>SELECT name, LENGTH(name), continent, LENGTH(continent),
 capital, LENGTH(capital) FROM world  
> WHERE name LIKE 'G%'

### Show the name and capital where the name and the capital have the same number of characters
>SELECT name, capital FROM world
>WHERE LENGTH(name) LIKE LENGTH(capital)
___

## 12) Matching name and capital
The capital of Sweden is Stockholm. Both words start with the letter 'S'.

Show the name and the capital where the first letters of each match. Don't include countries where the name and the capital are the same word.
You can use the function LEFT to isolate the first character.
You can use <> as the NOT EQUALS operator.
>SELECT name, capital FROM world  
>WHERE name <> capital AND LEFT(name, 1) LIKE LEFT(capital, 1)
___

## 13) Have all the vowels 
Equatorial Guinea and Dominican Republic have all of the vowels (a e i o u) in the name. They don't count because they have more than one word in the name.

Find the country that has all the vowels and no spaces in its name.

You can use the phrase name NOT LIKE '%a%' to exclude characters from your results.
The query shown misses countries like Bahamas and Belarus because they contain at least one 'a'
>SELECT name FROM world  
>WHERE name LIKE '%u%'   
>  AND name LIKE '%a%'   
>  AND name LIKE '%o%'   
>  AND name LIKE '%i%'  
>  AND name LIKE '%e%'  
>  AND name NOT LIKE '% %'  
