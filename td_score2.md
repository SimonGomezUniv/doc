# Adding score management to your MOTUS application 

## Keep the score

target is to have a score page displaying the following information


Info | Value
-------------|---------------
Nb Word(s) found        | 42
Average try       | data  

### Step 1 : page creation

In this step, the score should be empty
create a score.html page
add a link in your main page and a link to go back to the main game page in the score page 

### Localstorage

let's play with localstorage

On the score page initialisation, load data from the localstorage and display them in your table

if there is no data, display 0 or "no data available"

Check everything :
- change the value in your localstorage and check that your score page 
- Close your browser
- Re-open your browser and go to the score page

TIPS :

with jQuery, you can easily update the content of a span or a div
```
<span id='score'></span>
<script>$("#score").html("42")</script>
```

### Session storage

- Change your code to replace localstorage by session storage
- change the score value & display it 
- Close your browser
- Re-open your browser, check the score
- Go back to localstorage

### Track the score 

Update your motus app to properly track the score in the localstorage

Check that your score page is working properly

TIPS : 
- to be able to test, you will need an easy method to change the current word
- make a dedicated API seems a great way to to this)
  
## Add a local user management

When your motus APP is running in the browser, check if there is a username available in the localstorage
- if so : use it to show the username
- if not : redirect the user to a login page

The login page will be a simple form asking for a name.
When the login is input, store it in the localstorage and redirect to the main page

- Add a button on the main page that will handle a logout by removing the data from the localsorage


TIPS :
```
document.location = "/login.html" //will help you redirect the user on the client side
localstorate.setItem("name", "Simon")
console.log(localstorate.getItem("name") // to get a value
```
