# cf-docker-tomcat7
Docker Tomcat 7 running on Cloud Foundry


* Docker Hub

https://hub.docker.com/r/morals415/cf-docker-tomcat7/

* Build Steps

```
docker login
docker build -t cf-docker-tomcat7 .
docker images
docker tag cf-docker-tomcat7 morals415/cf-docker-tomcat7
docker images
docker push morals415/cf-docker-tomcat7
```

* CF Deployment

default deployment

```
cf push cf-docker-tomcat7 -o morals415/cf-docker-tomcat7
```

deployment without healthcheck at CF Diego to get ports mapping

```
cf push cf-docker-tomcat7 -o morals415/cf-docker-tomcat7 -u 'none'
cf app cf-docker-tomcat7 --guid
cf curl /v2/apps/<guid>/stats
```

* To Be Done
