# Cho_dataset

논문 "인공지능 활용 초서 OCR 개발 과정과 과제"에 사용된 학습데이터 원본이다.

## 
![Untitled](https://github.com/DBChoi85/Cho_dataset/assets/43774570/49214bfb-5fe5-4fd4-845f-4f1adf8c04db)

1. 한국학자료포털을 통해서 초서 85,285자, 행서 184,800자를 크롤링하였다. 크롤링 결과를 바탕으로 크롤링 되지 않은 유니코드 2,227종을 대상으로 중국 “書法大師” 사이트를 통해서 추가로 글자를 수집하였다. 추가로 수집된 글자는 2,227종 중 1,567종 17,010자이다. 
2. 한국학자료포털 기준 전체 유니코드 개수는 4,835개이며, 이중 299종은 중국  “書法大師” 에서도 자료를 찾지 못하였다.
3. 크롤링된 최종 결과는 유니코드 4,536개를 대상으로 총 287,095자 이다.
4. 크롤링된 결과물 중 382개의 유니코드는 1개의 자료만 수집되었으며, 자료가 10개 이하인 유니코드는 총 2039종, 자료가 20개 이하인 유니코드는 총 3,399종으로 전체 4,536 종 중 약75%가 20개 이하의 자료로 구성되어 있다.

### 특이점

1. 배경에 노이즈정도의 차이가 있으나 대부분 배경에 노이즈가 존재
    1. 약한 노이즈
        
        ![c6ef8c3a47f047baafc271a04096b249](https://github.com/DBChoi85/Cho_dataset/assets/43774570/41201d57-9eaf-4867-8b86-112d0a589061)

    2. 강한 노이즈
        
        ![960c232b258f4473848e4c31552e173f](https://github.com/DBChoi85/Cho_dataset/assets/43774570/6e8c992f-aed9-446d-9dbc-713f8dbb4c3e)

2. 가장 큰 이미지는 size = (438, 135, 3), path =  U4E26/d4008851093343c4b4e6492de5206110.jpg, img = 
    
    ![d4008851093343c4b4e6492de5206110](https://github.com/DBChoi85/Cho_dataset/assets/43774570/c25f203a-f58f-4e07-b72b-49a57c7a932d)

3. 가장 작은 이미지는 size = (26, 81, 3), path =  ./beijing/U5FC3/82a5249cdb4b4193bc355d59045f2499.jpg, img =
    
    ![82a5249cdb4b4193bc355d59045f2499](https://github.com/DBChoi85/Cho_dataset/assets/43774570/551951f2-4c7d-48e1-b637-c8cf292a7b46)

4. 색이 반전된 이미지가 존재
5. 단순한 선 형태의 이미지가 다수 존재함
    
    ![de8534fbd1644479afaa59434ea444e5](https://github.com/DBChoi85/Cho_dataset/assets/43774570/010e1845-95d8-4dd2-ba21-c7150240898e)

    ![3fb470cab30347d79174a0bbc996f669](https://github.com/DBChoi85/Cho_dataset/assets/43774570/338c2f9a-0df2-4e48-b249-a51b9f988beb)

