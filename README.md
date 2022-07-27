## :pushpin: HappyEver
>언제나 행복한 여행 :smile: </
>(국내여행 플래너)
</br>

## 1. 제작 기간 & 참여 인원
- (2022. 5. 17.~2022. 7. 1.)
- 팀 프로젝트(총 7명, 조장)
</br>

## 2. 사용 기술
- JSP
- JAVA 8
- ApacheTomcat 8.5v
- Oracle DB
- HTML5 & CSS3
- JavaScript & JQuery
- JSON
- MyBatis
- JSTL.jar
- 카카오지도API & 한국관광공사 Tour API
</br>

## 3. 프로젝트 개요
>코로나19 팬데믹으로 지친 클라이언트를 위해 보다 편리한 국내여행 플래너 웹사이트를 제작하였습니다. 
>
>클라이언트가 원하는 여행 지역을 선택하면, 플래너 제작 페이지로 넘어가며 해당 지역의 추천 여행지를 보여줍니다.
>
>클라이언트의 여행 계획에 맞춰 원하는 날짜에 원하는 관광지를 플래너에 추가할 수 있으며,
>
>완성된 여행 계획은 마이페이지에서 열람이 가능하고 게시판에 업로드까지 할 수 있습니다.
>
>![image](https://user-images.githubusercontent.com/101616249/181298194-1075f250-786c-4206-9c46-c170489510e9.png)

</br>

## 4. 설계
### 화면구현 사이트맵
![image](https://user-images.githubusercontent.com/101616249/181298709-9ce3dcd9-66ec-4a0f-938c-e63841fb9871.png)
</br></br>

### ERD
![image](https://user-images.githubusercontent.com/101616249/181298973-f9b13656-58f3-43ea-9235-bc38260eea9d.png)


---

- 혼커 족보 설명</br>
![혼커 족보 설명](https://user-images.githubusercontent.com/101616249/180952863-ad257483-982c-406a-b622-3b8e611c3981.PNG)
</br>

## 5. 핵심 기능

5-1. 게임 준비
- 포커 덱 만들기
>![포커 덱 만들기](https://user-images.githubusercontent.com/101616249/180955008-a68a9a98-e7b4-468f-917b-1d9d70c5c4ac.PNG)
</br>

- 포커 덱에서 이용자에게 보낸 카드를 버리기
>![포커 덱에서 보낸 카드 버리기](https://user-images.githubusercontent.com/101616249/180955152-1f80c653-1573-4013-b893-daeac83a0d4e.PNG)
</br>

- 베팅 메서드
>![베팅 메서드](https://user-images.githubusercontent.com/101616249/180955209-738ea73e-d443-468e-8b1f-d5621c78c089.PNG)

5-2. 패의 족보 판정하기(높은 족보 순으로 점수 부여)
- Jokbo.java 참고

## 6. 트러블 슈팅
- 가장 높은 족보인 '스트레이트플러쉬'에서 플러쉬와 스트레이트를 동시에 판별하기
>먼저, 동일한 문양 의 갯수가 5개일 때를 판별한 후, 같은 문양인 카드의 갯수가 5개 이상일 때,
>4칸 차이나는 카드 수의 차가 4일때 스트레이트로 판별</br>
>![image](https://user-images.githubusercontent.com/101616249/180962440-8aa467ab-c9e1-4c35-9c60-ae1456839f4f.png)</br>

---

- 숫자와 문양이 합쳐져 있는 카드에서 숫자만 도출하기
>정규표현식을 사용하여 숫자만 사용가능
>![image](https://user-images.githubusercontent.com/101616249/180962916-2f33dbd3-965a-42c2-bcc8-4f4cb3ebe0c8.png)

---





