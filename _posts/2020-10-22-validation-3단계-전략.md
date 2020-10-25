---
title: "Validation을 고려할 때는 3단계 전략을 취하자"
date: 2020-10-22 08:54:28 -0400
categories: 
---
 
데이터 유효성 검사를 할 때 주로 프론트엔드와 백엔드 API에서 값을 validation 해왔다. 들어온 값이  우리가 원하는 데이터의 형태와 맞는지 여부를 체크한 것.  

그런데 중요한 것 하나를 빠뜨리고 있었다. 바로 Database에 constraint를 추가하는 것이다. 

DB validation의 방식에는 여러가지가 있다. 

1. unique key 설정하기 
2. 컬럼 값 constraint 설정하기. ex) 값의 길이, type 등 
 


각설하면 
1. 프론트엔드에서 validate
2. 백엔드 애플리케이션 단에서 validate
3. database에 constraint (제약) 추가. 

세 번째를 잊지 말자 


<hr>

사실 하나 더 추가하고 싶다. 

#### 바로 type 이다 

파이썬의 경우 type 이 없어서 type에 대해 별 생각을 안 하고 살아왔는데, type 선언만으로 많은 값 문제들이 조기에 걸러질 수 있다. 
 
물론 에러를 일으키진 않는다. 

python 3.7부터 typing 모듈이 추가됐다. 웬만하면 type을 표기하도록 하자. 
