# xquare-access

WebSocket 터널 기반 내부 리소스 접근 솔루션

## 사용법

### Server (K8s)

```bash
docker run -d -p 8080:8080 \
  -e PASSWORD="your-password" \
  xquare/access-server:latest
```

### Client (로컬)

```bash
docker run -d -p 5432:5432 \
  -e PROJECT_NAME="your-project" \
  -e SERVICE_NAME="postgres-service" \
  -e SERVICE_PORT="5432" \
  -e PASSWORD="your-password" \
  xquare/access-client:latest
```
