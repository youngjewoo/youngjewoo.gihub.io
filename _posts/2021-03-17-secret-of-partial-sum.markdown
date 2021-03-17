---
layout: post
title:  "[알고리즘] Secret of Partial Sum"
date:   2021-03-17 02:48:54 +0900
categories: jekyll update
---

안녕하세요 오늘은 부분합을 빠르게 구하는 방법을 알아보겠습니다.

해당 글을 포스팅하게 된 계기는 leetcode를 풀다 보면 부분합을 구하라는 문제를 종종

만날 수 있는데, 그 때 유용하게 사용할 수 있는 방법 하나를 소개해드리려고 합니다.

처음에는 와 이게 되네~ 였다가

다음부터 부분합이라는 단어만 보면 이 방법부터 떠오르더라고여.. 

역시 코딩은 지식도 필요하지만 연습을 통해 숙달 되는 기술이기도 한 거 같습니다.

자 이제 바로 본론으로 들어가겠습니다.

인덱스 i 부터 k 까지의 부터의 부분합을 구한다고 가정하겠습니다.

부분합 구하기
![Untitled](https://user-images.githubusercontent.com/22024761/111404599-6181f500-8712-11eb-80e7-c2ec4ba95df8.png)

## 1. Brute force

첫 번째는 있는 그대로 생각하는 겁니다.

맞습니다. 바로 순차적으로 더한 다음 리턴하는 것이죠

![Untitled (1)](https://user-images.githubusercontent.com/22024761/111404600-62b32200-8712-11eb-82ae-06107510d8f7.png)

인덱스 1,2,3을 차례로 순회하면서 2,3,4값을 가져와서 9라는 값을 리턴하는 겁니다!

참 쉽네요. 

하지만 문제가 i부터 k까지가 아니라 배열의 모든 SubArray의 합을 구하라! 라면 어떨까요?

![Untitled (2)](https://user-images.githubusercontent.com/22024761/111404601-634bb880-8712-11eb-91ef-5f21a1828c64.png)
![Untitled (3)](https://user-images.githubusercontent.com/22024761/111404605-634bb880-8712-11eb-97ce-325245c23c13.png)

이런식으로 계속 합을 구할 때마다 계속 순회를 하게되면 시간 복잡도는 O(n^2) 이 되어버리고 맙니다..

시간 복잡도 : O(n^2) 

공간 복잡도 : O(1)

그러면 이 문제를 해결하기 위해서는 어떤 방법이 있을 까요?

## 2. Pre-sum

말 그대로 미리 합을 구해놓고 활용하는 방법이 있습니다.

미리 구해놓은 합 구해서 어디다가 사용하냐구요?

단순화해서 막대기 두 개가 있다고 가정하겠습니다.

![Untitled (4)](https://user-images.githubusercontent.com/22024761/111404606-63e44f00-8712-11eb-9e7e-d2c7f073bfa8.png)

여기서 w의 길이를 구하고 싶다고 하겠습니다. 어떻게 하면 될까요?

막대1 길이 - 막대2 길이 를 하면 구할 수 있지 않을까요?

배열의 부분합도 똑같습니다.

![Untitled (5)](https://user-images.githubusercontent.com/22024761/111404608-63e44f00-8712-11eb-9cf5-d347dd3db1a7.png)

인덱스 6~10까지의 합을 구하고 싶다면 10까지의 합에서 6까지의 합을 빼는 방식으로 구할 수 있는 것이죠

이렇게 미리 합을 한 번만 계산해놓으면 이후에 합을 구할 때는 순회 없이 O(1) 에 바로 구할 수 있는 것이죠.

배열의 값에 대한 접근 시간은 O(1)이니까 A[i] - A[k] 두 번 접근하는 것 쯤 O(n^2)에 비하면

감지덕지 입니다.

앞으로 부분합등의 단어가 나오면 해당 방법으로 최적화할 수 있다는 것을 꼭 기억해두세요!

연습할 수 있는 문제 몇 개 첨부합니다!

- Running Sum

[Running Sum of 1d Array - LeetCode](https://leetcode.com/problems/running-sum-of-1d-array/)

- Maximum Subarray

[Maximum Subarray - LeetCode](https://leetcode.com/problems/maximum-subarray/)

- Subarray sum equals k

[Subarray Sum Equals K - LeetCode](https://leetcode.com/problems/subarray-sum-equals-k/)

