# Mise en place d'un reverse Proxy

## instalation du HA PROXY

```
sudo apt-get install haproxy 
```

## utilisation de HA PROXY

### setup

1. add a new path in your motus app /port that return "MOTUS APP listening on port XXXX" with XXXX being the actual port
2. use your motus app and make it listen on port 3000

TIPS :
-to easily specify a port on launch :
```
 const port = process.env.PORT || 3000 
 
 PORT=5000 node index.js
```


### Simple Use Case

-  configure a haproxy to listen to port 3001 and foward to port 3000


### Another Server

- configure a second motus running on port 4000
- configure a second backend on your haproxy
- do a few request on the URL /port ==> check that you can reach both server
- kill one server ==> check that your application is still working on port 3001
- relaunch the server


### Unfair balancing

- configure your haproxy to ensure 75% of the request goes to the 3000 app
- check  the configuration with a few request

### healthcheck

- configure a healthcheck URL 
- use the haproxy in debug mode 
- kill the app running on port 4000
- check the log
- check the application is still working on port 3001
- relaunch the server

### stickiness

- configure a cookie to ensure stickiness
- do a few request using your browser
- do a few request using your curl
- explain the diference


## Bonus

### utilisation d'un proxy nginx

```
sudo apt-get install nginx
```
setup a proxy using the documentation
