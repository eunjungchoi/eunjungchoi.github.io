---
title: "mysql workbench 너무 재밌네"
date: 2020-10-24 08:54:28 -0400
categories: 
---

Django ORM과 postgresql만 몇년 썼는데 
간만에 mysql workbench 로 sql 쿼리 날려서 데이터 뽑아보고 있자니 너무 재밌다. 


북클럽 출석데이터를 내가 관리 중이다.  `팀 대항전 우승팀과 팀 출석왕을 찾아라.`

```
select slack_id, nick, display_name, count(*) as count
from archives
left join members
using (slack_id)
where month_index = 10 and day_index <= 23 and same_date = 'N' 
group by slack_id
order by count desc
```


팀은 매달 랜덤으로 바뀌기 때문에 db에는 저장해놓지 않고 
db에서 개인별/월별 출석 데이터를 계산해서 가져온 후 
엑셀에서 팀을 배합해 계산한다.

COUNTIF와 SUMIF 활용하면 간단. 

그런데 장기적으로는 팀을 저장하는 게 편하긴 할 듯 하다.

이 db가 다른 분이 만들어서 내게 공유를 해준 것이라, 내가 schema에 변화를 가하기는 조금 어렵겠다. 

그래도 지금 주어진 것만으로도 이것저것 활용해볼 수 있을 것 같다.  