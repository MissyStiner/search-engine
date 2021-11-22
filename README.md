# Book Search Engine

## Description
This is a fully functioning Google Books API search engine built with a RESTful API refactored to be a GraphQL API built
with Apollo Server. The app was built using the MERN stack, with a React front end, MongoDB database, and Node.js/Express.js server and API. It's set up to allow users to save book searches to the back end.

## GitHub URL
https://github.com/MissyStiner/search-engine

## Application URL
https://sirchbuk.herokuapp.com/

## Steps Taken
- Set up an Apollo Server to use GraphQL queries and mutations to fetch and modify data, replacing the existing RESTful API.
- Modify the existing authentication middleware so that it works in the context of a GraphQL API.
- Create an Apollo Provider so that requests can communicate with an Apollo Server.
- Deploy the application to Heroku.

## Back-End Specifications
- auth.js: Update the auth middleware function to work with the GraphQL API.
- server.js: Implement the Apollo Server and apply it to the Express server as middleware.

## User Story
AS AN avid reader<br>
I WANT to search for new books to read<br>
SO THAT I can keep a list of books to purchase

## Acceptance Criteria
GIVEN a book search engine<br>
WHEN I load the search engine<br>
THEN I am presented with a menu with the options Search for Books and Login/Signup and an input field to search for books and a submit button<br>
WHEN I click on the Search for Books menu option<br>
THEN I am presented with an input field to search for books and a submit button<br>
WHEN I am not logged in and enter a search term in the input field and click the submit button<br>
THEN I am presented with several search results, each featuring a book’s title, author, description, image, and a link to that book on the Google Books site<br>
WHEN I click on the Login/Signup menu option<br>
THEN a modal appears on the screen with a toggle between the option to log in or sign up<br>
WHEN the toggle is set to Signup<br>
THEN I am presented with three inputs for a username, an email address, and a password, and a signup button<br>
WHEN the toggle is set to Login<br>
THEN I am presented with two inputs for an email address and a password and login button<br>
WHEN I enter a valid email address and create a password and click on the signup button<br>
THEN my user account is created and I am logged in to the site<br>
WHEN I enter my account’s email address and password and click on the login button<br>
THEN I the modal closes and I am logged in to the site<br>
WHEN I am logged in to the site<br>
THEN the menu options change to Search for Books, an option to see my saved books, and Logout<br>
WHEN I am logged in and enter a search term in the input field and click the submit button<br>
THEN I am presented with several search results, each featuring a book’s title, author, description, image, and a link to that book on the Google Books site and a button to save a book to my account<br>
WHEN I click on the Save button on a book<br>
THEN that book’s information is saved to my account<br>
WHEN I click on the option to see my saved books<br>
THEN I am presented with all of the books I have saved to my account, each featuring the book’s title, author, description, image, and a link to that book on the Google Books site and a button to remove a book from my account<br>
WHEN I click on the Remove button on a book<br>
THEN that book is deleted from my saved books list<br>
WHEN I click on the Logout button<br>
THEN I am logged out of the site and presented with a menu with the options Search for Books and Login/Signup and an input field to search for books and a submit button

## Mock-Up
A user can type a search term (in this case, "star wars") in a search box and the results appear:
![https://github.com/MissyStiner/search-engine/blob/main/assets/21-mern-homework-demo-01.gif]

The user can save books by clicking "Save This Book!" under each search result, as shown in the following animation:
![https://github.com/MissyStiner/search-engine/blob/main/assets/21-mern-homework-demo-02.gif]

A user can view their saved books on a separate page, as shown in the following animation:
![https://github.com/MissyStiner/search-engine/blob/main/assets/21-mern-homework-demo-03.gif]

## Front End Specifications
You'll need to create the following front-end files:
- queries.js: This will hold the query GET_ME, which will execute the me query set up using Apollo Server.
- mutations.js:
- - LOGIN_USER will execute the loginUser mutation set up using Apollo Server.
- - ADD_USER will execute the addUser mutation.
- - SAVE_BOOK will execute the saveBook mutation.
- - REMOVE_BOOK will execute the removeBook mutation.

Additionally, you’ll need to complete the following tasks in each of these front-end files:
- App.js: Create an Apollo Provider to make every request work with the Apollo server.
- SearchBooks.js:
- - Use the Apollo useMutation() Hook to execute the SAVE_BOOK mutation in the handleSaveBook() function instead of the saveBook() function imported from the API file.
- - Make sure you keep the logic for saving the book's ID to state in the try...catch block!
- SavedBooks.js:
- - Remove the useEffect() Hook that sets the state for UserData.
- - Instead, use the useQuery() Hook to execute the GET_ME query on load and save it to a variable named userData.
- - Use the useMutation() Hook to execute the REMOVE_BOOK mutation in the handleDeleteBook() function instead of the deleteBook() function that's imported from API file. (Make sure you keep the removeBookId() function in place!)
- SignupForm.js: Replace the addUser() functionality imported from the API file with the ADD_USER mutation functionality.
- LoginForm.js: Replace the loginUser() functionality imported from the API file with the LOGIN_USER mutation functionality.




