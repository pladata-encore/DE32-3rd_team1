# 데이터 엔지니어 32기 3rd Project 1팀
김도현, 김령래, 김태영, 배주영, 조수진
## 영수증으로 가계부 만들기 프로젝트
(여기에 데모 이미지 올리기)
## Introduction
영수증을 찍어서 업로드하면 자동으로 모델이 문서화해주어 추후에 어떤 분야, 어떤 날에 얼마나 쓸 수 있는지 추적할 수 있는 서비스 입니다.
## Team Repository
[TEAM 1 REPO](https://github.com/DE32-3nd-team1/DE32-3nd-team1)
## 프로젝트 아키텍쳐 구상
![project3 workflow](https://github.com/user-attachments/assets/e177fa17-bbf5-4ca1-941e-423432863a6f)
## ⚙️ Stacks
### **Frontend**
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
### **Backend**
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
### **Database**
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white)
### **Pipeline**
![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=Apache%20Airflow&logoColor=white)
### **Model**
![Donut](https://img.shields.io/badge/🍩?style=for-the-badge&logo=🍩&logoColor=Brown)
### **Data Processing**
![Apache Spark](https://img.shields.io/badge/Apache%20Spark-FDEE21?style=flat-square&logo=apachespark&logoColor=black)
## Installation
Frontend, Backend와 Airflow, Pyspark까지 각각의 기능을 전부 Dockerizing하여 설치가 용이하도록 하였습니다. 
### Frontend Install
**Docker pull** : `$ sudo docker pull lsiwh37249/f_team1`<br />
**Docker run** : `$ sudo docker run -p 8501:8501 --name streamlit lsiwh37249/f_team1`
### Backend Install
**Docker pull** : `$ docker pull baechu805/b_team1:0.1.2`<br />
**Docker run** : `$ sudo docker run -d -p 8002:8002 --name b_team1 -e DB_IP=52.78.215.75 -e DB_PORT=53306 baechu805/b_team1:0.1.2`
## 기능 소개

## 프로젝트 회고
**김도현**:
