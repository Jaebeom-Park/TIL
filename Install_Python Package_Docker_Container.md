# 도커 컨테이너에 파이썬 패키지 설치 방법
우리가 사용하고자 하는 파이썬 패키지가 도커에 설치되지 않았거나 올바르게 설치되지 않았을 때 패키지를 가져오기 할수 없으며 다음과 같은 오류 메세지가 발생한다.  

> ImportError: No module named '<PACKAGE_NAME>' 

도커 컨테이너 관련 다음과 같은 내용을 주목해야 한다.  
* dockerfile을 통해 설치한 패키지와 laptop machine을 통해 설치한 패키지는 다른 폴더에 위치
* 사용자가 10개 패키지를 laptop machine에 설치했다고 가정하자. docker container는 해당 패키지를 인식하지 못한다. docker container는 격리되어 있기 때문이다.

Docker Conatiner에 파이썬 패키지를 설치하는 방법은 다음과 같다.

# Option 1 - docerfile 이용
기존 docker image의 dockerfile을 수정하거나 추가 패키지 설치 명령어를 포함하는 신규 dockerfile을 작성한다. 
```console
FROM docker-dev.artifactory.company.com/centos:7.3.1611 
***
dockerfile의 기존 명령어
***
***
신규 패키지 설치 명령어
***             
RUN yum install -y krb5-devel          
RUN yum install -y python-devel   
RUN yum install -y krb5-workstation   
RUN yum install -y python-setuptools   
RUN yum install -y python-pip    
```
# Option 2 - container console 이용
docker container에 login하고 직접적으로 package를 설치할 수 있다. 이것을 위해 container의 console 환경으로 가서 install 명령어를 실행한다.
다음 명령어를 이용하여 container의 console 환경으로 집입한다.

```console
docker exec -it <docker_container_name> /bin/bash
```
container의 console을 열고 다음과 같이 package를 설치한다.

```console
 pip install numpy
```


