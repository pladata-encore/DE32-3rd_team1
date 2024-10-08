![header](https://capsule-render.vercel.app/api?type=waving&color=71B048&height=300&section=header&text=DE32기%20세번째%20프로젝트&desc=클로바%20도넛🍩모델을%20이용한%20가계부&fontSize=60&descSize=30&fontColor=ffffff&fontAlignY=40)

# Team Member: 김도현, 김령래, 김태영, 배주영, 조수진

## 📚 목차
1. [프로젝트 개요](#프로젝트-개요)
2. [프로젝트 아키텍쳐 구상](#프로젝트-아키텍쳐-구상)
3. [사용 스택](#⚙️-Stacks)
4. [주요 기능](#🎯-주요-기능)
5. [설치및 사용 방법](#🚀-설치-방법)
6. [팀원 회고](#프로젝트-회고)
7. [라이센스](#📄-라이센스) 
   
## 🔰 프로젝트 개요
이 프로젝트는 영수증을 찍어서 업로드하면 자동으로 모델이 문서화해주어 추후에 어떤 분야, 어떤 날에 얼마나 쓸 수 있는지 추적할 수 있는 서비스 입니다.
<details>
  <summary><strong>Demo 확인하기</strong></summary>

  ![test1](https://github.com/user-attachments/assets/498ea2fd-df40-4c08-b5d9-de3b283fa623)
  이미지 업로드 및 시각화 페이지 보여주기

</details>

## 🏗 프로젝트 아키텍쳐 구상
![project3 workflow](https://github.com/user-attachments/assets/e177fa17-bbf5-4ca1-941e-423432863a6f)

## Team Repository
[TEAM 1 REPO](https://github.com/DE32-3nd-team1/DE32-3nd-team1)

## ⚙️ Stacks
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white) 
![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=Apache%20Airflow&logoColor=white) 
![Huggingface](https://img.shields.io/badge/-HuggingFace-FDEE21?style=for-the-badge&logo=HuggingFace&logoColor=black)
![Apache Spark](https://img.shields.io/badge/Apache%20Spark-FDEE21?style=for-the-badge&logo=apachespark&logoColor=black)

## 🎯 주요 기능

1. **이미지 업로드 및 예측**
   - 사용자는 **Streamlit** 인터페이스를 통해 강아지 이미지를 업로드할 수 있습니다.
   - 업로드된 이미지는 **FastAPI**로 전송되어 데이터베이스에 저장됩니다.
   - 업로드된 이미지는 머신러닝 모델을 통해 강아지 품종을 예측합니다.
   - 예측 결과는 로그에 기록됩니다.

2. **관리자 페이지**
   - 관리자는 처리되지 않은 이미지를 확인하고 직접 라벨을 지정할 수 있습니다.
   - 각 이미지에 대한 라벨링 작업은 **Streamlit** 관리 페이지에서 수행됩니다.
   - 관리자는 라벨을 입력하고 제출하여 데이터베이스에 저장합니다.

3. **자동 예측 및 로그 기록**
   - **Airflow**를 사용하여 (정해진 간격?)으로 머신러닝 모델이 실행됩니다.
   - 각 실행 결과는 로그에 기록되어 데이터 분석에 활용됩니다.

4. **데이터 집계 및 분석**
   - **PySpark**를 활용하여 예측된 데이터를 집계하고 분석합니다.
   - 분석 결과는 데이터 기반 의사결정에 사용될 수 있습니다.

5. **사용자 친화적인 인터페이스**
   - **Streamlit**을 이용한 직관적인 사용자 인터페이스로 쉽게 이미지 업로드 및 라벨링 가능.
   - 관리자는 처리할 데이터가 없는 경우에도 쉽게 상태를 확인할 수 있습니다.

## 🚀 사용 방법(User 관점)

1. Streamlit 접속(ip address/port)
2. 영수증 이미지 업로드
3. Streamlit 시각화 페이지 추후에 확인

## 🚀 설치 방법(관리자 관점)
Frontend, Backend와 Airflow, Pyspark까지 각각의 기능을 전부 Dockerizing하여 설치가 용이하도록 하였습니다. 
### Frontend Install
**Docker pull** : `$ sudo docker pull lsiwh37249/f_team1`<br />
**Docker run** : `$ sudo docker run -p 8501:8501 --name streamlit lsiwh37249/f_team1`
### Backend Install
**Docker pull** : `$ docker pull baechu805/b_team1:0.1.2`<br />
**Docker run** : `$ sudo docker run -d -p 8002:8002 --name b_team1 -e DB_IP=52.78.215.75 -e DB_PORT=53306 baechu805/b_team1:0.1.2`

## 프로젝트 회고
**김도현**:
**김령래**:
**김태영**:
**배주영**:
**조수진**:

## 📄 라이센스

이 라이센스는 소프트웨어의 사용, 복사, 수정, 병합, 출판 및 판매를 허가하며, 소프트웨어의 저작권 및 라이센스 고지를 포함해야 합니다.
