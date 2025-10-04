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

### Docker on Windows

```bash
winget install Docker.DockerDesktop

docker version
```

### Recommended Tools

- Windows Terminal
- Powershell
- VS Code

```bash
winget search WindowsTerminal

winget search powershell
winget install Microsoft.PowerShell

Set-PSReadLineOption -PredictionSource HistoryAndPlugin

winget search vscode
winget install Microsoft.VisualStudioCode
```

```bash
docker container run --rm -it -p 8080:80 nginx

docker container run --rm -it -p 10000:10000 envoyproxy/envoy

docker container run --rm -it -p 8080:8080 jenkins/jenkins

docker run --rm -it -p 8111:8111 jetbrains/teamcity-server
```

### Intro to Kubernetes

```bash
kubectl create deployment my-app --image=my-app-image

kubectl get pods
kubectl get services
```

##### Scaling and Monitoring a Deployment

```bash

kubectl apply -f 01_first_manifest.yml
kubectl scale deployment nginx-deployment --replicas 10
kubectl get pods

kubectl scale deployment nginx-deployment --replicas 3
kubectl get pods

```

##### Scaling a stateful application

```bash
kubectl apply -f 01_statefulset.yml
kubectl scale statefulset datacamp-statefulset --replicas 10
kubectl get pods

kubectl scale statefulset datacamp-statefulset --replicas 5
kubectl get pods
```

##### Monitoring Pods and Storage

```bash
kubectl apply -f 01_pods.yml -f 02_pvc.yml
kubectl get pv

kubectl describe pvc | grep "Used By" -B 3 -A 2
```

##### StatefulSet With Attached Storage

```bash
kubectl apply -f 01_namespace.yml
kubectl apply -f 02_statefulset.yml

kubectl get pvc -n datacamp

kubectl scale statefulset -n datacamp --replicas 10
kubectl get pvc -n datacamp
```

##### Deploy a Service

```bash
cat *.yml

kubectl apply -f 01_deployment.yml -f 02_service.yml
kubectl describe service datacamp-service

kubectl scale deployment datacamp-deployment --replicas 5
kubectl describe service datacamp-service

```

##### Deploy an ETL pipeline on Kubernetes

```bash
kubectl logs pod-load

kubectl logs pod-list-files
```
