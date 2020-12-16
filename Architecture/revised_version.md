#### 요구사항


**1. 회원 기능**
* 회원 등록 (회원가입)
* 로그인
* 로그아웃


**2. 설문기능**
* 설문 생성
* 설문 전체 목록 조회
* 설문 조회 (자신이 생성한 것)
* 설문 조회 (자신이 투표한 것)
* 설문 실시
* 설문 삭제


**3. 기타 요구사항**
* 설문 생성은 객관식, 주관식 두가지 타입으로 가능

<br/>



#### 도메인 설계 (피드백 반영 1차 수정본)

![revised_classdiagram](https://user-images.githubusercontent.com/31160622/102334719-5a8ffd00-3fd2-11eb-8bd4-b1b5c0af51c8.png)

**수정사항**
* 관계를 나타내는 애가 불필요한 속성을 가지고 있다 -> 제거 및 수정
* boolean 타입으로 질문의 유형 결정할 경우 2가지로 제한적 -> 타입 변경(Enum)
* 기존 단방향으로 충분한 관계를 양방향으로 표현 -> 단방향으로 부분 변경
* 객관식에 대해서는 각 목록 별 count 속성을 두어 편하게 관리할 수 있도록 변경
* 대답의 경우 상속관계 불필요할 것으로 판단되어 제거

<br/>



### Database 설계

<br/>

#### E-R Diagram

![er](https://user-images.githubusercontent.com/31160622/102334220-c4f46d80-3fd1-11eb-8b25-775612282bb9.png)

<br/>



#### Database Scheam

: 해당 E-R Diagram을 바탕으로 구성한 데이터베이스 스키마

![schema](https://user-images.githubusercontent.com/31160622/102334192-bc9c3280-3fd1-11eb-80e3-ee826f684cdf.png)
