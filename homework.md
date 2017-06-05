# SQL Homework

The Dominion Cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'
```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:
```
# terminal
psql -d marvel -f marvel.sql
``` 

Use the supplied data as the source of data to answer the questions.  Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1. Return ALL the data in the 'movies' table.

SELECT * FROM movies; 

id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 17:55
  2 | The Incredible Hulk                 | 2008 | 17:55
  3 | Iron Man 2                          | 2010 | 17:10
  4 | Thor                                | 2011 | 19:30
  5 | Captain America: The First Avenger  | 2011 | 18:50
  6 | Avengers Assemble                   | 2012 | 19:05
  7 | Iron Man 3                          | 2013 | 22:10
  8 | Thor: The Dark World                | 2013 | 23:30
  9 | Batman Begins                       | 2005 | 23:30
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 14:35
 13 | Ant-Man                             | 2015 | 19:15
 14 | Captain America: Civil War          | 2016 | 12:35
 15 | Doctor Strange                      | 2016 | 21:30
(15 rows)



2. Return ONLY the name column from the 'people' table

SELECT name FROM people;

name        
-------------------
 Faisal Ali
 Samantha Campbell
 Jasmse Cox
 Upul Dissanayaka
 Martin Eguizabel
 Pedro Everett
 Filipe Granha
 Winston Ingram
 Fred
 Reece Jones
 Eugene Kim
 Steven MacDonald
 Fred
 Jamie Martin
 Ciaran McKenna
 Ross Murray
 Victoria Plows
 Finn Porter
 Tom Roddick
 Alan White
 Glen Young
(21 rows)



3. Oops! Someone at CodeClan spelled James' name wrong! Change it to reflect the proper spelling (change 'Jasmse Cox' to 'James Cox').

UPDATE people SET name = 'James Cox' WHERE name = 'Jasmse Cox';
SELECT * FROM people;

UPDATE 1
 id |       name        
----+-------------------
  1 | Faisal Ali
  2 | Samantha Campbell
  4 | Upul Dissanayaka
  5 | Martin Eguizabel
  6 | Pedro Everett
  7 | Filipe Granha
  8 | Winston Ingram
  9 | Fred
 10 | Reece Jones
 11 | Eugene Kim
 12 | Steven MacDonald
 13 | Fred
 14 | Jamie Martin
 15 | Ciaran McKenna
 16 | Ross Murray
 17 | Victoria Plows
 18 | Finn Porter
 19 | Tom Roddick
 20 | Alan White
 21 | Glen Young
  3 | James Cox
(21 rows)



4. Return ONLY your name from the 'people' table.

SELECT name FROM people WHERE name = 'Filipe Granha';

  name      
---------------
 Filipe Granha
(1 row)



5. The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies WHERE title = 'Batman Begins';
SELECT * FROM movies;

DELETE 1
 id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 17:55
  2 | The Incredible Hulk                 | 2008 | 17:55
  3 | Iron Man 2                          | 2010 | 17:10
  4 | Thor                                | 2011 | 19:30
  5 | Captain America: The First Avenger  | 2011 | 18:50
  6 | Avengers Assemble                   | 2012 | 19:05
  7 | Iron Man 3                          | 2013 | 22:10
  8 | Thor: The Dark World                | 2013 | 23:30
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 14:35
 13 | Ant-Man                             | 2015 | 19:15
 14 | Captain America: Civil War          | 2016 | 12:35
 15 | Doctor Strange                      | 2016 | 21:30
(14 rows)



6. Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people (name) VALUES ('Zsolt');
SELECT * FROM people;

INSERT 0 1
 id |       name        
----+-------------------
  1 | Faisal Ali
  2 | Samantha Campbell
  4 | Upul Dissanayaka
  5 | Martin Eguizabel
  6 | Pedro Everett
  7 | Filipe Granha
  8 | Winston Ingram
  9 | Fred
 10 | Reece Jones
 11 | Eugene Kim
 12 | Steven MacDonald
 13 | Fred
 14 | Jamie Martin
 15 | Ciaran McKenna
 16 | Ross Murray
 17 | Victoria Plows
 18 | Finn Porter
 19 | Tom Roddick
 20 | Alan White
 21 | Glen Young
  3 | James Cox
 22 | Zsolt
(22 rows)



7. Winston Ingram, has decided to hijack our movie evening, Remove him from the table of people.

DELETE FROM people WHERE name = 'Winston Ingram';
SELECT * FROM people;

DELETE 1
 id |       name        
----+-------------------
  1 | Faisal Ali
  2 | Samantha Campbell
  4 | Upul Dissanayaka
  5 | Martin Eguizabel
  6 | Pedro Everett
  7 | Filipe Granha
  9 | Fred
 10 | Reece Jones
 11 | Eugene Kim
 12 | Steven MacDonald
 13 | Fred
 14 | Jamie Martin
 15 | Ciaran McKenna
 16 | Ross Murray
 17 | Victoria Plows
 18 | Finn Porter
 19 | Tom Roddick
 20 | Alan White
 21 | Glen Young
  3 | James Cox
 22 | Zsolt
(21 rows)



8. Somehow the list of people includes two people named 'Fred'. Change these entries to the proper names ('Jack Jarvis', 'Victor McDade')

UPDATE people SET name = 'Jack Jarvis' WHERE name = 'Fred' AND id = 9;
UPDATE people SET name = 'Victor McDade' WHERE name = 'Fred' AND id = 13;
SELECT * FROM people;

UPDATE 1
UPDATE 1
 id |       name        
----+-------------------
  1 | Faisal Ali
  2 | Samantha Campbell
  4 | Upul Dissanayaka
  5 | Martin Eguizabel
  6 | Pedro Everett
  7 | Filipe Granha
 10 | Reece Jones
 11 | Eugene Kim
 12 | Steven MacDonald
 14 | Jamie Martin
 15 | Ciaran McKenna
 16 | Ross Murray
 17 | Victoria Plows
 18 | Finn Porter
 19 | Tom Roddick
 20 | Alan White
 21 | Glen Young
  3 | James Cox
 22 | Zsolt
  9 | Jack Jarvis
 13 | Victor McDade
(21 rows)



9. The cinema has just heard that they will be holding an exclusive midnight showing of 'Guardians of the Galaxy 2'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, show_time) VALUES ('Guardians of the Galaxy 2', '00:00');
SELECT * FROM movies;

INSERT 0 1
 id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 17:55
  2 | The Incredible Hulk                 | 2008 | 17:55
  3 | Iron Man 2                          | 2010 | 17:10
  4 | Thor                                | 2011 | 19:30
  5 | Captain America: The First Avenger  | 2011 | 18:50
  6 | Avengers Assemble                   | 2012 | 19:05
  7 | Iron Man 3                          | 2013 | 22:10
  8 | Thor: The Dark World                | 2013 | 23:30
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 11 | Guardians of the Galaxy             | 2014 | 19:05
 12 | Avengers: Age of Ultron             | 2015 | 14:35
 13 | Ant-Man                             | 2015 | 19:15
 14 | Captain America: Civil War          | 2016 | 12:35
 15 | Doctor Strange                      | 2016 | 21:30
 16 | Guardians of the Galaxy 2           |      | 00:00
(15 rows)



10. The cinema would also like to make the Guardian movies a back to back feature. Update the 'Guardians of the Galaxy' show time from 12:10 to 21:30

UPDATE movies SET show_time = '21:30' WHERE show_time = '12:10' AND title = 'Guardians of the Galaxy';
SELECT * FROM movies;

UPDATE 1
 id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 17:55
  2 | The Incredible Hulk                 | 2008 | 17:55
  3 | Iron Man 2                          | 2010 | 17:10
  4 | Thor                                | 2011 | 19:30
  5 | Captain America: The First Avenger  | 2011 | 18:50
  6 | Avengers Assemble                   | 2012 | 19:05
  7 | Iron Man 3                          | 2013 | 22:10
  8 | Thor: The Dark World                | 2013 | 23:30
 10 | Captain America: The Winter Soldier | 2014 | 14:55
 12 | Avengers: Age of Ultron             | 2015 | 14:35
 13 | Ant-Man                             | 2015 | 19:15
 14 | Captain America: Civil War          | 2016 | 12:35
 15 | Doctor Strange                      | 2016 | 21:30
 16 | Guardians of the Galaxy 2           |      | 00:00
 11 | Guardians of the Galaxy             | 2014 | 21:30
(15 rows)



## Extension

1. Research how to delete multiple entries from your table in a single command.

DELETE FROM movies WHERE id IN (1, 2, 10);
SELECT * FROM movies;

DELETE 3
 id |               title                | year | show_time 
----+------------------------------------+------+-----------
  3 | Iron Man 2                         | 2010 | 17:10
  4 | Thor                               | 2011 | 19:30
  5 | Captain America: The First Avenger | 2011 | 18:50
  6 | Avengers Assemble                  | 2012 | 19:05
  7 | Iron Man 3                         | 2013 | 22:10
  8 | Thor: The Dark World               | 2013 | 23:30
 12 | Avengers: Age of Ultron            | 2015 | 14:35
 13 | Ant-Man                            | 2015 | 19:15
 14 | Captain America: Civil War         | 2016 | 12:35
 15 | Doctor Strange                     | 2016 | 21:30
 16 | Guardians of the Galaxy 2          |      | 00:00
 11 | Guardians of the Galaxy            | 2014 | 21:30
(12 rows)

