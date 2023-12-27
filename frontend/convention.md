# 프론트엔드 코드 컨벤션

이글은 [airbnb 스타일 가이드 문서](https://github.com/tipjs/javascript-style-guide?tab=readme-ov-file#%ED%98%95types)를 참고해 작성되었습니다. 이 중 몇가지만 골라 적었으니 시간이 나면 공식문서를 정독해보는 것을 권장합니다!!!

## ❔코드 컨벤션이란?

코드를 작성하기 위한 하나의 코딩 스타일 규약, 컨벤션이 없다면 협업 시 다른 사람의 코드를 파악하는데 시간이 오래 걸리므로 컨벤션을 잘 지키는 것은 필수적이라고 할 수 있음!

### 공식문서와 다른 점

1. 블록의 depth는 4이하로 제한한다.

---

## ✅ **Variables**

변수 선언은 가급적 `const` 를 사용하고, `var` 를 사용하지 않는다

```jsx
// bad
var a = 1;
var b = 2;

// good
const a = 1;
const b = 2;
```

참조를 재할당 해야한다면 `var` 대신 `let` 을 사용한다.

```jsx
// bad
var count = 1;
if (true) {
  count += 1;
}

// good, use the let.
let count = 1;
if (true) {
  count += 1;
}
```

- 자바스크립트는 함수 레벨 스코프(var 변수)를 따르는데 이는 코드 복잡성를 증가 시키는 원인이 될 수 있으므로 블록 레벨 스코프를 따르는 const와 let를 사용한다

---

## ✅ Object

오브젝트를 작성할 때는, 리터럴 구문을 사용한다.

```jsx
// bad
const item = new Object();

// good
const item = {};
```

메서드의 단축 구문을 이용한다.

```jsx
// bad
const atom = {
  value: 1,

  addValue: function (value) {
    return atom.value + value;
  },
};

// good
const atom = {
  value: 1,

  addValue(value) {
    return atom.value + value;
  },
};
```

속성의 단축구문을 이용한다

```jsx
const lukeSkywalker = 'Luke Skywalker';

// bad
const obj = {
  lukeSkywalker: lukeSkywalker,
};

// good
const obj = {
  lukeSkywalker,
};
```

얕은 복사(shallow-copy)를 하기 위해서 `[Object.assign](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)` 보다는 spread 연산자(...)를 선호한다. 오브젝트에서 몇몇 속성을 제거한 새로운 오브젝트를 얻고자 할때는 rest 파라미터(...)를 사용한다.

```jsx
// very bad
const original = { a: 1, b: 2 };
const copy = Object.assign(original, { c: 3 }); // this mutates `original`
delete copy.a; // so does this

// bad
const original = { a: 1, b: 2 };
const copy = Object.assign({}, original, { c: 3 }); // copy => { a: 1, b: 2, c: 3 }

// good
const original = { a: 1, b: 2 };
const copy = { ...original, c: 3 }; // copy => { a: 1, b: 2, c: 3 }

const { a, ...noA } = copy; // noA => { b: 2, c: 3 }
```

- 가독성을 위해 축약 구문을 적극적으로 활용해서 코드를 작성한다.

---

## ✅ **Arrays**

배열을 작성 할 때는 리터럴 구문을 사용한다.

```jsx
// bad
*const items = new Array();*
// good
const items = [];
```

아이템을 배열에 추가하는 경우, 직접 배열에 항목을 대입하지 말고 [Array#push](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/push)를 이용한다

```jsx
const someStack = [];

// bad
someStack[someStack.length] = 'abracadabra';

// good
someStack.push('abracadabra');
```

- 휴먼 에러를 방지하기 위함이다.

배열을 복사할 때는 배열의 spread 연산자(`...`) 를 이용한다.

```jsx
// bad
const len = items.length;
const itemsCopy = [];
let i;

for (i = 0; i < len; i++) {
  itemsCopy[i] = items[i];
}

// good
const itemsCopy = [...items];
```

---

## ✅ string

따옴표는 쌍따옴표를 사용한다.

```jsx
// bad
var key = 'naver';
var obj = {
  key: '1',
};

// good
var key = 'naver';
var obj = {
  key: '1',
};
```

- 자바스크립트에는 홑따옴표, 쌍따옴표를 혼용할 수 있지만 코드 가독성을 위해 쌍따옴표로 통일한다. 예외적으로 이스케이프한 경우는 예외로 홑따옴표를 사용할 수 있다. 단, 쌍따옴표가 아닌 홑따옴표로 통일 가능

## ✅ Arrow **Functions**

익명함수를 전달하는 경우, arrow function 표기를 이용한다

```jsx
// bad
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});

// good
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

함수의 몸체(body)가 단일 표현식이라면 중괄호(`{}`)를 생략하고, 묵시적으로 그 값은 반환값이 된다. 그렇지 않으면, 중괄호(`{}`)는 생략할 수 없고, 반환값이 필요한 경우는 return 을 명시한다.

```jsx
// bad
[1, 2, 3].map((number) => {
  const nextNumber = number + 1;
  `A string containing the ${nextNumber}.`;
});

// good
[1, 2, 3].map((number) => `A string containing the ${number}.`);
```

함수가 단일 파라미터인 경우, 소괄호(`()`)는 생략한다.

```jsx
// bad
[1, 2, 3].map((x) => x * x);

// good
[1, 2, 3].map((x) => x * x);
```

- arrow function의 경우 소괄호를 사용하는 방법이 다양하므로 코드 가독성을 위해 괄호 사용법을 통일한다.

---

## ✅ **Modules**

비표준 모듈시스템이 아닌 (`import`/`export`) 를 항상 사용한다.

```jsx
// bad
const AirbnbStyleGuide = require("./AirbnbStyleGuide");
module.exports = AirbnbStyleGuide.es6;

// ok
import AirbnbStyleGuide from "./AirbnbStyleGuide";
export default AirbnbStyleGuide.es6;

// best
import {es6} from "./AirbnbStyleGuide";
export default es6;
```

import는 중복되지 않게 한 곳에서 import 한다.

```jsx
// bad
import foo from "foo";
// … some other imports … //
import {named1, named2} from "foo";

// good
import foo, {named1, named2} from "foo";`
```

export가 하나일 경우, default export를 사용한다.

```jsx
// bad
export function foo() {}

// good
export default function foo() {}
```

모든 `import`문은 상위에 위치한다.

```jsx
// bad
import foo from "foo";
foo.init();

import bar from "bar";

// good
import foo from "foo";
import bar from "bar";

foo.init();`
```

- ES6에 도입된 import문의 경우 코드 최적화 등 여러 이점이 있어 사용을 권장합니다. (단 Common js 환경에서 사용이 불가능합니다.)

---

## ✅ **Whitespace**

제어구문 (`if` 문이나 `while` 문 등) 의 소괄호(`()`) 앞에는 공백을 1개 넣는다. 함수선언이나 함수호출시 인수리스트의 앞에는 공백을 넣지 않는다.

```jsx
// bad
if (isJedi) {
  fight();
}

// good
if (isJedi) {
  fight();
}

// bad
function fight() {
  console.log('Swooosh!');
}

// good
function fight() {
  console.log('Swooosh!');
}
```

연산자 사이에는 공백을 넣는다.

```jsx
// bad
const x = y + 5;

// good
const x = y + 5;
```

파일 끝에는 개행문자를 1개 넣는다

---

## ⭐Naming Conventions⭐

1문자의 이름은 사용하지 않는다.

```jsx
// bad
function q() {
  // ...stuff...
}

// good
function query() {
  // ..stuff..
}
```

네임스페이스, 오브젝트, 함수 그리고 인스턴스에는 camelCase를 사용한다.

```jsx
// bad
naver.FOO.bar = function () {};
const OBJEcttsssss = {};
const this_is_my_object = {};
function c() {}

// good
naver.foo.bar = function () {};
const thisIsMyObject = {};
function thisIsMyFunction() {}
```

클래스나 constructor에는 PascalCase 를 사용한다.

```jsx
// bad
function user(options) {
  this.name = options.name;
}

const bad = new user({
  name: 'nope',
});

// good
class User {
  constructor(options) {
    this.name = options.name;
  }
}

const good = new User({
  name: 'yup',
});
```

파일을 1개의 `클래스`로 export 하는 경우, 파일명은 클래스명과 완전히 일치시킨다.

```jsx
// file contents
class CheckBox {
  // ...
}
export default CheckBox;

// in some other file
// bad
import CheckBox from './checkBox';

// bad
import CheckBox from './check_box';

// good
import CheckBox from './CheckBox';
```

Default export가 `함수`일 경우, camelCase를 이용한다. 파일명은 함수명과 동일해야 한다.

```jsx
function makeStyleGuide() {}

export default makeStyleGuide;
```

약어 및 이니셜은 항상 모두 대문자이거나 모두 소문자이어야 한다.

```jsx
// bad
import SmsContainer from './containers/SmsContainer';

// bad
const HttpRequests = [
  // ...
];

// good
import SMSContainer from './containers/SMSContainer';

// good
const HTTPRequests = [
  // ...
];

// best
import TextMessageContainer from './containers/TextMessageContainer';

// best
const Requests = [
  // ...
];
```

- 소스의 변수명, 클래스명 등에는 영문 이외의 언어를 사용하지 않는다.
- 한글 발음을 그대로 사용하지 않는다.
- 클래스, 메서드 등의 이름에는 특수 문자를 사용하지 않는다. jQuery 변수의 경우 `$`을 사용하는 것은 예외사항으로 한다.
- 클래스명과 변수명은 `명사 사용`을 준수한다.
- 메서드명은 `동사 사용`을 준수한다.
- 상수명은 대문자를 사용하고, 단어와 단어사이는 \_로 연결한다.
