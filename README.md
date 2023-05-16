# Cho_dataset

논문 "인공지능 활용 초서 OCR 개발 과정과 과제"에 사용된 학습데이터 원본이다.

## 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ab989794-a150-4c08-8892-98a8c15de8ac/Untitled.png)

1. 한국학자료포털을 통해서 초서 85,285자, 행서 184,800자를 크롤링하였다. 크롤링 결과를 바탕으로 크롤링 되지 않은 유니코드 2,227종을 대상으로 중국 “書法大師” 사이트를 통해서 추가로 글자를 수집하였다. 추가로 수집된 글자는 2,227종 중 1,567종 17,010자이다. 
2. 한국학자료포털 기준 전체 유니코드 개수는 4,835개이며, 이중 299종은 중국  “書法大師” 에서도 자료를 찾지 못하였다.
3. 크롤링된 최종 결과는 유니코드 4,536개를 대상으로 총 287,095자 이다.
4. 크롤링된 결과물 중 382개의 유니코드는 1개의 자료만 수집되었으며, 자료가 10개 이하인 유니코드는 총 2039종, 자료가 20개 이하인 유니코드는 총 3,399종으로 전체 4,536 종 중 약75%가 20개 이하의 자료로 구성되어 있다.

### 특이점

1. 배경에 노이즈정도의 차이가 있으나 대부분 배경에 노이즈가 존재
    1. 약한 노이즈
        
        ![c6ef8c3a47f047baafc271a04096b249.jpg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7f51d404-620c-4e49-bc42-6e48c5eca775/c6ef8c3a47f047baafc271a04096b249.jpg)
        
    2. 강한 노이즈
        
        ![960c232b258f4473848e4c31552e173f.jpg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0197571a-394d-4b2c-bdee-b08b28cfe050/960c232b258f4473848e4c31552e173f.jpg)
        
2. 가장 큰 이미지는 size = (438, 135, 3), path =  U4E26/d4008851093343c4b4e6492de5206110.jpg, img = 
    
    ![d4008851093343c4b4e6492de5206110.jpg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/46ecda02-16ac-4b41-a108-ed2f8911805d/d4008851093343c4b4e6492de5206110.jpg)
    
3. 가장 작은 이미지는 size = (26, 81, 3), path =  ./beijing/U5FC3/82a5249cdb4b4193bc355d59045f2499.jpg, img =
    
    ![82a5249cdb4b4193bc355d59045f2499.jpg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/69542d81-c27e-454f-bf96-f216c5be2570/82a5249cdb4b4193bc355d59045f2499.jpg)
    
4. 색이 반전된 이미지가 존재
5. 단순한 선 형태의 이미지가 다수 존재함
    
    ![de8534fbd1644479afaa59434ea444e5.jpg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/68b3bfb3-e8b8-473d-9604-706039bf6651/de8534fbd1644479afaa59434ea444e5.jpg)
    
    ![3fb470cab30347d79174a0bbc996f669.jpg](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4ab41fab-5d5b-4938-b94f-90e36a2b4278/3fb470cab30347d79174a0bbc996f669.jpg)
    
6. 추가로 수집된 자료의 확장자는 png로 jpg 변환이 필요함.

### 작업 예정 사항

1. data normalize
    1. 사이즈 통일 
        1. 원본이 왜곡되지 않는 사이즈를 탐색
    2. 이미지 개수가 적은 유니코드에 대해서 data agumentation을 적용
        1. 모든 이미지에 색 반전 적용
        2. 사이즈 조정을 통한 data agumentation적용
    3. 이미지 개수가 많은 유니코드에 대해서 down sampling 적용
2. model 탐식
    1. 후보 model
        1. CoCa
        2. EffNet
        3. ViT-G
        4. VGG 계열
3. model 선정
    1. 모델 특징 분석을 통해서 현재 SOTA인 CoCa 모델로 인식기 개발에 착수.
