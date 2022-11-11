# 扫描器准备工作

## 安装 sonar-scanner

```bash
brew install sonar-scanner
```

## 使用

login：启动后创建本地工程时创建的 token

1.可以通过添加 java 启动参数 -D 的方式扫描本地项目

```bash
sonar-scanner \
  -Dsonar.projectKey=x \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=828090dd8992ac45bc109202fcd8adae797c2b3e
```

2.(推荐)可以通过在项目根目录添加 sonnar-project.properties 文件方式扫描本地项目

```properties
sonar.projectKey=bmall
sonar.projectName=bmall
sonar.host.url=http://localhost:9000
sonar.login=828090dd8992ac45bc109202fcd8adae797c2b3e
sonar.sources=.
sonar.exclusions=test
sonar.java.binaries=target
sonar.java.libraries=target
sonar.language=java
sonar.scm.provider=git
```

添加完毕后，可以通过命令直接扫描分析项目

```bash
sonar-scanner
```

## 镜像相关

### 社区 sonarqube-arm 镜像

```bash
docker pull koolwithk/sonarqube-arm
```

### 也可以自己编译镜像 download 下载，也可通过官网下载

```bash
git clone https://github.com/SonarSource/docker-sonarqube
cd docker-sonarqube/9/community
docker build -t sonarqube-arm .
```
