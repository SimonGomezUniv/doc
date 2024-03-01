
```
const express = require('express')
const app = express()
const redis = require('redis')
const redis_uri = process.env.REDIS_URI || 'redis://localhost:6379'
const port = process.env.PORT || 4000

// Redis connection
const client = redis.createClient({url:redis_uri})

client.on('connect', () => {
  console.log('Connected to Redis')
})

client.on('error', (err) => {
  console.error('Redis Error:', err)
})

  
app.use(express.static('www'));

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.use('/params',(req,res)=>{
  console.log(req.query)
})

app.get('/health', (req, res) => {
  res.send('ok')
})


function pushWordToList(word) {
  client.rPush('wordList', word, (err, reply) => {
    if (err) {
      console.error('Error pushing word to list:', err);
    } else {
      console.log('Word pushed to list:', word);
    }
  });
}

/**/ 
app.get('/setScore/:score', (req, res) => {
  const score = req.params.score;
  client.set('score', score).then((data) => {
    res.send('Score set '+data);  
  })
});

app.get("/getScore", (req, res) => {
  client.get('score').then((data) => {
    res.send(data);  
  })
});

/**/
(async ()=>{await client.connect()})();

console.log("starting Server ...")

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
```

## Docker compose

```
version: '3'
services:
  redis:
    image: redis/redis-stack-server:latest
    ports:
      - 6379:6379
    volumes:
      - ./data:/data
  redisinsight:
    image: redislabs/redisinsight:latest
    ports:
      - 8001:8001
    depends_on:
      - redis
  node:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - 3000:4000
    volumes:
      - .:/app
    depends_on:
      - redis
      - redisinsight
    environment:
      - REDIS_URI=redis://redis:6379      
```
