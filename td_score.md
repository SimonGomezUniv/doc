# Adding score management to your MOTUS application 

## add a local user management

### localstorage
let's play with localstorage
when your motus APP is running in the browser, check if there is a username available in the localstorage
- if so : use it to show the username
- if not : redirect the user to a login page

the login page will be a simple form asking for a name.
When the login is input, store it in the localstorage and redirect to the main page

- add a button on the main page that will handle a logout by removing the data from the localsorage

- login & play 
- close your browser
- re open your browser, are you still log in ?

### session storage

- change your code to replace localstorage by session storage
- login & play 
- close your browser
- re open your browser, are you still log in ?
- go back to localstorage

## keep the score

to be able to test, you will need an easy method to change the current word

we want to keep track of the following data
- number of word guess
- number of tentative for each diferent word

Store this data in the local storage
create a score page that will display these data


