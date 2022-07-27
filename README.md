## :pushpin: HappyEver
>### 언제나 행복한 여행 :smile:
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
>- 코로나19 팬데믹으로 지친 클라이언트를 위해 보다 편리한 국내여행 플래너 웹사이트를 제작하였습니다. 
>
>- 클라이언트가 원하는 여행 지역을 선택하면, 플래너 제작 페이지로 넘어가며 해당 지역의 추천 여행지를 보여줍니다.
>
>- 클라이언트의 여행 계획에 맞춰 원하는 날짜에 원하는 관광지를 플래너에 추가할 수 있으며,
>
>- 완성된 여행 계획은 마이페이지에서 열람이 가능하고 게시판에 업로드까지 할 수 있습니다.
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

## 5. 핵심 기능

### 5-1. 메인 페이지 & 로그인
#### <메인 페이지>
![image](https://user-images.githubusercontent.com/101616249/181301261-8514d51d-f225-4f65-a9ea-c97c2159876a.png)
![image](https://user-images.githubusercontent.com/101616249/181301310-ab941fe5-c394-4b17-9b2a-7c56b1b89ea8.png)

- 모든 페이지에서 헤더를 통해 메인 페이지로 이동 가능
- 글자를 입력할 때마다 검색 결과가 즉각적으로 변하는 검색기능 구현
- 여행지를 선택하면 일정 만들기 페이지로 이동
- 비로그인 시 사용기능 제한
</br></br>

#### <로그인 & 비밀번호 찾기>
![image](https://user-images.githubusercontent.com/101616249/181302292-5c8343e8-859b-43c1-88d4-3a175227ffb5.png)

- 정규표현식을 사용하여 이메일 형식 체크
- 사용자 정보가 틀렸을 때 alert으로 안내문구 출력
- [로그인]
  - header에 로그인 버튼 클릭시 모달창 화면 구현
  - 로그인 성공시 session에 회원정보 저장
- [비밀번호 찾기]
  - 이메일과 이름으로 회원가입 검사, 이메일로 임시 비밀번호 전송
</br></br>

### 5-2. 일정만들기 & 게시판
#### <일정만들기>
![image](https://user-images.githubusercontent.com/101616249/181305180-ab7da478-adf0-453e-8122-c6955e846f04.png)

- 선택한 여행지에 따라 화면 이동
- 지도 API와 한국관광공사 API를 이용하여 클라이언트에게 추천 장소와 위치를 제공
- 여행 날짜를 입력 시 여행 일수만큼 좌측에 DAY 생성
- DAY마다 사용자가 원하는 여행지 개별 추가 기능
- 각 DAY는 서로 독립적이다.
</br></br>

#### <게시판>
![image](https://user-images.githubusercontent.com/101616249/181305751-dff320bc-9b73-4b8e-a3a2-e53486e8c23e.png)

- 여행 키워드 클릭 또는 검색어를 입력하였을 때 동적으로 변하는 검색기능 구현
</br></br>

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





