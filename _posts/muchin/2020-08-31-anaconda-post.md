---
title: "AI - anaconda"
excerpt: "anaconda"
toc: true
toc_sticky: true
categories: ai
tags: ai
last_modified_at: 2020-09-07T08:17:00-18:00
---



## Anaconda 설치

AI에 들어가기앞서 필요한 Anaconda를 설치해야합니다.

1. anaconda 다운로드
   https://docs.anaconda.com/anaconda/install/
   해당 URL에서 OS에 맞게 설치합니다.

2. anaconda prompt 관리자 권한으로 실행
   시작프로그램에 Anaconda Prompt (anaconda3)라는 파일을 
   관리자 권한으로 실행합니다.

3. pip 최신버전으로 업데이트

   ![image-20200907221341976](C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907221341976.png)

   ``python -m pip install --upgrade pip`` 

    pip를 최신버전으로 업데이트해줍니다.
   

4. 가상환경 생성

   <img src="C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907221458774.png" alt="image-20200907221458774" style="zoom:80%;" />

   ``conda create -n data_env python=3.7 openssl``

   앞으로 사용할 가상환경 폴더를 만들어줍니다.

   - 3.7쓰는 이유 : 텐서플로우가 3.8을 지원하지않아 3.7환경에서 해야합니다.

5. 가상환경 확인

   ![image-20200907221733896](C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907221733896.png)

    

   ``conda info --envs``
   가상환경이 잘 설치되었는지 확인해줍니다.

6. 가상환경 전환

   ![image-20200907221823010](C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907221823010.png)

    

   ``activate data_env``

   기본 ``base``에서 ``data_env`` 가상환경으로 변경해줍니다.
   

7. 개발도구 IDE 설치

   ![image-20200907221927662](C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907221927662.png)

    

   ``conda install nb_conda``

   ide를 설치해줍니다.
   

8. jupyter_notebook 경로 검색
   ![image-20200907222154163](C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907222154163.png)

   ``jupyter notebook --generate-config``

   jupyter_notebook 설정 파일이 설치되어있는 폴더를 확인합니다.
   

9. config 에서 jupyter의 working directory 경로 설정

   <img src="C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907222319795.png" alt="image-20200907222319795" style="zoom:80%;" />
    ``c.NotebookApp.notebook_dir`` 

   jupyter_notebook_config.py파일에서 해당 문구를 찾아 
   주석을 해제하고 기본경로를 설정해주세요.

10. jupyter실행
    ![image-20200907222547061](C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907222547061.png)

    ``jupyter notebook``
    주피터를 실행합니다.
    <img src="C:\Users\kssam\AppData\Roaming\Typora\typora-user-images\image-20200907222625659.png" alt="image-20200907222625659" style="zoom: 50%;" />
    
