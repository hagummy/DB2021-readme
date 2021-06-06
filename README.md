 DB2021-readme

# 목차
* 프로그램 설명
* 프로그램 사용 방법
   * 관리자모드
   * 사용자모드
  

# 프로그램 설명

이화데벡과(8조)가 만든 프로그램은 사용자가 원하는 영화, 배우, 감독에 대한 정보를 쉽게 검색할 수 있는 프로그램이다. 관리자는 새로운 정보를 삽입하거나, 기존에 있던 정보를 삭제 및 업데이트할 때 불편함 없이 입력할 수 있도록 구현하였다.

사용한 테이블은 총 7개이다.

DB2021_MOVIES | DB2021_ACTORS | DB2021_ACTOR_HAS | DB2021_DIRECTOR | DB2021_GENRES | DB2021_GENRE_HAS
------------- | --------------|------------------| ----------------| --------------| ----------------
movieNumber | actorNumber | actorNumber | name | genreNumber | genreNumber
title | name | movieNumber | gender | genre | movieNumber
director | gender | | nationality | |
releaseDate | nationality | | birthday | |
country | birthday | | filmography | |
runningTime | | | | |
score | | | | |
attendance | | | | |

DB2021_ACTOR_HAS와  DB2021_GENRE_HAS을 사용하여 정보의 이상현상들이 나타나지 않게끔 구현하였다.

# 프로그램 사용 방법
모드선택창이 뜨면 관리자모드로 사용할 건지, 사용자모드로 사용할 건지 선택한다.

     관리자모드 선택시 1, 사용자모드 선택시 2를 입력한다.
     
## **관리자모드**

관리자모드에는 정보 추가, 정보 삭제, 내용 갱신, 전체 검색, 세부 검색 총 5개의 카테고리가 있다.

### 1. 정보추가 

정보추가에는 __배우,감독,국가,영화__ 가 가능하다. 

  (1)  __배우추가__ 에는 actorNumber, 배우 이름, 성별, 배우의 국적, 생년월일를 차례로 입력해준다.
  
    예시)  ActorNumber : A531
  
           이름:박수아

           성별(M/F) : F

           국적 : 한국

           생년월일 (ex)YYYY-MM-DD : 1999-04-05


  (2)  __감독추가__ 에는 이름, 성별, 국적, 생년월일, 필모그래피를 차례로 입력해준다. 
  
    예시) 감독 이름 :김재환
  
          성별(M/F) :M

          국적 :한국

          생년월일 (ex)YYYY-MM-DD :1996-05-27

          필모그래피 :3


  (3)  __국가추가__ 에는 국가, 대륙을 차례로 입력해준다.
  
    예시) 국가명 :터키
  
          continent :서아시아


  (4)  __영화추가__ 에는 movieNumber, 제목, 감독, 평점, 국가, 러닝 타임, 개봉 날짜, 관객수, 출연 배우, 장르를 차례로 입력해준다.

   출연 배우와 장르는 모두 입력이 끝나면 '0'을 입력한다.
   
    예시) 영화 시리얼 번호 ex) M000 : M222
   
          영화 제목 : 터키에 대하여
        
          감독 : 김재환
        
          평점 : 6.0

          국가 : 터키
        
          러닝 타임 : 123
        
          개봉 날짜 : 2021-06-02
        
          관객 수 : 1886
        
          이름 :  박수아
        
          이름 :  하정우
        
          이름 :  0
        
          장르 :  액션
        
          장르 :  스릴러
        
          장르 :  0

   
  _형식이 필요한 입력값은 옆에 예시로 써있기때문에 그 형식에 맞춰서 입력하면 된다._
  
### 2. 정보삭제 

정보삭제에는 __영화,배우,감독__ 이 가능하다. 

(1) __영화삭제__ 에는 시리얼 번호로 삭제, 제목으로 삭제가 있다.
 
   시리얼 번호는 movieNumber이다.
   
   movieNumber를 모른다면 세부검색에서 찾아볼 수 있다. 
    
    예시) 영화 제목 : 바람
         '바람'이(가) 포함된 영화 목록
         [Number : M017]
         제목:Gone With The Wind (바람과 함께 사라지다)
         감독:빅터 플레밍 개봉일:1957-03-25 국가:미국 러닝타임:230(분) 평점:9.22 관객수:26000명
         영화 시리얼 번호 : M017


   
   __제목은 풀네임을 입력해야만 삭제가 된다. __

(2) __배우삭제__ 에는 시리얼 번호로 삭제, 제목으로 삭제가 있다.

   시리얼 번호는 actorNumber이다.
   
   actorNumber를 모른다면 세부검색에서 찾아볼 수 있다. 
   
   __제목은 풀네임을 입력해야만 삭제가 된다. __
   
    예시) 배우 이름 : 박수아

(3) __감독삭제__ 는 이름을 통해서만 가능하다.
   
  _형식이 필요한 입력값은 옆에 예시로 써있기때문에 그 형식에 맞춰서 입력하면 된다._
  
### 3. 내용갱신

내용갱신에는 __영화 평점,영화 관객 수,감독 작품 수, 영화 출연 배우 추가__ 가 가능하다. 

(1) __영화 평점__ 은 시리얼 번호를 알아야만 가능하다.
 
   시리얼 번호는 movieNumber이다.
   
   movieNumber를 모른다면 세부검색에서 찾아볼 수 있다. 
    
   __제목은 풀네임을 입력해야만 삭제가 된다.__

(2) __영화 관객 수__ 는 시리얼 번호를 알아야만 가능하다.

   시리얼 번호는 actorNumber이다.
   
   movieNumber를 모른다면 세부검색에서 찾아볼 수 있다. 
   
   __제목은 풀네임을 입력해야만 삭제가 된다. __

(3) __감독 작품 수__ 는 이름을 통해서만 가능하다.

(4)__영화 출연 배우 추가__ 는 영화 시리얼 번호, 배우 시리얼 번호를 알아야만 가능하다.

   영화 시리얼 번호는 movieNumber이다.
   
   배우 시리얼 번호는 actorNumber이다.
   
   movieNumber, actorNumber를 모른다면 세부검색에서 찾아볼 수 있다. 
   
  _형식이 필요한 입력값은 옆에 예시로 써있기때문에 그 형식에 맞춰서 입력하면 된다._
  
### 4. 전체 검색

전체 검색에는 __영화,배우,감독,국가, 장르__ 가 가능하다. 

위의 카테고리 중 원하는 정보에 대한 숫자를 입력하면 DB가 가지고 있는 전체 데이터와 개수를 출력한다. 

_전체 정보를 알고 싶을 때 유용하게 사용된다._

### 5. 세부 검색

전체 검색에는 __영화,배우,감독, 장르__ 가 가능하다. 

세부 검색은 전체 단어를 입력하는 것이 아닌 일부만 입력해도 해당하는 모든 데이터들의 정보가 출력된다.

_특히, 배우와 감독은 국적별로도 검색이 가능하다._

# 사용자모드

사용자 모드에는 __영화 검색,배우 검색,감독 검색, 장르 검색__ 이 가능하다.

__영화, 배우, 감독__의 경우 사용자가 제목 또는 이름의 일부만 검색해도 정보가 나온다.

장르검색은 입력한 장르에 대한 모든 데이터가 추출된다. 


  






