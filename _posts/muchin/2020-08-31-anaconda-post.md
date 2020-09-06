### Anaconda 설치

1. anaconda 다운로드
2. anaconda prompt 관리자 권한으로 실행
3. pip 최신버전으로 업데이트
   python -m pip install --upgrade pip
4. 가상환경 생성
   conda create -n data_env python=3.7 openssl
   3.7쓰는 이유 : 텐서플로우가 3.8을 지원하지않음
5. 가상환경 확인
   conda info --envs

8. 가상환경 전환
   activate data_env
9. 개발도구 IDE 설치
   conda install nb_conda
10.  
11. jupyter_notebook 경로 검색
    jupyter notebook --generate-config경로 확인
12. config 에서 jupyter의 working directory 경로 설정
    ctrl + f 후 c.NotebookApp.notebook_dir 검색
13. jupyter실행



실행

