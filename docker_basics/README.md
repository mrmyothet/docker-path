### Docker Basic 

```bash
docker buildx build -t myserver .

docker run -d -p 8080:80 myserver

curl localhost:8080

```

```bash
docker info

docker info | grep Storage
docker info | grep Network

docker info | grep Log
docker logs <container_name>
```

```bash
journalctl -u docker.service
```

```bash
sudo nano /etc/docker/daemon.json

sudo systemctl restart docker
```