ERROR: Cannot uninstall 'PyYAML'. It is a distutils installed project and thus we cannot accurately determine which files belong to it which would lead to only a partial uninstall.

github에서 README 대로 pystorm package를 설치시 PyYAML 버젼을 지우고 pystorms에 맞는 PyYAML을 재설치 위와 같은 에러가 발생한다.
에러를 무시하고 PyYAML을 다음과 같이 재설치 후 pystorm을 설치하면 오류가 해결된다.

pip install --ignore-installed PyYAML
