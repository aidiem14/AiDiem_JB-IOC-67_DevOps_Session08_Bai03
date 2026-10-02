# Session08 - Bài 3
## Build và Push Image lên GitHub Container Registry

### 1. Build JAR

./gradlew clean bootJar

### 2. Build Docker Image

docker build -t payment-service:1.0.0 .

### 3. Kiểm tra image

docker images payment-service

### 4. Đăng nhập GHCR

read -s CR_PAT
echo "$CR_PAT" | docker login ghcr.io -u aidiem14 --password-stdin
unset CR_PAT

### 5. Tag image

docker tag payment-service:1.0.0 ghcr.io/aidiem14/payment-service:1.0.0

### 6. Push image

docker push ghcr.io/aidiem14/payment-service:1.0.0

### 7. Package URL

https://github.com/users/aidiem14/packages/container/package/payment-service