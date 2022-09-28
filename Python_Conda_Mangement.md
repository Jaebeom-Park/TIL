# Anaconda 가상환경 관리
## Conda 가상환경 생성
```
conda create -n bmp_moo python=3.7
```
C:\Anaconda3\envs 폴더 아래에 bmp_moo 폴더가 있으면 삭제 후 가상환경 생성
## 가상환경 활성화
```
conda activate bmp_moo
```
## 가상환경에 패키지 설치
(1) requirements.txt 이용
```
pip install -r requirements.txt
```
```
conda install --file requirements.txt
```
(2) github에서 직접 설치
* git과 pip 설치
```
conda install git pip
```
* github python library 설치
```
pip install git+git://github.com/scrappy/scrappy@master
```
(3) 직접 설치
* 일반적으로 conda install을 이용
* conda로 설치되지 않을 경우 pip 이용
```
pip install package-name
```
Fiona library의 경우 
```
conda install Fiona
```
## 가상환경 해제
```
conda deactivate
```
## 가상환경 조회
```
conda info --envs
```
## 가상환경 라이브러리 목록 조회
```
conda list
```
## 현재 환경에서 설치한 라이브러리 목록 저장
```
pip freeze > requirements.txt
```
## 가상환경 삭제
```
conda remove -n bmp_moo --all
```
## vscode jupyter에서 가상환경 사용하기
(1) 가상환경에 jupyter notebook 설치
```
pip install jupyter notebook
pip install ipykernel
```  
(2) 가상환경 kernel 연결하기
```
python -m ipykernel install --user --name 가상머신이름 --display-name "표시할이름"
python -m ipykernel install --user --name bmp_moo --display-name "bmp_moo"
```   
(3) vscode에서 Jupyter: create new jupyter 선택             
(4) Jupyter:Specify locat or remote jupyter server for connections에서 bmp_boo kernel 선택    
(5) jupyter-lab 명령어 실행                      
## vscode에서 프로그램 실행
(1) ctrl+shift+p > select interpeter > bmp_moo 가상환경 python 선택                    
(2) ctrl+F5 실행              
## 특정 패키지 업데이트
(1) 최신 버젼으로 업데이트         
```
pip install --upgrade  패키지 이름
```  
(2) 특정 버젼으로 업데이트    
```
pip install --upgrade  패키지 이름==버젼
pip install --upgrade scikit-learn==0.22.1
```
## 기존 코드가 실행이 안될경우 버젼에 따른 문제인지 확인 필요

