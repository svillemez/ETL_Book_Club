## ETL_Book_Club

ETL Project - Book Club Adela, Juliet, and Shannon

Data Cleanup & Analysis
 
The following sources of data were used:

 NYT Books API
 Goodreads API
 data.world: https://data.world/andidewa/books/workspace/file?filename=books.csv

The type of transformation needed for this data(cleaning, joining, filtering, aggregating, etc).

The data required cleaning, joining, and filtering.  We cleaned the data by dropping null values and filtered by specific columns.  The columns we filtered by the average ratings and isbn13 columns.  The NYT Book API data was merged with the Goodreads API data and the data.world was merged with the Goodreads API data.  


-The type of final production database to load the data into (relational or non-relational).

It was a relational database.


-The final tables or collections that will be used in the production database.

books_data

book_id int PK FK >- ratings_data.book_id
isbn13 int 
authors varchar
original_publication_year int
original_title varchar
title varchar
average_rating float
ratings_count float
whole_rating int

ratings_data

book_id int PK
rating float
average_rating float
whole_rating int FK >- NYT_Books_nonfict.whole_rating

NYT_Books_fict

List varchar
List_Date date
Title varchar
Author varchar
Weeks_On_List int
Rank_This_Week int
Publisher varchar
Primary_ISBN_13 int PK FK >- NYT_Books_nonfict.Primary_ISBN_13
Description varchar
average_rating float
whole_rating int

NYT_Books_nonfict

List varchar
List_Date date
Title varchar
Author varchar
Weeks_On_List int
Rank_This_Week int
Publisher varchar
Primary_ISBN_13  int PK
Description varchar
average_rating float
whole_rating int FK >- NYT_Books_fict.whole_rating

