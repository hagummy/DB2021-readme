 DB2021-readme

# 목차
* 프로그램 설명
* 프로그램 사용 방법

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

DB2021_ACTOR_HAS와  DB2021_GENRE_HAS을 사용하여 정보의 이상현상들이 나타나지않게끔 구현하였다.

# 프로그램 사용 방법







