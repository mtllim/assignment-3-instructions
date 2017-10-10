# ST445 Managing and Visualizing Data

## Week 3 Assignment, MT 2017
---
**Note: This assignment will be assessed.  Deadline: 5pm, 25 October 2017**

### A.  Normalizing data (40 points).

This question uses this table (from [the lecture notes](https://github.com/lse-st445/lectures/blob/master/week03/ST445_wk3_lecture.ipynb#normalization-example).  For each answer, please explain as fully as possible, and feel free to use tables or diagrams if you prefer.

1.  Why does this table violate the first normal form, and what would be required to make it 1NF?

2.  Why additional steps would be needed to make the table 2NF, and why?

3.  Why might we not want to normalize data to the fullest extent possible?

4.  In the table below, which of the three normalization rules does this violate, if any, and why?

    |  countryID  |  countryName    |   EUmember   |  EUjoindate  |
    | -----------:|:----------------|:------------:|:------------:|
    | 00001       | France          |  `true`      |  1958-01-01  |
    | 00004       | Hungary         |  `true`      |  2004-05-01  |
    | 00003       | Serbia          |  `false`     |       `NULL` |
    | 00004       | Finland         |  `true`      |  1995-01-01  |
    | 00005       | Russia          |  `false`     |       `NULL` |
    | 00006       | Ireland, UK     |  `true`      |  1973-01-01  |

    Are there any other problems with the table, besides normalization?

5.  What would it take to full (1NF-3NF) normalize this dataset?

    Write out these tables, and describe why this meets each of the normal forms.  This is a database of movies watched on NetBricks, a streaming movie service.

    | Name           | Address    |   Movies Rented   |  Salutation  | Category |
    |:---------------|:-----------|:------------------|:------------:|----------|
    | Bob Smith      | 1 Houghton Street    | _Star Wars_, _Inception_ |  Dr.   |  Scifi, Scifi |
    | Pry Ministair  | 10 Downing St     |  _Brexit the Movie_      |  Lady  | Tragedy |
    | Joe Bloggs     | 8 Myhatt St.      |  _Fast and Furious 6_, _Fast and Furious 7_     | Mr. | Action, Action |
  
### B.  Reshaping data (30 points)

For this exercise, we will use the **nycflights13** R package, whose tables have been output in `.csv` form [here](nycflights13/).  You may do the following in either R or Python.  Note that this example is developed extensively in [_R for Data Science_](http://r4ds.had.co.nz/relational-data.html).

1.  Create a subtable of the `flights` data, that departed before 05:53 on 2013-02-28.  How many rows and columns does this subtable have?  

2.  Merge or join the subtable from a. `airports` data, to produce a result that includes:  
    *  Departure time
    *  Carrier (two digit code, from `carrier`)
    *  Flight number
    *  Destination airport name (hint: you will need to get this from the `airports` table)  

3.  For every airline that had flights in the `flights` data compute the average age of the planes it flew from the entire dataset.  Age here will be defined as 2013 minus the `year` variable from the `planes` data.  Hint: This involves a join operation on `tailnum`, but also a grouped mean to compute the age (and subtracting 2013, which you can do before or after the computation of the mean).

### C.  Working with SQL.  (30 points)

1.  Create a relational dataset in SQLite using the `.csv` data found [here](nycflights13/).  Name each table so that it matches the base filenames of the input data.  You can use DB Browser for this, but describe how you did it.   If you use SQL commands, include that.

2.  Replicate 2b above using an SQL query, including both the command and the output.

3.  Replicate 2c above using an SQL query, including both the command and the output.
