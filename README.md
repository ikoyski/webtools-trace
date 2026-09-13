# webtools-trace

`webtools-trace` provides a simple way to deploy and run the [Zipkin](https://zipkin.io/) distributed tracing server.

## Getting Started

### Running on Localhost (JAR)

1. Download and install Zipkin:
   ```bash
   curl -sSL https://zipkin.io/quickstart.sh | bash -s
   ```

2. Run the server:
   ```bash
   java -jar -Dserver.port=8087 zipkin.jar
   ```

3. Access the Zipkin UI in your browser:
   [http://localhost:8087/zipkin/](http://localhost:8087/zipkin/)

### Running with Docker

Run the official Zipkin image:
```bash
docker run -d -p 8187:9411 openzipkin/zipkin:latest
```
The UI will be available at `http://localhost:8187`.

### Running on Kubernetes (K8s)

You can deploy the server using the provided manifest:

1. Login to the Kubernetes host.
2. Clone this repository.
3. Navigate to the `webtools-trace` directory.
4. Apply the deployment:
   ```bash
   kubectl apply -f Deploy-webtools-trace-private.yaml
   ```

Alternatively, use the Jenkins pipeline provided in the `Jenkinsfile`.
