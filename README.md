### Docker Command and Nginx Scaffolding

* ##### Application: 1
```app1
$ cd app1
$ docker build -t app1 .

# RUN: For expossing outer world
$ docker run -d -p 8080:80/tcp --name application1 app1


# Terminal: 
    ## Public check
        $ curl http://localhost:8080


# Else, not expossing (Lb doesn't required to expose)
$ docker run -d --name application1 app1
```

```docker ip app1
$ docker ps
$ docker inspect <app1-container-id>
```

* ##### Application: 2
```app2
$ cd app2
$ docker build -t app2 .

# RUN: For expossing outer world
$ docker run -d -p 8081:80/tcp --name application2 app2


# Terminal:
    ## Public check
        - curl http://localhost:8081


# Else, not expossing (Lb doesn't required to expose)
$ docker run -d --name application2 app2
```

```docker ip app2
$ docker ps
$ docker inspect <app2-container-id> | grep IP
```


* ##### Layer4: nginx
```lb4
$ cd lb4
$ docker build -t nginx-layer4 .

# LB requires to expose for accessing publiclly
$ docker run -d -p 80:80/tcp --name nginx-l4-proxy nginx-layer4

# Terminal:
    ## Public check
        - curl http://localhost:80
```

#### Implement Service Discovery (FQDN)

```
Using static container IP addresses in Docker is generally considered an anti-pattern because container network interfaces are ephemeral and change whenever a container restarts. 
To build a robust, scalable architecture, you should leverage Docker's built-in DNS service to achieve Fully Qualified Domain Name (FQDN) resolution between your containers.

$ docker-compose up -d
```