---
layout: post
title:  "[알고리즘] Tree-traversing"
date:   2021-03-18 02:48:54 +0900
categories: jekyll update
---

안녕하세요! 오늘은 Tree 자료구조의 순회 방법에 대해 말씀드리겠습니다.

Tree를 순회하는 방법은 총 세 가지 입니다.

1. Preorder (전위 순회)
2. Inorder (중위 순회)
3. postorder (후위 순회)

라고 부르고 있지요!

그럼 바로 각 순회 방법이 어떤 식으로 이뤄지는지 알아보겠습니다.

### 1. Preorder (전위)

![Untitled](https://user-images.githubusercontent.com/22024761/111647803-2254c080-8846-11eb-8084-5789500f5354.png)

전위 순회는 **가운데 - 왼쪽 - 오른쪽** 순서대로 순회하는 방법입니다.

![ezgif com-gif-maker](https://user-images.githubusercontent.com/22024761/111647810-2385ed80-8846-11eb-97cf-71a95a34d506.gif)

### 2. Inorder (중위)

![Untitled (1)](https://user-images.githubusercontent.com/22024761/111647813-241e8400-8846-11eb-9ff2-d85a783fe504.png)
중위 순회는 **왼쪽-가운데-오른쪽** 입니다.

![ezgif com-gif-maker_(1)](https://user-images.githubusercontent.com/22024761/111647817-241e8400-8846-11eb-88dc-b943e59ed93f.gif)


## 3. Pos#torder (후위)

![Untitled (2)](https://user-images.githubusercontent.com/22024761/111647819-24b71a80-8846-11eb-9860-e376d3bf11ad.png)

**왼쪽-오른쪽-가운데** 순서

![ezgif com-gif-maker_(2)](https://user-images.githubusercontent.com/22024761/111647820-254fb100-8846-11eb-8ed4-fa83fca54d67.gif)

정리하자면 

Preorder : 가운데-왼쪽-오른쪽

Inorder : 왼쪽-가운데-오른쪽

Postorder : 왼쪽-오른쪽-가운데

입니다!

가운데 노드를 방문하는 순서가 하나씩 오른쪽으로 옮겨가죠??

![Untitled (3)](https://user-images.githubusercontent.com/22024761/111647825-254fb100-8846-11eb-9c66-3d98bdf3ef3b.png)

전/중/후 가 가운데 노드를 기준으로 이름 붙여졌다고 생각하면 기억하기 쉽습니다!

**신기한 거는 재귀로 구현한 코드로 봐도 위 규칙이 그대로 적용됩니다.**

- Preorder

```jsx
/* 전위순회. 순회순서: 중앙->좌->우 */
const preorder = (node) => {
	console.log(node.data); // 출력
	if(node.left!=null) preorder(node.left);
	if(node.right!=null) preorder(node.right); 
}
```

- Inorder

```jsx
/* 중위순회. 순회순서: 좌->중앙->우 */
const inorder = (node) => {
	if(node.left!=null) inorder(node.left); 
	console.log(node.data); // 출력
	if(node.right!=null) inorder(node.right); 
}
```

- Postorder

```jsx
/* 후위순회. 순회순서: 좌->우->중앙 */
const postorder = (node) => {
	if(node.left!=null) postorder(node.left);
	if(node.right!=null) postorder(node.right);
	console.log(node.data); // 출력
}
```

코드에도 똑같이 적용되니까 저 이미지가 아주 중요하겠죠?

![Untitled (4)](https://user-images.githubusercontent.com/22024761/111647827-25e84780-8846-11eb-98cb-9ee07e928259.png)

꼭 기억해두시죠!
