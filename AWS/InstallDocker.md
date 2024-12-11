### Install Docker in virtual server
```
sudo dnf install -y docker
```

### Start Docker in virtual server
```
sudo systemctl start docker
```
or
```
systemctl start docker
```

### Pull image from Dockerhub
```
sudo docker pull notafraid/application-backend
```

### Re-mark (tag) the Docker image
```
docker tag application-backend:latest notafraid/application-backend:latest
```
