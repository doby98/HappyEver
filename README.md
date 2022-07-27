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

---

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

---

## 6. 핵심 코드

### 6-1. 한국관광공사 API를 이용해 받아온 JSON 형식의 데이터를 테이블에 INSERT 하기
![image](https://user-images.githubusercontent.com/101616249/181307577-4f9064fc-45e8-45cd-89ed-62fe01ffec0a.png)
![image](https://user-images.githubusercontent.com/101616249/181307870-1872988c-ebfe-4e25-86c8-c9d9b2a2e94b.png)

- API를 통해 JSON 형식으로 받아온 데이터 중 필요한 정보들을 추려서 list 객체에 담아 Parameter로 넘긴다.
- 넘어온 데이터를 DB 테이블과 동일한 순서와 타입으로 세팅한 후 MVC2 방법을 이용해 처리한다.</br></br>

### 6-2. 회원탈퇴 기능 구현
1. 넘어온 URL을 판별하여 해당 기능을 구현한 Action 메서드 실행</br>
![image](https://user-images.githubusercontent.com/101616249/181308881-0d544c11-b340-4883-b368-fc4ea0c38665.png)</br>
2. 메서드에서 회원탈퇴를 진행할 DAO로 이동</br>
![image](https://user-images.githubusercontent.com/101616249/181308924-54168b31-345f-4935-83f3-f863a67c14ce.png)</br>
3. DAO에서는 회원탈퇴에 해당하는 쿼리문을 실행</br>
![image](https://user-images.githubusercontent.com/101616249/181308995-63f6b8ad-7566-4b4d-8e40-cac48cbdcd3e.png)</br>
4. 해당 쿼리문을 통해 DB 테이블에서 delete 성공</br>
![image](https://user-images.githubusercontent.com/101616249/181309165-df61822f-2d3c-4be7-9b2b-640cb6326b28.png)</br>

- MVC2 방법을 이용한 회원탈퇴 기능 구현
- session에 담긴 이메일을 이용하여 회원탈퇴 진행, DB 테이블에서 로그인 되어있는 이메일과 일치하는 데이터 삭제 
</br></br>

---

## 7. 트러블 슈팅

### 일정만들기 페이지에서 관광지를 각 DAY 영역에 독립적으로 추가 및 삭제하기 문제
![image](https://user-images.githubusercontent.com/101616249/181312002-c2110165-9198-4f27-84d6-4e04b66f031b.png)
![image](https://user-images.githubusercontent.com/101616249/181312702-4eb9f44f-3932-4669-8746-9ce6ffc302bb.png)

- 추가버튼(+)을 누르면 좌측 영역에 선택한 관광지의 정보를 innerHTML을 통해 입력
- day_filter를 통해 각 DAY에 해당하는 값을 가지고 있는 관광지만 보여주기 

---





