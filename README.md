# Flixsy
its movie recommendation website  that have major functions like- search bar for two functions accd to movie you inputed you got recommendation or according to mode you have  inputed you got recommendation 

THINGS I HAVE PERFORMED IN THIS PROJECT
Database Design
Schema Definition: I began by defining the overall schema for the movie recommendation system. This involved outlining the main entities required to store relevant data, which include:

Movies: Basic information about each movie, such as movie_id, title, release_date, overview, and other relevant metadata.
Cast: Details about the cast members associated with each movie, including movie_id, cast_name, and the character they portrayed.
Reviews: User-generated content, which comprises movie_id, author, and content of the reviews.
Table Relationships: I established relationships between the tables to ensure data integrity.

The Movies table serves as the primary entity, while the Cast and Reviews tables reference the movie_id to maintain a one-to-many relationship, meaning a single movie can have multiple cast members and reviews.
Normalization: I ensured that the database is normalized to reduce data redundancy. For example:

Rather than storing actor details repeatedly in the Movies table, I created a separate Cast table that links to the Movies table through the movie_id.
SQL Script: I wrote a schema.sql file that contains the SQL commands to create the necessary tables and establish the relationships. This script was executed in PostgreSQL to set up the database environment.

Data Types and Constraints: I specified appropriate data types for each column (e.g., VARCHAR, TEXT, DATE) and applied constraints such as NOT NULL for essential fields and PRIMARY KEY for unique identifiers to ensure data consistency and integrity.

API Integration
API Selection: I chose TMDb (The Movie Database) API for its extensive collection of movie data, including details about movies, cast, and reviews. The API offers various endpoints to retrieve specific information required for the recommendation system.

Data Fetching Scripts: I developed scripts to interact with the TMDb API. The scripts perform the following functions:

Fetch Movie Data: I wrote a function to retrieve details of a movie using its ID. This function constructs the API URL, makes a GET request, and handles the response.
Fetch Cast and Reviews: Separate functions were created to obtain the cast details and reviews for each movie. These functions utilize the corresponding API endpoints.
Error Handling: I implemented error handling in the API interaction code to manage cases where the API request might fail (e.g., due to network issues or invalid movie IDs). This ensures the application remains robust and can handle unexpected situations gracefully.

Data Storage: After successfully fetching the movie data, cast, and reviews, I wrote additional functions to insert this data into the corresponding tables in the PostgreSQL database. This involved preparing SQL INSERT statements and executing them through a database connection.

Data Consistency: I added logic to avoid duplicate entries in the database. By checking if a movie or its associated data already exists before attempting an INSERT, I ensured that the database maintains accurate and unique records.

Automation: To streamline the data population process, I created a loop that iterates through a range of movie IDs, fetching and inserting data for each. This automated approach allows for populating the database with a large dataset efficiently.
