# Microservice - les pré-requis

les outils suivants vont être utilisés pendant les deux premières journée :

### instalation via apt

- telnet
- curl
- wget
- netcat
- nodejs
- haproxy
- docker
- docker-compose

### instalation via npm

après avoir installer nodejs, l'outil de gestion de package npm doit être disponible 

- express
- express-session
- jsonwebtoken

```
cd /myWorkDir/src
mkdir microservice
cd microservice
npm install express
npm install express-session
npm install jsonwebtoken
```

### instalation via docker 

```
docker pull redis
docker pull redislabs/redisinsight 
```

### IDE

Vous pouvez choisir votre IDE préféré pour développer, j'utiliserai VS Code pendant les cours. 
