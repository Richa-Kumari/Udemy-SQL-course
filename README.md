# Udemy-SQL-course
Overview

This repository contains SQL queries for managing and retrieving data from a bookshop database. The queries cover basic CRUD operations, filtering, sorting, and various SQL techniques to refine data selections.

Table Schema

The database consists of a books table with the following fields:

title (VARCHAR) - The title of the book

author_fname (VARCHAR) - The first name of the author

author_lname (VARCHAR) - The last name of the author

released_year (INT) - The year the book was released

stock_quantity (INT) - The number of copies in stock

pages (INT) - The total number of pages

SQL Queries

1. Inserting Sample Data

INSERT INTO books (title, author_fname, author_lname, released_year, stock_quantity, pages)
VALUES ('10% Happier', 'Dan', 'Harris', 2014, 29, 256),
       ('fake_book', 'Freida', 'Harris', 2001, 287, 428),
       ('Lincoln In The Bardo', 'George', 'Saunders', 2017, 1000, 367);

2. Retrieving Unique Author Names

SELECT DISTINCT CONCAT(author_fname, ' ', author_lname) AS author_name FROM books;

Alternative:

SELECT DISTINCT author_fname, author_lname FROM books;

3. Sorting Data

SELECT author_fname, released_year, title FROM books ORDER BY released_year;

4. Limiting Results

SELECT title FROM books ORDER BY released_year LIMIT 5;

5. Using LIKE for Filtering

SELECT title, author_fname FROM books WHERE author_fname LIKE '%da%';

6. Advanced Queries

Finding the longest book:

SELECT title, pages FROM books ORDER BY pages DESC LIMIT 1;

Displaying a summary of the 3 most recent books:

SELECT CONCAT(title, ' - ', released_year) AS SUMMARY FROM books ORDER BY released_year DESC LIMIT 3;

Best Practices

Use column names instead of positional ordering in ORDER BY.

Utilize aliases (AS) for better readability.

Be mindful of wildcard usage in LIKE queries.

Use LIMIT for efficient result handling.

Contributing

Feel free to contribute by adding more queries or optimizing existing ones.

License

This project is open-source and available under the MIT License.
