---
layout: post
title: "서버에서 사용자 데이터 삭제하기"
description: ""
category: study
tags: [rails]
---
{% include JB/setup %}

#### 서버에서 일정시각 기준으로 사용자 정보 삭제하기

1. SELECT 기준 시점을 한국 시간으로 변환
    - dateTime = DateTime.parse("2014-07-01 00:00:00 +0900")

2. 사용자 SELECT
    - u = User.where(["created_at < ?_" , dateTime])

3. 개수 확인
    - u.size

4. 맨 처음 등록된 관리자는 제외하고 배열에 담기
    - u.size의 결과값이 21개 일때 0번부터이므로, 0번 관리자 제외하고 1번부터 마지막까지 
    - deleteUser = u[1..21]

5. 배열 요소 각각 삭제
    - activerecord 이면 du.destroy_all 로 삭제 가능하지만 array 이므로 배열 요소 하나씩 지우기
    - du.each{|u|u.destroy}