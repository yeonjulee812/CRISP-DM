## QGIS 시각화

### QGIS 시각화 단계
#### 1. 바탕 지도 레이어 추가
  + QGIS 상 TMS for Korea 플러그인 설치
  + TMS for Korea 플러그인 내 Kakao Street 레이어 사용<br><br>
  
#### 2. 대전 행정동 별 흡연위험지수 시각화
  + 대전 행정동별 시도군구동 코드 리스트 geojson 파일 레이어 추가
      - 파일명: 대전geojson.geojson
  + 대전 행정동별 흡연위험지수 포함한 csv 파일 레이어 추가
      - 파일명: geojson_to_csv.csv
  + 추가된 geojson 파일과 csv 파일 결합 (결합/대상 필드 = adm_cd8) 하여 레이어 병합
  + 단계 구분 값 = 흡연위험지수로 하여, 7개의 시각화 분류 값 범위 구분
  + 각 분류 별 색상 (그라데이션) 지정
  + **행정동 별 흡연위험지수 시각화 완료**<br><br>
 
#### 3. 단일 행정동 내 흡연위험 관련 오브젝트 밀집도 시각화
  + 흡연위험 관련 지역 좌표 각 csv 파일 레이어 추가 > shp 파일 변환
    - 흡연위험 지역 좌표 파일명: 흡연위험지역_QGIS.csv
    - 취약계층 지역 좌표 파일명: 취약계층지역_QGIS.csv
  + 단일 좌표 기반, 밀집도(반경 200m)에 따른 히트맵 생성
    - 흡연위험 지역 히트맵 색상: 주황색
    - 취약계층 지역 히트맵 색상: 노란색
  + **단일 행정동 내 흡연위험 관련 오브젝트 밀집도 시각화 완료**<br><br>
 

#### 4. 시각화 화면자료
![image](https://user-images.githubusercontent.com/69462995/209299890-f4210a96-5d51-48de-ae7a-e50524c3e183.png)

![image](https://user-images.githubusercontent.com/69462995/209299921-fcc095e5-20a1-43ff-a371-2c65dfb9336b.png)

![image](https://user-images.githubusercontent.com/69462995/209299948-ac6dbd36-a54e-4971-bfae-ebcc3a3152a6.png)

![image](https://user-images.githubusercontent.com/69462995/209299975-7639c91b-ad1d-41b2-90eb-b4b6fa74d559.png)

![image](https://user-images.githubusercontent.com/69462995/209300006-30c34782-8995-4584-a09f-ac68b10ff516.png)

![image](https://user-images.githubusercontent.com/69462995/209300032-021624cd-07fb-476d-b452-30c0ae4ec187.png)



