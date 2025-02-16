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