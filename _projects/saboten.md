---
title: '[Backend] 선인장 프로젝트'
description: 선인장(선택장애 인간들을 위한 장) 이라는 소재로 만든 SNS 커뮤니티 앱서비스.
image: '/saboten/Saboten_ERD.png'
date: 2022-05-22
---

## 프로젝트 요약

선인장(선택장애 인간들을 위한 장) 이라는 소재로 만든 **SNS 커뮤니티 앱서비스**.

<br>
<hr><br>

### 프로젝트 기간

**2022년 1월 ~ 현재 (진행중)**


### 소개

최근 유행이었던 일명 '밸런스게임' 과 같은 형태로 **두개의 선택지**가 주어지면 해당 주제에 대해 **투표를 하고, 댓글**을 통해 토론하는 장을 만들고, **투표한 사람들의 연령, 성별, 투표율 등의 통계**를 볼 수 있는 앱서비스입니다. 

<br>
<hr><br>


### 프로젝트 깃허브주소

[https://github.com/GDSC-Daejin/project-saboten.git](https://github.com/GDSC-Daejin/project-saboten.git)

<br>
<hr><br>

### 1) Server 기술스택 및 사용 툴

- **형상관리 및 문서화**
    - Github
    - Notion, ERDCloud, Swagger 3.0
    - JIRA, Slack
    - Sentry&Logback
- **사용 프레임워크 및 라이브러리**
    - JAVA , SpringBoot, JPA, QueryDSL, JUnit5, Mockito
    - PostgreSQL
- **CI/CD**
    - Github-Action, GCP
    

    <br>
<hr><br>

### 2) 팀원구성 및 일정관리

- **총 6명 (안드로이드 팀원 2명, 백엔드 팀원 2명, 디자이너 팀원 2명)**의 팀원들과 함께 협업으로 개발 진행 중이며, 올해 8-9월 출시예정으로 개발하고 있습니다.
- 현재 팀 내에서 **백엔드를 담당**하고 있으며, **서버 구축, API 개발 및 배포, 문서화를 담당**하고 있습니다.
- 1-2주 간격으로 회의를 통해 Jira에 새로운 스프린트 목표와 백로그를 작성하고, 난이도/소요시간을 기준으로 storyPoint를 매겨 팀원들간 일의 분배와 목표치를 최대한 수치화하여 관리하고있습니다.
- 매 회의는 Notion에 회의록으로 기록되며, 스프린트 종료시마다 회고 회의를 반드시 하여 팀원과 파트별로 어떤 이슈가 발생하였고, 해결방안에 대해 함께 고민하는 시간을 가지고 있습니다.

<br>
<hr><br>

### 3) 프로젝트 진행시 경험했던 이슈

**1) 계층형 프로젝트 구조의 한계**

- 문제 : 프로젝트 구조가 처음엔 계층적으로 Controller / Service / Model 등 레이어별로 나뉘어져 있었는데 조금씩 프로젝트 규모가 커지고, 도메인별로 응집도가 높아지는 것을 현재 프로젝트 구조가 방해하고 있다는 생각이 들었습니다. 같은 도메인, 역할을 수행하고 있는데 패키지가 중구난방으로 흩어져 있어 생산성이 조금 떨어지고 있었습니다.
- 해결방안 이러한 문제에 대해 다른 분들은 어떻게 대처를 하시고 계신지 궁금해 찾아보니 DDD(Domain Driven Design) 이라는 방식이 매우 인상깊었습니다. 조만간 현재 개발 중이던 스프린트들만 마무리 되면 도메인 형 구조로 변경할 예정입니다.
- 프로덕트 구조를 고민하면서 알게된, 최근 여러 기업들에서 모놀리틱 구조에서 MSA(Micro Service Architecture) 형태의 프로덕트 구조로 변화하는 모습들이 인상깊어 만약 큰 비즈니스 프로젝트로의 확장 시, 도메인별 분리가 중요할 수 있음을 알 수 있었습니다.

**2) ERD 설계 및 구현단계에서의 정규화**

- 테이블 설계를 하며 초기에 중복된 어트리뷰트의 테이블들이 많이 생겨 정규화에 대한 필요성을 느꼈습니다. 때문에 최대한 1,2.3 정규화를 해보기 위해 고민을 하였습니다.
- 추후 객체를 생성해 쿼리를 날릴때 발생한 에러로 테이블 매핑시에도 즉시로딩과 지연로딩(Lazy/Eager) 에 대한 고민을 할 수 있었습니다.

3**) 레이어단 역할 분배 고민**

- 같은 레이어에서 동일 레이어단을 호출한다면 순환 참조오류가 일어날 수 있기에 만약 동일 레이어단이 여러개 필요한 경우라면 Controller > Service > Repository 처럼 상위 레이어에 주입한 후 비즈니스 로직을 작성하기로 팀원 간 협의하였습니다.

4**) Access Token, Refresh Token 만료 보안이슈**

- 팀원과 함께 상의 후 Redis 캐시 도입

5**) 복합키 GeneateValue 이슈**

- 대표ID로 변경

<br>
<hr><br>


### 선인장 프로젝트 서버 ERD


![선인장 ERD](/assets/images/projects/saboten/Saboten_ERD.png)

<br>
<hr><br>

### 와이어프레임

![와이어프레임](/assets\images\projects\saboten\wire.png)

![와이어프레임2](/assets\images\projects\saboten\wire2.png)

<br>
<hr><br>

### 선인장 형상관리

- 브랜치 번호는 jira의 백로그 티켓번호입니다.
- **Git Rules**

**Branch Create**

- 브랜치 생성시 "feature/{포지션 : BE, FE, AND, IOS}/SBOT-{백로그번호}-{비고(Optional)}" 로 생성합니다.
    - 예 : "feature/BE/SBOT-120-user-api"

![깃헙](/assets\images\projects\saboten\git.png)

<br>
<hr><br>

### 선인장 PR 방식

- pr 공통양식을 만들어 관리합니다.
- 다양한 태그들을 통해 급한PR, 개발중인 PR, 새로운기능/문서화 등 PR상태의 식별에 용이하도록 하였습니다.

![깃헙2](/assets\images\projects\saboten\github.png)

<br>
<hr><br>


## 선인장 클라이언트/서버 전체 아키텍쳐

## **Table of Contents**

- [Architectures](https://github.com/GDSC-Daejin/project-saboten#1)
    - [Project Architecture Overall](https://github.com/GDSC-Daejin/project-saboten#1-1)
    - [Common Client Side Architecture Overall](https://github.com/GDSC-Daejin/project-saboten#1-2)
- [Git Rules](https://github.com/GDSC-Daejin/project-saboten#2)
