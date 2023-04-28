---
layout: post
title: "Javascript ES6 문법 정리"
categories: javascript
---

# JavaScript ES6 문법 정리

ES6는 ECMAScript 2015라고도 불리며, JavaScript에 새로운 기능을 추가하는 버전입니다. 이번 포스트에서는 ES6에서 추가된 기능과 개념을 살펴보겠습니다.

## 변수 선언

ES6에서는 `let`과 `const`를 사용하여 변수를 선언할 수 있습니다.

```javascript
let x = 1;
const PI = 3.14;
```

`let`은 값을 재할당할 수 있는 변수를 선언할 때 사용하고, `const`는 한 번 할당한 값은 변경할 수 없는 상수를 선언할 때 사용합니다.

## 화살표 함수

ES6에서는 화살표 함수를 사용하여 함수를 간결하게 작성할 수 있습니다.

```javascript
// 일반 함수
function add(x, y) {
  return x + y;
}

// 화살표 함수
const add = (x, y) => x + y;
```

화살표 함수는 `function` 키워드 대신 `=>` 기호를 사용하며, 매개변수와 함수 몸체를 감싸는 괄호를 생략할 수 있습니다.

## 템플릿 리터럴

ES6에서는 백틱(`)으로 문자열을 감싸고, `${}`로 변수를 삽입하는 템플릿 리터럴을 사용할 수 있습니다.

```javascript
const name = "Alice";
console.log(`Hello, my name is ${name}.`); // Hello, my name is Alice.
```

## 매개변수 기본값

ES6에서는 매개변수에 기본값을 지정할 수 있습니다.

```javascript
function greet(name = "World") {
  console.log(`Hello, ${name}!`);
}

greet(); // Hello, World!
greet("Alice"); // Hello, Alice!
```

## 나머지 매개변수

ES6에서는 나머지 매개변수를 사용하여 인자의 개수가 가변적인 함수를 만들 수 있습니다.

```javascript
function sum(...numbers) {
  return numbers.reduce((total, number) => total + number, 0);
}

console.log(sum(1, 2, 3)); // 6
console.log(sum(4, 5, 6, 7, 8)); // 30
```

## 전개 연산자

ES6에서는 전개 연산자를 사용하여 배열이나 객체를 펼칠 수 있습니다.

```javascript
// 배열 전개 연산자
const numbers = [1, 2, 3];
console.log([...numbers, 4, 5]); // [1, 2, 3, 4, 5]

// 객체 전개 연산자
const person = { name: "Alice", age: 30 };
console.log({ ...person, city: "Seoul" });

## 클래스

ES6에서는 클래스를 사용하여 객체를 생성할 수 있습니다.

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}.`);
  }
}

const person = new Person("Alice", 30);
person.greet(); // Hello, my name is Alice.
```

## 모듈

ES6에서는 `import`와 `export` 키워드를 사용하여 모듈을 정의하고 가져올 수 있습니다.

```javascript
// my-module.js
export function add(x, y) {
  return x + y;
}

export const PI = 3.14;

// index.js
import { add, PI } from "./my-module.js";

console.log(add(1, 2)); // 3
console.log(PI); // 3.14
```

## 프로미스

ES6에서는 비동기 처리를 위한 `Promise` 객체를 사용할 수 있습니다.

```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Data");
    }, 1000);
  });
}

fetchData()
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error(error);
  });
```

## `async/await`

ES6에서는 `async/await` 키워드를 사용하여 비동기 코드를 동기적으로 작성할 수 있습니다.

```javascript
async function fetchData() {
  const response = await fetch("https://jsonplaceholder.typicode.com/todos/1");
  const data = await response.json();
  return data;
}

fetchData()
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error(error);
  });
```

## 정리

이상으로 ES6에서 추가된 변수 선언, 화살표 함수, 템플릿 리터럴, 매개변수 기본값, 나머지 매개변수, 전개 연산자, 클래스, 모듈, 프로미스, `async/await`에 대해 알아보았습니다. 이러한 ES6 문법을 사용하면 코드를 더 간결하고 가독성 있게 작성할 수 있습니다.
