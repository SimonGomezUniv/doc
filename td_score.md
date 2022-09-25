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


### number of word guess

First we want to display the number of word guess by the user

When the user correctly guess a word, store this information in the local storage

create a score page that will display the number of word guessed by the user

TIPS : 
- to be able to test, you will need an easy method to change the current word
- make a dedicated API seems a great way to to this)

### improve the score

for each word guess we want to keep the number of try
we want to display the average number of try in the score page


