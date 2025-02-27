# webtools-trace 

This is a using the zipkin server. Details on https://zipkin.io/


## Running on localhost

Open terminal, then

```
curl -sSL https://zipkin.io/quickstart.sh | bash -s
```

Then run the jar file

```
java -jar zipkin.jar
```

## Running on K8 (Kubernetes) 

Either use the Jenkinsfile on Jenkins or, manually login to the K8 host, clone this repo, go inside the folder, then

```
kubectl apply -f Deploy-webtools-trace-private.yaml
```


## Running on Docker

Open terminal, then

```
docker run -d -p 8187:9411 openzipkin/zipkin:latest
```
