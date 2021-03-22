---
layout: post
title:  "[Jekyll] 포스팅 이슈 해결"
date:   2021-03-17 02:48:54 +0900
categories: jekyll update
---

안녕하세요 오늘은 GitHub 페이지를 Jekyll로 구성하면서 발생했던 오류에 대해 정리해보려고 합니다.

문제 상황은 이렇습니다.

저는 Jekyll을 이용해서 markdown으로 포스트를 작성했고,

신나게 업로드를 했는데 다음과 같이 특정 라인 이후로 글자가 깨져서 나오는 현상이 있었습니다.

<br>
<br>
- 오류가 발생한 포스팅 (특정 라인 이후로 스타일이 깨져서 적용됨)
![Untitled](https://user-images.githubusercontent.com/22024761/111405344-a6f2f200-8713-11eb-822c-eb92af40858d.png)

Cheese crust.

"<문제의 메모리 사용량>" 이후의 글자들이 모두 깨져서 보입니다.

정말 왜 이러는 걸까요?

<br>
저는 제가 이미지 추가하는 방법이 잘못됐나 생각해서 여기저기 뒤지고 다녔는데,

의외로 원인은 매우 간단했습니다.
이미지 한 장으로 요약합니다.

<br>
- Jekyll로 실행시킨 깃헙 페이지

![Untitled (1)](https://user-images.githubusercontent.com/22024761/111405347-a78b8880-8713-11eb-95a2-5787be4939ff.png)


<br>
<br>

아까 이미지를 다시 보겠습니다.

<br>
<br>
- 오류가 발생한 포스팅
![Untitled (2)](https://user-images.githubusercontent.com/22024761/111405349-a8241f00-8713-11eb-852e-c817bde296da.png)

<br>
<br>
감이 오셨나요?

<br>
<br>
그렇습니다. 너무 당연하게도 우리가 markdown으로 작성한 파일들은 **html 파일** 형태로 업로드됩니다.

그리고 오류가 발생한 포스팅에서 보면 제가 이미지의 제목으로 '<','>'을 사용한 것이 보이시나요?


<br>
<br>

**저 이미지 제목을 html tag로 인식하여 발생한 에러였습니다.**


<br>
<br>

태그를 열었는데, 닫는 태그가 없으니 당연히 밑에 내용들을 정상적으로 읽을 수 없었던 겁니다..

고로 깃헙 페이지를 markdown 혹은 깃헙페이지 작성 시 '<','>' 사용에 유의하세요! 

<br>
<br>
라고 마치고 싶지만 이미 저는 궁금증이 생겨버렸습니다...
<br>
<br>
<br>
### 의문점 3 가지

***1. Markdown 파일에 직접 html 태그를 입력하는 것이 가능한가?***

***2. 문제의 포스팅에서 태그를 닫아주면 문제가 해결될 것인가?***

***3. 그 위에 "문제의 run-time 1등 코드" 밑에 내용은 왜 정상 출력 됐는가?***

<br>
<br>
<br>

### 실험 1 : Markdown에 직업 html 태그 입력이 가능한가? ( O )

- 테스팅 데이터

![Untitled (3)](https://user-images.githubusercontent.com/22024761/111405351-a8241f00-8713-11eb-92cb-f4f5d892b021.png)

마크 다운 파일에 html 태그를 직접 입력해봤습니다.

Syntax highlight까지 되는 걸 보니 뭔가 될 거 같군요 ㅋ

<br>
<br>
<br>
- 결과

![Untitled (4)](https://user-images.githubusercontent.com/22024761/111405353-a8bcb580-8713-11eb-9aca-c16ecc8d05b2.png)

<br>
<br>
결과는 **성공**입니다!

멋지게 스타일이 입혀진 결과물을 내뱉어줬네요. 종종 사용해볼 수 있겠습니다. ㅋ

<br>
<br>
<br>
### 실험 2 : 태그를 닫아주면 문제가 해결되는가? ( O )

- 테스트 코드

![Untitled (5)](https://user-images.githubusercontent.com/22024761/111405356-a9554c00-8713-11eb-981d-b04556a2a600.png)

<br>
- 닫아주지 않을 경우

![Untitled (6)](https://user-images.githubusercontent.com/22024761/111405358-a9554c00-8713-11eb-955f-6392bb43b732.png)

<br>
<br>
신기하게도 직접 입력한 html 태그는 문제가 있더라도 정상 출력됩니다.

<br>
<br>
하지만 빨간줄로 표시된 마크다운 문법은 아쉽게도 살아남지 못했네요..

<br>
- Full-name으로 닫아주는 경우

![Untitled (7)](https://user-images.githubusercontent.com/22024761/111405360-a9ede280-8713-11eb-999c-ccf04b236d14.png)

괄호를 닫아주더라도 역시 마크다운이 정상적으로 인식되지 않는 군요..

혹시 메모리, 사용량을 attribute로 인식한 것 같아 

'문제의' 태그 이름으로 닫아보았습니다.

<br>
<br>
- '문제의' 태그로 닫아주는 경우

![Untitled (8)](https://user-images.githubusercontent.com/22024761/111405361-a9ede280-8713-11eb-9125-b6bc6fea1ecd.png)

<br>
<br>
..? 됐습니다.

<br>
<br>
- 마크다운이 정상적으로 출력된 이유 (feat. Chrome 개발자 도구)

![Untitled (9)](https://user-images.githubusercontent.com/22024761/111405363-aa867900-8713-11eb-90a6-a4d46d2a4f46.png)

<br>
물론 정상 tag로 처리된 거는 아니고 text로 인식하고 마지막 닫는 태그는 지워버렸네요...

만약 닫는 태그 사이에 마크 다운으로 입력된 내용이 있다면 

그 내용에는 마크 다운 형식이 유지되지 않습니다.


<br>
<br>
<br>
### 실험 3 : "<문제의 run-time 1등 코드>" 이후 데이터는 왜 정상 출력 되는가?

동작했던 태그를 입력하고 그 밑에 내용들을 채워넣어 봤습니다.

<br>
- 테스트 코드

![Untitled (10)](https://user-images.githubusercontent.com/22024761/111405364-aa867900-8713-11eb-8b03-88ea21e18e8c.png)

<br>
<br>
- 결과

![Untitled (11)](https://user-images.githubusercontent.com/22024761/111405365-ab1f0f80-8713-11eb-95f4-5d233e9fc1b1.png)

<br>
<br>
또 되네요 ;;  🥴

<br>
<br>
"문제의 메모리 사용량"과 도대체 무슨 차이일까요??

<br>
여러 가지 실험을 통해 알아낸 결과,

> **attribute 이름이나 tag 이름에 숫자가 들어가면 내부적으로 태그가 아닌 것으로 처리하는 로직이 있습니다.**

<br>
<br>
- 숫자 태그의 처리 (Chrome 개발자 도구)

![Untitled (12)](https://user-images.githubusercontent.com/22024761/111405368-ab1f0f80-8713-11eb-900d-3f7353ace7ca.png)

텍스트로 인식하여 '<p>' 태그로 처리하였다.

결국 1등이라는 숫자 덕에 위 태그는 정상적으로 처리,

밑에는 숫자가 없었기 때문에 태그로 처리하려다가 스타일이 모두 깨지는 현상을 겪었습니다.


포스팅 하시는 분들은 예외적인 상황을 만나고 싶지 않으시다면

**'>' 문자는 사용하지 않는 것이 좋겠습니다!**

근데... 진짜 진짜 최종으로 진진최
행여 '<>' 이 문자가 너무너무너무 사용하고 싶으면 어떻게 해야할까요?

앞에 백슬래쉬(\\)를 붙여주면 됩니다!

"\\\<" 이런 식으로요 ㅋㅋ 

수식을 작성한다던가 꼭 필요한 곳에는 '\'를 활용하여 활용하시기를 바랍니다!

이제 정말 끝입니다!

모두 Jekyll markdown 작성 시 '<','>'에 주의하시길 바라며 행복한 GitHub 페이지 만드시길!

