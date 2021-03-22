---
layout: post
title:  "[leetcode] Merge Intervals"
date:   2021-03-22 01:48:54 +0900
categories: jekyll update
---

안녕하세요 오늘은 간단한 문제에서 느낀점을 기록해보겠습니다.

- Merge Intervals

[Merge Intervals - LeetCode](https://leetcode.com/problems/merge-intervals/solution/)

해당 문제는 2차원 array가 주어집니다. interval의 배열이 주어지죠!

Ex) [[1,3],[4,5],[2,2]] - input

주어진 interval을 받아 겹치는 범위를 합쳐서 리턴하는 문제입니다.

Ex) [[1,3],[4,5]]        - output

간결하게 짜면 간결하지만 하나 아이디어를 삐끗하면 코드가 상당히 지저분해 지더군요...

바로 이 점이 포스팅의 이유입니다!

### 첫 번째 구현

![Untitled](https://user-images.githubusercontent.com/22024761/112020485-ba6ae680-8b73-11eb-8322-084accf2f133.png)

물론 여러 분들께 코드를 읽으라고 한 것은 아닙니다. 

좀 더 보기 좋은 그림으로 말씀 드리죠

1. **start 값 기준 정렬**

![Untitled (1)](https://user-images.githubusercontent.com/22024761/112020491-bb037d00-8b73-11eb-8215-c171425e09a3.png)

  **2. i 에서 i-1까지 누적된 조건을 확인하고 push!**

![Untitled (2)](https://user-images.githubusercontent.com/22024761/112020494-bb9c1380-8b73-11eb-8ca0-9e4dbde6669f.png)

  가장 작은 start값과 가장 큰 end값을 계속 기록하다가,

  maxEnd보다 i번째 원소의 start값이 커지는 순간이 오면 누적해왔던 값을 push 하는 형태입니다.

  시간 복잡도는 (n log n)이네요. 

  시간 복잡도도 나쁘지 않고, 모든 테스트 케이스를 통과할 수 있었습니다.

  그래서 저도 만족하고 넘어갔었죠.
<br>
<br>
<br>
  **하지만, 알고리즘 스터디를 하는데 동료들 코드보다 제 코드가 유난히 긴 겁니다...**

  Java나 C#은 하는 사람들은 그렇다 쳐도.. C++ 하는 분도 13라인에 끝내셨다길래

  이건 뭔가 문제가 있다고 생각하고 제 코드의 최적화 포인트를 찾아봤습니다.

  i 번째에서 i-1의 조건을 확인하는 방식은 맨 마지막 원소에 대한 고려를 항상 해줘야합니다.

  [ 발생한 엣지 케이스 ]

![Untitled (3)](https://user-images.githubusercontent.com/22024761/112020495-bb9c1380-8b73-11eb-98f4-f4ed22d0f765.png)

  ***맨 마지막 원소에 interval이 분리되거나 한다면 i+1이 없기 때문에***

  결과값에 추가해줄 수 가 없습니다. 

  따라서 불필요한 조건문이 들어가게 된 것이죠...

![Untitled (4)](https://user-images.githubusercontent.com/22024761/112020498-bc34aa00-8b73-11eb-9cc3-0db876ff73e5.png)

  물론 성능상의 이슈는 없습니다.

  그러나 가독성에 문제가 생기죠ㅋ 뒷 사람이 코드를 읽기가 싫어집니다...

  이해하기 난해하기도 하고요...

  그래서 방법을 살짝 바꿔봤습니다.

  일단 넣어놓고 나중에 업데이트 하는 방식으로요!

![Untitled (5)](https://user-images.githubusercontent.com/22024761/112020499-bc34aa00-8b73-11eb-8ff0-f9f829af2567.png)

  이래나 저래나 결과는 똑같지만..

  [ 로직을 바꾼 이후 코드 ] 

![Untitled (6)](https://user-images.githubusercontent.com/22024761/112020501-bccd4080-8b73-11eb-8955-88ea7adb8297.png)

  훨씬 코드도 짧아지고 조건문도 clear 해졌네요.

  예전처럼 잘하는 한 명이 프로그램 전체를 개발하는 시대가  아니라,

  여러 명이 함께 코드를 개발하는 이 시대엔  성능, 메모리상의 최적화도 물론 좋지만

  이런 식의 코드 정리도 개발자의 실력이 아닐까 생각합니다 ㅋ
<br>
<br>
  이 문제를 통해서는 다른 사람들과 풀이를 공유하며 더 좋은 코드에 대해

  다시 한 번 생각해볼 수 있는 기회가 됐습니다.

  여러 분들도 짧고 굵은 코딩 하시길 바랄게요!
