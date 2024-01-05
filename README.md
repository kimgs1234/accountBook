# 가계부 팀 프로젝트 
## 프로젝트 개요
가계부의 앱에서 지출 등록을 하면 메인화면에 메인화면에 지출이 등록되어 한눈에 볼 수 있게 하면서 차트 페이지로 그 지출 내역을 시각화하는 앱을 구현하기로 하였다. <br>
부가적으로 로또 번호 자동으로 추출되는 기능도 넣어보았다.

## 기획의도 & 목표
MongoDB를 이용해 회원가입과 로그인을 구현하고 앱을 사용하면서 실제 예산관리를 하여 지출을 줄여보는 앱을 만들고자 함

### 목표
*	리액트 경험을 늘리고 사용 기술 향상
*	앱의 가독성을 위한 기본적인 UI/UX 디자인을 파악
* 팀원 들과의 협업을 통해 커뮤니케이션 능력 향상
*	MongoDB와 express를 이용해 로그인/회원가입을 구현
  
## 프로젝트 작업 순서
1. 팀원과 자기 소개 후 앱 선정과 역할 분담
2. 워크플로우와 기능적 요구사항 분석
3. 디렉토리 구조 설정
4. git organization 레파지토리 생성
5. UI 디자인 완성
6. 가계부 앱 만들기
7. 가계부 회원 가입 / 로그인 MongoDB에 연결
8. PPT 발표

## 사용기술
* Tool : GitHub , figma <br>

### 프론트엔드
* 라이브러리/프레임워크 : React
* 언어 : javascript
* 기타 도구 및 라이브러리 : React-calendar , React-router-dom , Rechart

### 백엔드
* 런타임 환경 : Node.js
* 웹 프레임워크 : Express
* 세션 관리 : Express-session
* 비밀번호 해싱 : sha-256
  
### 데이터 베이스
* 데이터 베이스 : MongoDB

## 담당업무
* 프로젝트 리더
* 지출 등록 기능 , 차트 페이지 구현 , 로그인 /회원가입 페이지 구현
* 로그인/회원가입 MongoDB 연결

## 프로젝트 내용
### 기능적 요구 사항
![기능적요구사항](https://github.com/kimks1234/accountBook/assets/142865411/b92088f1-eb25-417a-9acc-7098f9a88da4)

### 워크플로우
![1703225689702-62aa3ee4-fa60-407b-a569-11da06bb2740_1](https://github.com/kimks1234/accountBook/assets/142865411/a46dbde5-fe23-4a40-9e23-c278b1b12f96)

### 디렉토리 구조
![디렉토리구조](https://github.com/kimks1234/accountBook/assets/142865411/bad94bbf-01d7-4c10-a011-7ca3512184ce)

### 페이지 구성
![가계부](https://github.com/kimks1234/accountBook/assets/142865411/28f63a92-57e5-4c17-893c-0b8ad705fbd3)

### 문제 및 해결
#### 첫번째 문제
* 상황: 깃 허브 페이지에 결과물을 올렸는데 앱 안의 내용이 하나도 보이지 않음 <br>
* 문제확인: 라우터를 설정하면 앱 안의 내용이 보이지 않을 수 있다는 사실을 깨달음 <br>
* 해결: 프론트엔드 최상위 index.js 앱을 감싸고 있는 BrouserRouter 에 <br>
```<BrowserRouter basename={process.env.PUBLIC_URL}>``` 코드를 작성하고 다시 push와 npm run build를 하여 문제를 해결함 <br>

#### 두번째 문제
* 상황: 등록페이지 라우터에서 메인 라우터로 데이터가 전송이 되어야 하는데 저장을 눌러도 데이터가 전송이 안되는 상황 <br>
* 해결: 배운 것 중에 Context API가 생각이나 context를 통해 데이터상태관리를 하여 데이터를 다른 라우터에도 공유가 되게 함 <br>
![context](https://github.com/kimgs1234/accountBook/assets/142865411/4fd0f760-c9ee-42a7-99b5-75261a6f5977)

#### 세번째 문제
* 상황: react-chartjs-2 로 바모양 차트와 도넛모양 차트를 넣으려고 하는데 차트가 화면에 안나옴
* 해결 : 구글링을 통해 블로그도 찾아보면서 해결 해보려 하였지만 해결을 못하여서 인공지능의 활용을 통해
  ``` react
   <Doughnut
          data={{
            labels: categoryLabels,
            datasets: [
              {
                data: categoryTotal,
                backgroundColor: doughnutColors,
              },
            ],
          }}
          options={{
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
              legend: {
                display: true,
                position: "bottom",
              },
              layout: {
                padding: {
                  bottom: 150,
                },
              },
            },
          }}

  ```
  의 태그를 작성하여서 해결함 내가 option 하고 data의 활용이 미숙해서 해결 못하던 것 이었음 바모양도 비슷하게 태그를 써서 해결

## 프로젝트 완료 리뷰
### 아쉬운 부분
* 팀원과의 소통의 부재로 팀원이 잠적을 할때 연락을 따로 할수가 없었음
* css 디자인 실력의 부족으로 퍼블리싱이 완벽하지 못함
* UI 디자인이 조금 아쉬움

### 잘한 부분
* 팀원이 한명이 연락이 안되는 상황에서도 최선을 다해 팀프로젝트를 완료할수 있었음 
* 처음 사용해 보는 라이브러리도 사용법을 찾아내어 결국 사용하게 됨
* 계획에 문제가 생겼음에도 정신을 차리고 프로젝트를 완료 할수 있었음 

### 배운 점 및 주관적인 의견
팀원과 평소에 소통을 안하였고 그 결과 팀원이 잠적해도 연락을 받지 못하는 상황에 발생해 다음에 이런일이 있으면 평소에 소통을 많이 해야 겠다고 느꼇다 <br>

팀원이 연락이 안되는 바람에 많이 당황스러웠고 중간에 포기하고 싶은 마음도 있었지만 주어진 일에 최선을 다하는 과정을 통해 이건 단순한 해프닝에 불과하고 정신만 차리면 결국 일을 마무리 지을 수 있구나 하며 많이 배웠다. <br>

그리고 처음 사용해 보는 것도 결국에는 구글링과 인공지능을 활용하면 많이 도움이 되는구나 느꼈다. <br>

## 프로젝트 바로가기
<a href="https://port-0-accountlogin-hkty2alqemuiae.sel4.cloudtype.app/" target="_blank">가계부 사이트</a>
