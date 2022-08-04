# TD 2 Node JS 

## project setup

install nodejs
init project

```
sudo apt-get install nodejs
node -v 
mkdir motus
cd motus
npm init
```


## Run server

Vanilla JS : no framework

```
const http = require('http');
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World');
});
server.listen(port, () => {
  console.log(`Server running at http://localhost:${port}/`);
});
```


## Express & Morgan

### install express & morgan

```
npm install express
npm install morgan
```

### run express

```
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
```



## Home Page
## First API

```
mkdir data
cd data
wget https://www.freelang.com/download/misc/liste_francais.zip
unzip liste_francais.zip
rm liste_francais.zip
iconv -f ISO-8859-15 -t UTF-8 liste_francais.txt -o liste_francais_utf8.txt
```

- read the word list and store it in an array variable
- generate a random sead which change everyday and get the same word for a day
- return the word on the /word endpoint

TIPS :
generate sead based on time
use modulo to get the word
test in browser 


## First Page

1 create a form with an input
2 on form submit, check if word match and return the result

TIPS :
- word.split() method can split a word into an array of characters
  - $(“#id”) get an html element
  - $(“#id”).val() get an input value
  - $(“#id”).append(...) append something to a span
  - array.include(somevalue) allow to test if somevalue is part of the array

# Some consideration

word is simply available on the page (cheating is possible)
it’s easy to test every letter
**let’s do it server side !**

# Some improvements
- store CSS and JS localy
- allow sead configuration
- improve UI 
  - color
  - form control
  - button
- score
  - localstorage
  - cookie
