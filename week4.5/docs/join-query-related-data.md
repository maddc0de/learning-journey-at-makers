# Using joins to query related data

## The N+1 Problem

If we want to select information both about an album _and_ its related artist, we need two queries — a first one to retrieve an album, and a second one to retrieve information about the artist, using the foreign key.

```sql
-- First, retrieve the album
SELECT id, title, artist_id FROM albums WHERE title = 'Bossanova';

-- Then retrieve the artist using the foreign key value in artist_id queried above
SELECT id, name, genre FROM artists WHERE id = 1;
```

As our database grows and contains more data, this is not ideal. Every query sent to the database adds some extra time to the query execution. If we were to retrieve ten different albums, and then the associated artist for each of them, that would mean running twenty SQL queries in total. This is a common issue when working with databases, called the **n+1 problem**.

Thankfully, we can retrieve all this information in a single SQL query, using what is called a **join**.

A join query "combines" rows from different tables in the same result set, based on a relationship between those tables. Essentially we're running a single SQL query, but getting results from more than one table. (this technique is called **eager loading**)

Here is the general syntax:

```
SELECT [columns to select]
  FROM [table name]
  JOIN [other table name]
  ON [join condition]
```

Let's breakdown an example:

```sql
SELECT albums.id, albums.title, artists.id, artists.name
  FROM albums
    JOIN artists
    ON artists.id = albums.artist_id;
```

 * The first table we're querying on the left of the `JOIN` keyword is `albums`. We'll call this the "left" table.
 * The second table, on the right of the `JOIN` keyword, is `artists`. We'll call this one the "right" table.
 * We're specifying how the two tables are related, with `ON`. Since every value in the foreign key `albums.artist_id` references a primary key value of `artists.id`, we're using `artists.id = albums.artist_id`. The `JOIN` will match associated records by using this condition.
 * Note that we need to prefix column names (in the list of queried columns, and in the `ON` condition) with their table name, to remove ambiguity. If you forget to do this, you might end up running into this kind of error:
    ```
    ERROR:  column reference "id" is ambiguous
    ```

## The join result set

Let's run the following query:

```sql
SELECT albums.id,
      albums.title,
      artists.id,
      artists.name
  FROM albums
    JOIN artists
    ON artists.id = albums.artist_id;
```

```
 id |        title         | id |     name     
----+----------------------+----+--------------
  1 | Doolittle            |  1 | Pixies
  2 | Surfer Rosa          |  1 | Pixies
  3 | Waterloo             |  2 | ABBA
  4 | Super Trouper        |  2 | ABBA
  5 | Bossanova            |  1 | Pixies
  6 | Lover                |  3 | Taylor Swift
  7 | Folklore             |  3 | Taylor Swift
  8 | I Put a Spell on You |  4 | Nina Simone
  9 | Baltimore            |  4 | Nina Simone
```

Even though we prefixed the column names, we still end up with two columns `id` in the result set, although they reference different things. We can specify an **alias** in the list of columns to retrieve to avoid this:

```sql
-- We added an alias for artists.id using the "AS" keyword.
SELECT albums.id,
       albums.title,
       artists.id AS artist_id,
       artists.name
  FROM albums
    JOIN artists
    ON artists.id = albums.artist_id;
```

```
 id |        title         | artist_id |     name     
----+----------------------+-----------+--------------
  1 | Doolittle            |         1 | Pixies
  2 | Surfer Rosa          |         1 | Pixies
  3 | Waterloo             |         2 | ABBA
  4 | Super Trouper        |         2 | ABBA
  5 | Bossanova            |         1 | Pixies
  6 | Lover                |         3 | Taylor Swift
  7 | Folklore             |         3 | Taylor Swift
  8 | I Put a Spell on You |         4 | Nina Simone
  9 | Baltimore            |         4 | Nina Simone
```

You'll note that we have duplicate values for the artist name (the last column of the result set). **This is expected**, as we have more than one album record for each artist. 

## Other examples

```sql
-- Find the album ID, artist ID, album title and artist name
-- of all the albums.

SELECT albums.id AS album_id,
       artists.id AS artist_id,
       albums.title,
       artists.name
  FROM artists
    JOIN albums
    ON albums.artist_id = artists.id;
```

We can also filter the result set by using `WHERE` — specifying the filter column.

```sql
-- Find the album ID, artist ID, album title and artist name
-- of all the albums
-- where the associated artist is ABBA.
--
-- (in other words, only albums by ABBA).
SELECT albums.id AS album_id,
       artists.id AS artist_id,
       albums.title,
       artists.name
  FROM artists
    JOIN albums
    ON albums.artist_id = artists.id
  WHERE artists.name = 'ABBA';
```

## Demonstration

[Here's a video demonstration.](https://www.youtube.com/watch?v=5DT7XuOqXsI)