22.11.22.~11.28. 유화제작 프로젝트 🕵️Black Market

# Black Market

## 프로젝트 목표
업로드된 이미지를 유화로 바꿔주는 서비스 🖼

## 팀원 구성
* 팀장 : 이승연
* 팀원 : 정유준
* 팀원 : 송창주
* 팀원 : 정태희
* 팀원 : 이효정

## 역할
- 딥러닝, 백엔드 : 이효정, 이승연
- 백엔드, 프론트엔드 : 송창주, 정유준, 정태희

## 프로젝트 목표
업로드된 이미지를 유화로 바꿔주는 서비스 🖼

## 기본 기능
- [x] 회원가입, 로그인, 로그아웃
- [x] 이미지 업로드
- [x] 이미지 유화 변환
- [x] 게시글 작성, 수정, 삭제, 리스트
- [x] 댓글 작성, 수정, 삭제, 리스트
- [ ] aws ec3를 이용해 백엔드 프로젝트 배포

## 추가 기능
- [ ] 게시글 좋아요 기능
- [ ] 팔로우 기능
- [x] 마이 페이지 - 본인 게시물 보기
- [ ] 도메인 구매 및 연동하기
- [ ] 이미지 s3 관리하기
- [ ] https 적용하기
 
## 화면 설계
![회원가입](https://user-images.githubusercontent.com/96775737/204175039-251ad316-dc67-40e0-83ec-01269f6e49dd.png)
회원가입   

![메인페이지(게시글)](https://user-images.githubusercontent.com/96775737/204175149-609e89ef-4ce8-458d-92f5-277646067199.png)
메인페이지(게시글)

![게시글 상세](https://user-images.githubusercontent.com/96775737/204175184-1f5415a8-3f4e-48be-8919-4af2e2f61fe6.png)
게시글 상세

![마이페이지](https://user-images.githubusercontent.com/96775737/204175220-6b123dea-2cfe-4648-bf0e-a4e3a1d59664.png)
마이페이지

## DB 설계
![db 최종 PNG](https://user-images.githubusercontent.com/96775737/204175245-3dbcbf13-68b1-43b0-b101-e1622b6ec413.png)

## API 설계
<img width="774" alt="usersapi" src="https://user-images.githubusercontent.com/96775737/204175715-de7cb971-63d3-4299-badc-70a57b955482.png">
Users
<img width="484" alt="articlesapi" src="https://user-images.githubusercontent.com/96775737/204175745-fd41ad16-a05f-4174-9c32-1fcbb22d0ea6.png">
Articles

## 진행과정
# 첫번째, 유화시스템 / drf 백엔드 및 프론트엔드 기능

이번에도 S.A제작은 큰 무리가 없었다. 심지어 다름 팀들의 이전 S.A를 보고 이렇게 작성해야 하는구나를 알게되었다.(아직도 헷갈리는 점들이 있지만 이전보다 공부가 되었다…) 딥러닝도 무난하게 구현할 것이라 생각해 일단 우리가 생각했던 알고리즘으로 코드를 짜놓고 이후 나머지 백엔드와 연동할 것으로 계획했다. 원격강의를 참고해서 구현했기 때문에 초반에는 큰 무리가 없었던 편이다. 물론 이번에 conda 사용을 위해 계정을 새로 파는 과정은….(먼산)

프론트엔드의 경우에는 전에 했던 프로젝트 보다 간단하게 제작하여 한결 수월하게 제작 할 수 있었다.  백엔드의 경우 아무래도 강의가 많아서 참고할 자료가 많았다 보니 3명이서 부분적으로 파트를 나눠, 빠르게 완성하였다.
기본적으로 구현해야 되는 기능들은 빠르게 완성시키고 추가적인 기능 구현을 시도 해보았다.

# 두번째, 유화시스템 연동
딥러닝 부분에서 생각보다 시간이 걸렸던 이유는… 파일로 media 폴더에 결과가 저장이 안되었기 때문이다… 이걸로 꽤 오래 시간을 소모했는데 오류원인이 생각보다 다소 허무해 짜증났다.(파일이름이 겹치지 않게 현재 시간을 파일이름으로 저장하려고 했는데 현재시간을 찍는 라이브러리가 문자열로 전환하면 오류가 발생하는 것 같다고 튜터님이…)
그리고 사용자가 이미지를 업로드한 것을 opencv로 여는 것이 어려워 결국 모델을 변경해 진행했다.
유화 제작 코드를 Vscode에 연동하기 위해 conda를 설치하여 그림을 유화로 변경하는 기능을 완성했다.

# 세번째,  drf 백엔드와 프론트 기능 연동
프론트엔드와 백엔드 기능을 연동하지 못해 시간관계상 몇가지 기능들을 추가하지 못했다.(북마크 기능과 프로필 수정 기능은 백엔드를 완성하고 postman으로 정상 작동을 확인했지만 프론트적으로 동작하지 못했다…) 그래도 이전보다는 구현 시간이 빨라진 것을 느낄 수 있었다. 이해가 부족한 부분들은 프로젝트가 끝나고 코드 리뷰를 하기로 했다.

# 네번째, 마지막 전체 연동 및 구현 테스트 / docker 연결
백엔드, 프론트엔드 서버를 동시에 열어서 오류 없이 잘 연동되는 것을 확인했다.  이후 
docker로 배포를 시도해 보려 했지만, AWS 인스턴스의 메모리 부족으로 requirements.txt를 install하다가 막히는 오류가 발생하였다. 

## 시연 영상
<https://www.youtube.com/watch?v=UzneqBcOHOY>

## Good & Weak

# 😀Good

- 팀원 간 활발한 소통
- 오류 다같이 고민하기
- 기능 우선순위 정하기
- 장고 기능 다같이 구현하기
- .env를 통해 settings에서 secret key 처리를 통해 보안 유지
- GitHub 컨벤션 사용 commit push **(효정님 강의)**

# 😧Weak

- 백엔드와 프론트엔드 간 연동 소요시간
- 인스턴스 메모리 부족으로 인한 서버 배포 실패
- 코드 리팩토링(시간 부족)
- 파일, 함수 등 기능별 가독성 부족
- 팀원들이 다함께 모여 작업하는 시간 부족(일정이 안 맞았음)

# 🤔How to

- GitHub 이슈 기능 활용 및 트러블 이슈 정리 등 GitHub에 기록 열심히 남기기
- 변수명, 필드명, URL 처음 계획 무조건 지키기(변하면 알려주기)
- 파일 구조화
- 기본적 프론트 구현 및 연동 숙지하기
- 코드 리뷰를 통해 JS 코드 이해도 함양
- AWS 크레딧 발급을 활용한 서버 배포하기
- 건강관리 잘하기(아프지 말자)🤒💊😷

## 느낀점
* 정태희  
*초반에 프론트엔드 구성하는데 많은 집중을 하며 프로젝트를 시작했다. 하지만 정작 백엔드 부분 연동에 있어서 아직도 많이 부족하다 느꼈다. 
소셜로그인, 게시물 좋아요, 전체게시판 등등 머리속으로 생각하고 구현해보고 싶은 것은 많았지만 하지 못했다. 시간이 부족한 것도 있지만 솔직히 핑계이고 그냥 못 한 거다. 그리고 백엔드 부분을 계속 전에 했던 프로젝트에서 똑같이, 새로운 기능 없이 가져와서 사용 하는게 너무 아쉬운 부분 이였다..  프로젝트 발표가 끝이 나면 마지막 프로젝트를 위해 이번 프로젝트의 코드리뷰를 상세히 해야겠다.*

* 정유준  
*체력적인 부분에 대한 관리가 매우 중요함을 느꼈다. 안 그래도 짧은 프로젝트 기간 중에 컨디션이 좋지 않아지니, 회복하는 시간이랑 겹쳐서 제대로 할 일을 못 마쳐 아쉬웠다. 배려해준 팀원들에게 감사함을 느낀다. 다음 최종 프로젝트 때에는 조금 더 기초를 탄탄히 하고 긴 프로젝트 기간 동안 체력 관리도 잘해서 유종의 미를 잘 거두고 싶다.*

* 송창주  
*저번 프로젝트와 동일하게 프론트엔드와 백엔드의 연동이 매우 어려웠다. 영상 이외의 코드를 작성하는 사고력이 많이 부족했다. 팀원의 도움으로 js 기능들을 추가했고 코드에 대해 세세히 설명해주셨지만 전부를 이해하긴 어려웠다. 완성된 js 코드를 보면서도 내가 보고있는 페이지가 어떻게 구현된것인지 헷갈렸다. 프로젝트가 종료된 후 팀원들끼리 코드 리뷰를 통해 다시 한번 js에 대해 숙달하는 시간을 가질 예정이며, 인스턴스 메모리 문제로 서버 배포하지 못한 것을 해결하여 마지막 프로젝트때는 완성도 있는 프로젝트로 마무리하기 위해 노력할 예정이다.*

* 이승연  
*배포에 성공하지 못한게 많이 아쉬웠다. 기본적으로 스스로가 배포에 대한 공부도 부족했고, aws 크레딧을 미리 받아놓지 않아 더이상의 진행이 불가했다. 프론트엔드와 백엔드 서버 배포에 대한 전체적인 흐름이 그려지지 않아 공부가 많이 필요함을 느꼈다. 전체적인 프로젝트 완성도는 만족스러웠다. 중간중간 내가 부족했던 개념들도 확인할 수 있었고(예를 들면 역참조의 개념을 알고 있었지만 그게 시리얼라이저에서 어떻게 사용되어야 하는지 같은…), 팀원들간 시간을 조율해 함께 완성한 점이 좋았다.*

* 이효정
*백엔드와 딥러닝 기능 구현이 수월하게 진행되어서 지난 프로젝트보다 프론트 연동할 수 있는 시간적 여유가 있었음에도 전체적으로 js 이해도가 부족해서 소셜로그인, 북마크 등 프론트에 연동하지 못한 기능들이 조금 아쉽다. 프로젝트 발표 후 팀원들과 코드 리뷰를 통해서 이해 되지 않은 부분들은 꼭 이해하고 최종 프로젝트를 시작해야겠다. 
배포는 인스턴스 메모리 문제로 성공하지 못했지만 팀원들이 도커를 통해 배포하는 절차를 다시 한번 공부할 수 있는 기회였다고 생각한다. 프로젝트 계획 수립 단계에서 팀원들끼리 정했던 약속들도 잘 지켜졌고, 서로 배려하면서 진행했던점이 좋았다.*