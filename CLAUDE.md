# webtools-trace

This repository provides deployment configurations for the Zipkin tracing server.

## Build and Run Commands
- **Run locally (Jar)**:
  - Download: `curl -sSL https://zipkin.io/quickstart.sh | bash -s`
  - Start: `java -jar -Dserver.port=8087 zipkin.jar`
- **Run locally (Docker)**:
  - `docker run -d -p 8187:9411 openzipkin/zipkin:latest`
- **Deploy to Kubernetes**:
  - `kubectl apply -f Deploy-webtools-trace-private.yaml`

## Testing
- Verify the server is running by accessing the Zipkin UI:
  - Jar: `http://localhost:8087/zipkin/`
  - Docker: `http://localhost:8187`

## Guidelines
- This project is a deployment wrapper for the official Zipkin server.
- Any changes to deployment manifests should be tested against a K8s cluster.
