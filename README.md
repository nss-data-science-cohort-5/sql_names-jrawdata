===========================## SQL Names

Save a script containing the query you used to answer each question and your answer (as a comment).

1. How many rows are in the names table?
SELECT COUNT(*)
FROM names;
1957046

2. How many total registered people appear in the dataset?
SELECT SUM(num_registered)
FROM names;
351653025

**3. Which name had the most appearances in a single year in the dataset?
SELECT name, MAX(num_registered)
FROM names
GROUP BY name
ORDER BY MAX(num_registered) DESC;
LINDA

4. What range of years are included?
SELECT MIN(year), MAX(year)
FROM names;
1880 to 2018

5. What year has the largest number of registrations?
SELECT year,MAX(num_registered)
FROM names
GROUP BY year
ORDER BY MAX(num_registered) DESC;
1947

6. How many different (distinct) names are contained in the dataset?
SELECT COUNT(DISTINCT name)
FROM names;
98400

7. Are there more males or more females registered?
SELECT COUNT(gender), gender
FROM names
GROUP BY gender;
Females

8. What are the most popular male and female names overall (i.e., the most total registrations)?
SELECT MAX(num_registered), name, gender
FROM names
GROUP BY gender,name
ORDER BY max(num_registered) DESC;
Linda and James 

9. What are the most popular boy and girl names of the first decade of the 2000s (2000 - 2009)?
SELECT MAX(num_registered), name, gender
FROM names
WHERE year BETWEEN 2000 AND 2009
GROUP BY gender,name
ORDER BY max(num_registered) DESC;
Emily and Jacob 

10. Which year had the most variety in names (i.e. had the most distinct names)?
SELECT COUNT(DISTINCT name),year
FROM names
GROUP BY year
ORDER BY COUNT(DISTINCT name) DESC;
2008

11. What is the most popular name for a girl that starts with the letter X?
SELECT MAX(num_registered), name
FROM names
WHERE gender = 'F' AND name LIKE 'X%'
GROUP BY name
ORDER BY MAX(num_registered) DESC;
Ximena

12. How many distinct names appear that start with a 'Q', but whose second letter is not 'u'?
SELECT COUNT(DISTINCT name)
FROM names
WHERE name LIKE 'Q%' AND name NOT LIKE '_u%',
46

13. Which is the more popular spelling between "Stephen" and "Steven"? Use a single query to answer this question.
SELECT SUM(num_registered), name
FROM names
WHERE name = 'Stephen' OR name='Steven'
GROUP BY name;
Steven

14. What percentage of names are "unisex" - that is what percentage of names have been used both for boys and for girls?


15. How many names have made an appearance in every single year since 1880?

16. How many names have only appeared in one year?

17. How many names only appeared in the 1950s?

18. How many names made their first appearance in the 2010s?

19. Find the names that have not be used in the longest.

20. Come up with a question that you would like to answer using this dataset. Then write a query to answer this question.
