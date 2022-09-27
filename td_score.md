# Adding score management to your MOTUS application 

## Add a local user management

### Localstorage

let's play with localstorage

When your motus APP is running in the browser, check if there is a username available in the localstorage
- if so : use it to show the username
- if not : redirect the user to a login page

The login page will be a simple form asking for a name.
When the login is input, store it in the localstorage and redirect to the main page

- Add a button on the main page that will handle a logout by removing the data from the localsorage

- Login & play 
- Close your browser
- Re-open your browser, are you still log in ?

### Session storage

- Change your code to replace localstorage by session storage
- Login & play 
- Close your browser
- Re-open your browser, are you still log in ?
- Go back to localstorage

## Keep the score

### Number of word guess

First we want to display the number of word guess by the user

- When the user correctly guess a word, store this information in the local storage
- Create a score page that will display the number of word guessed by the user

TIPS : 
- to be able to test, you will need an easy method to change the current word
- make a dedicated API seems a great way to to this)

### Improve the score

For each word guess we want to keep the number of try
we want to display the average number of try in the score page
