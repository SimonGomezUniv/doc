# Adding score management to your MOTUS application 

## Keep the score

Target is to have a score page displaying the following information


Info | Value
-------------|---------------
Nb Word(s) found        | 42
Average try       | 3.5  



### API creation

we are going to build a new app in charge tracking score. This app will only handle the following API request :
- /setscore : which will record the score for a player
- /getscore : which will display the score of a player

Be careful of when to call the API, when user input a word, when he found today's word.

Set up both these API in a new and dedicated nodejs app :
- move your existing App in a repository 
- create a new directory and develop your app in this directory

You can store the data in a flat file or but it would be far better to store it in a dedicated database (ex Redis).
You can use the documentation available here [https://redis.io/docs/connect/clients/nodejs/](https://redis.io/docs/connect/clients/nodejs/)

### Track the score (API calls)

During the game, ensure that when needed the Api setscore is called to record the player score and number of try.

### Page creation

create a score.html page in your motus page or in your score App
add a link in your main page and a link to go back to the main game page in the score page 

This page should display the score information

TIPS :

with jQuery, you can easily update the content of a span or a div
```
<span id='score'></span>
<script>$("#score").html("42")</script>
```

### BONUS

Soon, we will think about user management, you can try to think on how you will handle score if there is more than one player.
You could create a page displaying the best player's score. 
