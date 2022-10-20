---
title: "Microservices"
theme: night
highlightTheme: tomorrow-night-bright
---

## Microservices
### take over

---

### Dev Web
- http
- nodejs 
- express

Lots of other way to do the Job (PHP, FLASK)

---

### Simple Express Server

```javascript
const express = require('express')
const app = express()

const port = process.env.PORT || 4000

app.use(express.static('www'));

app.get('/health', (req, res) => {
  res.send('ok')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})

```

---

###  one step further

- application architecture
- Dev tools (nodemon, unit test, ...)
- front (ReactJs)


---

### Docker & Reverse Proxy
- packaging
- deployment
- load balancing

---

###  one step further

- publication d'image (Nexus)
- deployment on cloud
- CI/CD

---

## Microservice is architecture

---

### From monolith to microservice

![](monolith.jpg){.fragment width="30%"}
![](monolith_split.jpg){.fragment width="40%"}


---


### Key point

- modularity
- build time
- deployment
- scaling / tuning
- responsability


---

### Network

- complexity outside the code
- network cost
- network quality
- error management 
- documentation

---

### Security

- OWASP
- oAuth2/OpenID
- token (JWT)

Communication between microservice
- certificat
- password
- token (JWT or other) 

---

### Monitoring

- logs
- metrics
- tools !!! (grafana)

---

### Assessment


https://simongomezuniv.github.io/assessment
