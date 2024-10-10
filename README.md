![header](https://capsule-render.vercel.app/api?type=waving&color=71B048&height=300&section=header&text=DE32기%20세번째%20프로젝트&desc=클로바%20도넛🍩모델을%20이용한%20가계부&fontSize=60&descSize=30&fontColor=ffffff&fontAlignY=40)

# Team Member: 김도현, 김령래, 김태영, 배주영, 조수진

## 📚 목차
1. [프로젝트 개요](#프로젝트-개요)
2. [프로젝트 아키텍쳐 구상](#프로젝트-아키텍쳐-구상)
3. [주요 기능](#주요-기능)
4. [설치및 사용 방법](#사용-방법)
5. [팀원 회고](#프로젝트-회고)
6. [라이센스](#라이센스)
   
## 프로젝트 개요
이 프로젝트는 영수증을 찍어서 업로드하면 자동으로 모델이 문서화해주어 추후에 어떤 분야, 어떤 날에 얼마나 쓸 수 있는지 추적할 수 있는 서비스 입니다.

## 프로젝트 아키텍쳐 구상
![project3 workflow (1)](https://github.com/user-attachments/assets/f702675c-e4ac-433c-9609-65235861176a)

## Team Repository
[TEAM 1 REPO](https://github.com/DE32-3nd-team1/DE32-3nd-team1)

## Stacks
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white) 
![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=Apache%20Airflow&logoColor=white) 
![Huggingface](https://img.shields.io/badge/-HuggingFace-FDEE21?style=for-the-badge&logo=HuggingFace&logoColor=black)
![Apache Spark](https://img.shields.io/badge/Apache%20Spark-FDEE21?style=for-the-badge&logo=apachespark&logoColor=black)

## 주요 기능

1. **이미지 업로드 후 데이터 베이스 저장**
   - 사용자는 **Streamlit** 인터페이스를 통해 영수증 이미지를 업로드할 수 있습니다.
   - 업로드된 이미지의 경로는 **FastAPI**로 전송되어 데이터베이스에 저장됩니다.
   - 업로드된 이미지는 aws 서버에 저장되어 추후 이미지의 경로와 함께 모델의 input으로서 사용됩니다.

2. **자동 예측 및 로그 기록**
   - **Airflow**를 사용하여 정해진 시간단위마다 머신러닝 모델이 실행됩니다.
   - **Airflow**는 자동적으로 데이터베이스에 접근하여 데이터를 얻어내고 모델을 실행시켜 그 결과를 데이터베이스에 업로드합니다.
   - 각 실행 결과는 데이터베이스에 기록되어 데이터 분석에 활용됩니다.
     
3. **관리자 페이지**
   - 관리자는 부정확하게 문서화된(예측된) 모델 처리 결과를 확인하고 이를 해당 이미지와 비교하여 수정할 수 있습니다.
   - 각 이미지에 대한 수정 작업은 **Streamlit** 관리 페이지에서 수행됩니다.
   - 관리자는 수정된 결과값을 데이터베이스에 업데이트 할 수 있습니다.

4. **데이터 집계 및 분석**
   - **PySpark**를 활용하여 예측된 데이터를 집계하고 분석합니다.
   - **Streamlit**에서 일별 소비 총액, 월별 소비 총액 등으로 소비습관을 파악할 수 있습니다.

## 사용 방법

1. Streamlit 접속(ip address/port)
2. 영수증 이미지 업로드
3. Streamlit 시각화 페이지 추후에 확인

## 설치 방법
Frontend, Backend와 Airflow, Pyspark까지 각각의 기능을 전부 Dockerizing하여 설치가 용이하도록 하였습니다. 
### Frontend Install
**Docker pull** : `$ sudo docker pull lsiwh37249/f_team1`<br />
**Docker run** : `$ sudo docker run -p 8501:8501 --name streamlit lsiwh37249/f_team1`
### Backend Install
**Docker pull** : `$ docker pull baechu805/b_team1:0.1.2`<br />
**Docker run** : `$ sudo docker run -d -p 8002:8002 --name b_team1 -e DB_IP=52.78.215.75 -e DB_PORT=53306 baechu805/b_team1:0.1.2`
### Airflow Install
**Docker pull** : `$ docker pull sooj1n/airflow:0.3.1`<br />
**Docker run** : 
```bash
$ sudo docker run -d -p 8080:8080 \
> -v /home/ubuntu/images/:/home/ubuntu/images/ \
> -v /home/ubuntu/airflow/dags/:/opt/airflow/dags/ \
> --entrypoint=/bin/bash \
> --name airflow sooj1n/airflow:0.3.1 \
> -c '(airflow db init && airflow users create --username admin --password admin --firstname Anonymous --lastname Admin --role Admin --email test@test.com); airflow webserver & airflow scheduler'
```

## 프레젠테이션
[팀ppt](https://docs.google.com/presentation/d/1eEjRoTl1rVfWlgvs5Na0BdWhGG5vo6vbI2_LrgWT-0c/edit#slide=id.g2f9df5f8404_1_75)

## 라이센스
이 라이센스는 소프트웨어의 사용, 복사, 수정, 병합, 출판 및 판매를 허가하며, 소프트웨어의 저작권 및 라이센스 고지를 포함해야 합니다.
