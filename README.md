# practice--docker
# Linux에서 docker 삭제 

기존 있는 도커의 오래된 버전을 삭제
``` bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

리눅스 패키지 업데이트(최신화)
``` bash
sudo apt-get update
```
설치를 위한 세
``` bash
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
``` bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | 
```
``` bash
sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
``` bash
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  sudo apt-get update
```

docker를 설치
``` bash
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

docker가 실행되었는지 확인
```bash
docker version
```






# 컨테이너 이름 또는 ID 확인


# 컨테이너 실행
```bash
docker start <CONTAINER_ID>
```



# 컨테이너 종료
실행 중인 컨테이너를 종료하는 코드는 아래와 같다.
```bash
docker stop <CONTAINER_ID>
```


실행 중인 컨테이너를 종료 / 강제 종료할 때,
```bash
docker stop $(docker ps -q)

docker kill $(docker ps -q)
```

# 컨테이너 조회

```bash
docker container ls
```
현재 시스템에서 실행 중인 모든 Docoker 컨테이너 목록을 표시
```bash
docker container ls -a
```
중지된 컨테이너도 포함하여 모든 컨테이너를 표시

# 실행 중인 Docker 컨테이너에 접속하며, 컨테이너 내부 터미널에 연결
```bash
docker attach <CONTAINER_ID>
```

# 이미지를 사용하여 새로운 컨테이너를 실행
```bash
docker run <CONTAINER_ID>
```
docker 이미지를 사용해서 새로운 컨테이너를 실행하면서, 대화형 터미널로 컨테이너 내부에 연결
```bash
docker run -it <CONTAINER_ID>
```

# 컨테이너 삭제
```bash
docker rm <CONTAINER_ID>
```
컨테이너의 파일 시스템과 설정 정보가 모두 삭제
