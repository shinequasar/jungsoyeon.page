---
title: '[Crawler] 유튜브 댓글 및 감정분석 프로그램 개발'
description: D-day 크롬 확장프로그램 개발
image: '/csv/1.png'
date: 2021-12-05
---

# 프로젝트요약
유튜브 댓글분석 프로그램 개발 (AI감정분석, CSV, 워드클라우드, 형태소분석)


## 프로젝트 기간
- 2021년 12월 1일 - 3일
- 2022년 6월 업데이트


## 프로젝트 소개
1. 유튜브 **링크 하나**만 입력하면
2. 해당 유튜브의 **댓글들을 모조리 받아온 후** 댓글 내용을 **AI 감정분석**해 받아오고
     (원한다면 대댓글까지)
3. 댓글 및 각종 작성정보들과 감정분석 결과를 정제하여 **CSV 형태**로 저장
4. 해당 댓글들에서 많이 사용된 단어들을 형태소 분석하여 **빈도별 댓글 워드클라우드 생성**

## 제작동기

- 휴학 기간 중 지내던 창업기숙사에서 만난 **문과 룸메이트가** 시장조사를 할때에 유튜브 댓글반응을 **손으로 하나하나 긁어와서** 엑셀로 정리하는 것을 보고 도와주면 좋겠다라는 생각이 들어 해당 크롤링 프로그램을 제작하게되었습니다.
- 개발에 대한 지식이 없는 친구를 위한 개발이었기에, **GUI 프로그램**을 이용해 개발에 대한 지식이 없어도 해당 유튜브 URL을 입력하기만 하면 작동할 수 있게끔 만들었습니다.

## 프로젝트 깃헙주소
[- https://github.com/shinequasar/gui-crawler.git](https://github.com/shinequasar/gui-crawler.git)

## 개발일지
[https://blog.naver.com/shinequasar/222767662416](https://blog.naver.com/shinequasar/222767662416)

<br>
<hr><br>

# **gui-crawler**

## 기능

- 유튜브 댓글 크롤링
- 엑셀시트 분리
- 의뢰인 명으로 파일이름 자동생성
- 댓글 워드클라우드 기능
- 원하는 이미지 삽입시 해당 이미지모양대로 워드클라우드 모양 설정가능
- 댓글 내용 AI 감정분석 후 (부정/긍정/중립) 으로 분석

## **GUI**

![크롤링](/assets\images\projects\csv\1.png)

## **wordCloud - 워드클라우드(모양변경가능)**

- html 관련 키워드 정제 (불용어로 지정)
![크롤링](/assets\images\projects\csv\11.png)


=> 디폴트 모양형태
![크롤링](/assets\images\projects\csv\222.png)

=> 파이리 모양으로 만든버전
![크롤링](/assets\images\projects\csv\333.png)


<br>
<hr><br>

## CSV

### - ‘의뢰내용’시트
- 댓글작성자 / 작성날짜 / 좋아요 수 / 댓글 / 감정분석결과 /  작성자채널 URL 등의 정보를 수집
- 댓글 감정분석은 (positive / neutral / negative) 로 분석됨.

![크롤링](/assets\images\projects\csv\444.png)

### - ‘분석표’ 시트
![크롤링](/assets\images\projects\csv\4.png)