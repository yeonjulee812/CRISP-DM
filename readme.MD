# ![image](https://user-images.githubusercontent.com/69462995/209247019-fa05b0f2-45ad-4d07-8514-096b4a334e7e.png)

## 0. 프로젝트 개요
1. 공공 데이터를 활용한 대전광역시의 흡연 위험지역 및 취약계층 분석
2. 해당 분석 결과를 토대로 QGIS를 활용하여 시각화
3. 대전광역시의 효율적인 흡연단속원 배치와 흡연취약계층 보호에 기여

### 개발 기간
* 2022.11.18 ~ 22.12.16(4주)

### 멤버 구성(5인)
|이름|역할|담당 업무|
|---|---|---|
|장병용|팀장|`데이터 수집`, `전처리`, `EDA`, `지수 산출`, `PPT제작`, `발표`, `프로젝트 관리`|
|안지인|팀원|`데이터 수집`, `전처리`, `EDA`, `지수 산출`, `QGIS`|
|이연주|팀원|`데이터 수집`, `전처리`, `EDA`, `지수 산출`, `QGIS`, `PPT제작`|
|정수영|팀원|`데이터 수집`, `전처리`, `지수 산출`|
|박민서|팀원|`데이터 수집`, `전처리`, `EDA`, `지수 산출`, `QGIS`|

### 개발 환경
* `python 3.10`
* `QGIS 3.28.1`


## 1. 프로젝트 정의
사회적으로 정의된 단어가 아닌 `흡연위험지수`, `흡연위험지역`, `흡연취약계층`등의 단어 정의

* 흡연취약계층 - 흡연으로부터 보호해야 할 대상(어린이, 청소년, 임산부, 넓은 의미의 비흡연자)
* 흡연위험지역 - 1)흡연취약계층과 밀접한 장소, 2) 공공성이 높은 시설, 3) 흡연이 빈발하는 장소
* 흡연위험지수 - 흡연취약계층 관련 피쳐와 흡연위험지역 관련 피쳐가 밀집된 정도를 수치화한 것(행정동 단위)


## 2. 데이터 수집 및 전처리
### 데이터 수집 및 정제
* 수집된 9개의 데이터셋에 1차 정제 진행  

![image](https://user-images.githubusercontent.com/69462995/209248199-479aa773-da7c-4e52-9b6f-7ae3417493ed.png)

### 전처리 과정
![image](https://user-images.githubusercontent.com/69462995/209248266-4fc108d7-cf09-4ad9-a519-1896ff38c413.png)
![image](https://user-images.githubusercontent.com/69462995/209248328-ac7d4487-4afc-47de-8ca5-bae63429a7cd.png)

### 최종 전처리 결과
* 과태료, 금연구역, 주차장, 상권정보 4가지 데이터에서 97% 이상의 위치정보 추출 성공
![image](https://user-images.githubusercontent.com/69462995/209248366-be57900a-a636-4398-9f9a-914cc1d8e0f0.png)

### 전처리 완료 후 구성변수
![image](https://user-images.githubusercontent.com/69462995/209248443-5c39ab5b-fb64-4808-8971-cfb7dc81a0e9.png)

### 전처리 데이터 통합
* EDA를 위한 통합 데이터 프레임 생성


## 3. EDA
프로젝트 정의 단계에서 상정한 필요 피쳐와 수집한 피쳐가 어느정도 부합하는지 확인해본 단계

* 행정동 별 과태료 부과건수 비중 TOP20 , BOTTOM 20
![image](https://user-images.githubusercontent.com/69462995/209249998-8d8cc42b-5d80-479b-b2e7-5f808cb40a02.png)

* 행정동 별 노상주차장 시설 수와 과태료 부과건수
![image](https://user-images.githubusercontent.com/69462995/209250031-bc863a0a-ca3a-4835-9c20-646be0a22488.png)

* 지역구 별 흡연율 및 성별 별 흡연율 분포
![image](https://user-images.githubusercontent.com/69462995/209250137-8f04822e-4b31-4182-9efd-98e22b10c723.png)

* 행정동 별 주민등록 인구 수(Sort by 취약계층 인구수)
![image](https://user-images.githubusercontent.com/69462995/209250175-ac150770-9a61-4e59-946f-dab8cb530ed8.png)

* 취약계층 관련 변수와 흡연 위험 변수
![image](https://user-images.githubusercontent.com/69462995/209250224-c2880499-f980-479c-8d9b-5fcaaa4e258f.png)


## 4. 흡연위험지수 도출
### 흡연위험지수 산출식 설정
![image](https://user-images.githubusercontent.com/69462995/209292130-c3f3e375-997d-4778-b791-46785aa648c9.png)

### 최종 구성변수
![image](https://user-images.githubusercontent.com/69462995/209260598-3eac6284-403a-4472-b2c1-c8042f2b9a0c.png)

### 흡연발생변수 가중치 산정
![image](https://user-images.githubusercontent.com/69462995/209260662-e3ee2ec2-2671-40c8-8b32-8456e461cbcc.png)

### 취약계층변수 가중치 산정
![image](https://user-images.githubusercontent.com/69462995/209260722-f1ff76c7-ad92-476b-815e-70d609b68eb0.png)

### 행정동 별 흡연위험지수 도출
![image](https://user-images.githubusercontent.com/69462995/209260760-d4c4f20a-620a-4c0d-a1df-4e308526e48c.png)



## 5. QGIS 시각화(Output)
* 최종 아웃풋 - 대전광역시의 행정동별 흡연위험지수에 따른 시각적 구분과 관련 오브젝트들의 밀집도 시각화
![ezgif com-gif-maker](https://user-images.githubusercontent.com/69462995/209261532-0bc347d9-5efd-497e-9544-6a0b25fb4d9d.gif)


