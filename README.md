# Docker_study
도커를 설치 및 사용해보기


### 설치
wsl2 기반으로 docker desktop을 설치함.

### 기능
#### Images
도커에서의 저장된 형상. <br/>
오픈된 다른 Images를 다운받아 사용 할 수 있고, 직접 commit으로 구워 저장할 수 있다. <br/>
```bash
docker images
현재 실행중인 docker desktop의 images 목록을 불러온다
docker rmi imageId
이미지를 삭제한다.
```
#### Container
저장된 image를 이용해 별개의 os를 생성하는 개념. <br/>
```bash
docker ps
현재 실행중인 컨테이너들을 불러온다
```
image를 이용해 컨테이너 실행하기
```bash
docker run -it -v /C/path:/ContainerPath imageName:imageTag /bin/bash
-it는 양방향 터미널, -v는 두 디렉토리를 마운트한다는 뜻
뒤에는 image이름과 태그를, 그리고 마지막으로는 기본으로 사용할 쉘을 설정해줌
exit
종료
```
컨테이너에서 앱 다운로드 ex)gcc, gdb
```bash
yum -y install appName
이때 -y는 다운로드 과정에서 모두 Yes로 대답한다는 뜻
```

컨테이너에서 설정한 환경을 이미지로 저장 가능
```bash
docker commit containerId newName
commit 뒤에 컨테이너 id를 넣고 그 뒤 저장할 이름을 지정한다.
```
