> ERROR: Cannot uninstall 'PyYAML'. It is a distutils installed project and thus we cannot accurately determine which files belong to it which would lead to only a  partial uninstall.

github에서 README 대로 pystorm package를 설치시 PyYAML 버젼을 지우고 pystorms에 맞는 PyYAML을 재설치 위와 같은 에러가 발생한다.
에러를 무시하고 PyYAML을 다음과 같이 재설치 후 pystorm을 설치하면 오류가 해결된다.

```console
pip install --ignore-installed PyYAML
```
특히, pip -r requirements.txt를 이행하여 다수의 Package를 설치하다가 위의 문제가 발생할 수 있다. 기존의 패키지를 uninstall하고 다시 새로운 버전을 설치하는 과정에서 어떤 파일을 지워야할지 결정할 수 없기 때문에 발생하는 installation 에러이다.

```console
pip isntall -r --ignore-installed requriements.txt
```
