# 제어문

제어문은 **조건에 따라 코드 블록을 실행(조건문)** 하거나 **반복 실행(반복문)** 할 때 사용한다.

---

## 블록문

- 0개 이상의 문을 중괄호(`{}`)로 묶은 것
- 블록문은 자체 종결성을 가지므로 끝에 세미콜론(`;`)을 붙이지 않음

```jsx
// 블록문
{
    var foo = 10;
}

// 제어문
var x = 1;
if (x < 10) {
    x++;
}

// 함수 선언문
function sum(a, b) {
    return a + b;
}
```
### 조건문
주어진 조건식의 평가 결과에 따라 코드 블록의 실행을 결정한다. <br>
조건식은 불리언 값으로 평가될 수 있는 표현식이다.

### if...else 문
```jsx
if (조건식) {
    // 조건식이 참이면 이 코드 블록이 실행된다.
} else {
    // 조건식이 거짓이면 이 코드 블록이 실행된다.
}
```

```jsx
// x가 짝수이면 result 변수에 문자열 '짝수'를 할당하고, 홀수이면 문자열 '홀수'를 할당한다.
var x = 2;
var result;

if (x % 2) {
    result = '홀수';
} else {
    result = '짝수';
}
```

- 삼항 연산자로 변경

```jsx
var x= 2;

// 0은 false로 취급된다.
var result = x % 2 ? '홀수' : '짝수';
```

- 경우의 수가 세 가지인 경우
```jsx
var num = 2;
var kind = num ? (num > 0 ? '양수' : '음수') : '영';
```

### switch 문
주어진 표현식을 평가하여, 일치하는 case 문의 실행 흐름으로 이동한다.

```jsx
switch (표현식) {
    case 표현식1:
        switch 문의 표현식과 표현식1이 일치하면 실행될 문;
        break;
    case 표현식2:
        switch 문의 표현식과 표현식2이 일치하면 실행될 문;
        break;
    default: // 선택사항
        switch 문의 표현식과 일치하는 case 문이 없을 때 실행될 문;
}
```
switch 문의 표현식은 보통 문자열이나 숫자 값을 사용한다.

## 반복문
조건식이 참인 동안 코드 블록을 반복 실행한다. <br>
조건식이 거짓이 되면 반복을 종료한다.

### for 문
```jsx
for (변수 선언문 또는 할당문; 조건식; 증감식) {
    조건식이 참인 경우 반복 실행될 문;
}
```

### while문
- 조건식이 참이면 계속 반복
- 반복 횟수가 불명확할 때 주로 사용
```jsx
var count = 0;

/// count가 3보다 작을 때까지 코드 블록을 게속 반복 실행한다.
while (count , 3) {
    console.log(count);
    count++;
}
```

무한 루프 + break 탈출

```jsx
var count = 0;

// 무한루프
while (true) {
    console.log(count);
    count++;
    //count가 3이면 코드 블록 탈출
    if (count === 3) break;
}
```

### do...while
- 코드 블록을 먼저 실행하고, 이후 조건식을 평가
- 무조건 한 번은 실행됨
```jsx
var count = 0;

// count가 3보다 작을 때까지 코드 블록을 게속 반복 실행
do {
    console.log(count);
    count++;
} while (count < 3);
```

### break 문
- 레이블 문, 반복문, switch 문에서 코드 블록을 탈출
- 이외의 위치에서 사용하면 SyntaxError

- 레이블 문
```jsx
foo: {
    console.log(1);
    break foo;
    console.log(2);
}

console.log('Done!');
```

### continue 문
반복문에서 해당 반복만 건너뛰고 증감식으로 이동

```jsx
var string = 'Hello World.';
var search = 'l';
var count = 0;

// 문자열은 유사 배열이므로 for 문으로 순회할 수 있다.
for (var i = 0; i < string.length; i++) {
    // 'l'이 아니면 현 지점에서 실행을 중단하고 반복문의 증감식으로 이동한다.
    if (string[i] !== search) continue;
    count++; // continue 문이 실행되면 이 문은 실행되지 않는다.
}

console.log(count); // 3
```

### 반복문 대체 기능
- 배열 순회: forEach 메서드
- 객체 프로퍼티 열거: for...in 문
- 이터러블 순회: for...of 문