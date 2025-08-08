# 변수

변수란 **하나의 값을 저장하기 위해 확보한 메모리 공간 자체** 또는 그 메모리 공간을 **식별하기 위해 붙인 이름**이다.

> 즉, **"값의 위치를 가리키는 상징적인 이름"**

```jsx
var userId = 1;

// 객체나 배열 같은 자료구조를 사용하면 여러 개의 값을 하나로 그룹화해서 사용할 수 있다.
var user = {id: 1, name: 'Lee'};
```

## 식별자 (Identifier)
- 값을 식별할 수 있는 고유한 이름
- 변수, 함수, 클래스 등 모두 식별자에 해당
- 값이 아닌 메모리 주소를 기억
- 선언하지 않은 식별자에 접근 시 ReferenceError 발생

## 변수 선언
| 종류 | 설명 |
|-----|-------|
|var|중복 선언 O, 함수 레벨 스코프|
|let|중복 선언 X, 블록 레벨 스코프|
|const|중복 선언 X, 블록 레벨 스코프 + 재할당 금지 (상수)|

변수 선언문은 런타임 이전에 실행되어 코드 상단으로 끌어올려진 것처럼 동작한다 → 변수 호이스팅

## 값의 할당
```jsx
var score;     // 변수 선언
score = 80;    // 값의 할당

// ↓ 선언과 동시에 할당
var score = 80;
```
선언 후 값을 할당하지 않으면 undefined 출력됨:

```jsx
console.log(score); // undefined

var score;
score = 80;

console.log(score); // 80
```

## 값의 재할당
- var, let: 자유롭게 재할당 가능
- const: 선언 시 반드시 값을 할당해야 하며, 재할당 불가 → 상수 표현 가능

```jsx
const PI = 3.14;
PI = 3.1415; // ❌ TypeError: Assignment to constant variable.
```

## 식별자 네이밍 규칙
- 문자, 숫자, _, $ 사용 가능 (단, 숫자로 시작 불가)
- 예약어 (var, if, class 등)는 사용 불가

### 네이밍 컨벤션
| 스타일 | 예시 | 설명|
|-----|-------|----|
|camelCase|`userName`| 변수, 함수명에 사용|
|PascalCase|`UserProfile`|클래스, 생성자 함수명에 사용|
|snake_case|`user_name`|❌ JS에서는 비추천|
|HungarianCase|`strUserName`|❌ JS에서는 잘 쓰이지 않음|
