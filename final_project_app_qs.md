# SI 364 - Final Project questions

## Overall

* **What's a one-two sentence description of what your app will do?**
The user will enter a movie that they want to find out more information about and then using the OMDB API the app will email them information about the movie based on what kind of information they want to receive.

## The Data

* **What data will your app use? From where will you get it? (e.g. scraping a site? what site? -- careful not to run it too much. An API? Which API?)**

OMDB API--Then sorting through JSON I will be able to decide which info they receive based on their preferences.

* **What data will a user need to enter into a form?**
The Title and Year of the movie

* **How many fields will your form have? What's an example of some data user might enter into it?**
1 Text entry form to type in the name of the movie 
1 Text entry form for them to enter their email address
1 Submit button
A bunch of check boxes to decide which info the user wants to receive

* **After a user enters data into the form, what happens? Does that data help a user search for more data? Does that data get saved in a database? Does that determine what already-saved data the user should see?**
The user enters data into the form which is then entered into the OMDB API. The email address entered can be stored in a db along with the users movie title input. Then a new database can be created for the movie title to be stored with along with all of the infomation from the OMDB API about the movie. This way the databases can be cross-referenced to store infomation and send it to the right email address.

* **What models will you have in your application?**
User, Movie, Search, Movie_Information

* **What fields will each model have?**
User - User_ID, email, username 
Movie- Movie_ID, Movie_Title, 
Search- User_ID, Movie_ID 
Movie_Information- Movie_ID, Movie_Title, Rotten_Rating, Meta_Rating, IMDB_Rating, Actors, Year, Directors, Actors

* **What uniqueness constraints will there be on each table? (e.g. can't add a song with the same title as an existing song)**
The movie information database will not add the same title twice. If a title is entered that is already stored in the database then it will return the infomation in the database that it has already stored to the new email address/user requesting the information.

* **What relationships will exist between the tables? What's a 1:many relationship between? What about a many:many relationship?**
User-Search: 1 to many
Search-Movie: 1 to many
Movie-Movie_Information: many to many


* **How many get_or_create functions will you need? In what order will you invoke them? Which one will need to invoke at least one of the others?**

1st for the user
2nd for the Movie
3rd for the Movie_Information for the Movie_Title

Movie will invoke the user email to send to and the movie_information to search for and store



## The Pages

* **How many pages (routes) will your application have?** 4

* **How many different views will a user be able to see, NOT counting errors?** 3

* **Basically, what will a user see on each page / at each route? Will it change depending on something else -- e.g. they see a form if they haven't submitted anything, but they see a list of things if they have?**

1) Form that allows user to input movie title and email adress and what data it should return with checkboxes
2) Results page will have the movie information they asked for
3) Error (movie not found, etc.)
4) History: A list of the username and all of their previous searches

## Extras

* **Why might your application send email?**

My application will send an email to send the information about a movie that a user requests

* **If you plan to have user accounts, what information will be specific to a user account? What can you only see if you're logged in? What will you see if you're not logged in -- anything?**
If a user is logged in they can view their past searches...otherwise an error message will show that they are not logged in and there is no history to view

* **What are your biggest concerns about the process of building this application?**
Working with the check boxes and history aspects of this app.
