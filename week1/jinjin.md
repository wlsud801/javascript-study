# 0️⃣ 자바스크립트 기본

### ✅ **<script> 태그**

- 웹페이지에 스크립트 코드를 추가하기 위해 사용한다.
- src와 내부 코드는 동시에 사용될 수 없다.
- 스크립트를 별도의 파일에 작성하면 브라우저가 스크립트를 다운받아 [캐시(cache)](https://en.wikipedia.org/wiki/Web_cache)에 저장하기 때문에, 성능상의 이점이 있다.

### ✅ **기본 코드 구조**

```jsx
// 문(statement)
console.log("Hello, world");

// 1. 한 줄 주석
console.log("worldwide") // 2. 문 다음으로 이어지는 주석
/*
	3. 두 줄 주석
*/
```

- 서로 다은 문(statement)은 세미콜론(;)을 이용해서 구분한다.
- 코드의 가독성을 위해 줄바꿈을 한다.
- 줄바꿈이 있다면 세미콜론(;)은 생략 될 수 있다. 하지만 모든 상황에 적용될 수 없기 때문에 항상 작성하는 것을 권고한다.
- 코드의 설명이 필요할 땐 주석으로 작성할 수 있다.
- 두 줄 주석 안에 주석이 중첩으로 들어갈 수 없다.

### ✅ ”use strict”

- ECMAScript5(ES5)가 등장하기 전까지 있었던 javascript의 여러가지 불완전한 문법이 기존사이트에 영원히 박제되는 경우가 있었다.
- 해당사항을 극복하더라도, 호환성 문제를 해결하기위해 엄격모드에서만 해당 변경사항이 활성화 되도록 해놓았다.
- 'use strict' 는 최상단에 위치시켜야한다. 그리고 취소할 수 없다.
- 모던자바스크립트에는 class나 import등의 구조가 존재하는데, 이를 사용하면 자동으로 적용이 된다.

### ✅ 변수와 상수

**변수**

- 데이터를 저장할 때 사용하는 ‘이름이 붙은 저장소’이다.
- var, let, const 를 사용해서 선언한다.
- 변수 선언 규칙
    - 변수명은 주로 카멜표기법(camelCase)을 사용한다.
    - $, _ 기호를 사용할 수 있다.
    - 대소문자를 구별한다.
    - 비라틴계 언어도 변수명에 사용할 수 있다.(하지만 권장하지는 않음)
    - 예약어는 사용할 수 없다.
    - 변수명은 간결하고, 명확해야 한다. 변수가 담고있는 것이 무엇인지 잘 설명할 수 있어야 함.

<aside>
💡 **다양한 변수 표기법** 
- 카멜 표기법 : camelCase
- 파스칼 표기법 : PascalCase
- 스네이크 표기법 : snake_case
- 케밥 표기법 : kebab-case

</aside>

<aside>
💡 예약어는 자바스크립트에서 이미 사용되고 있는 단어들로 변수명을 만들 때 사용할 수 없다.

</aside>

- var : ES6 이전에 사용되던 변수 선언 키워드로 재선언이 가능하기 때문에 모던 자바스크립트에서는 사용되지 않는다.
- let, const. : ES6부터 사용되는 변수 선언 키워드로 재선언이 불가능하다.
    - let은 재할당이 가능하다.
    - const는 변하지 않는 **상수** 값을 선언할 때 사용, 재할당이 불가능하다.

<aside>
❓ 예상 질문

- Hoisting에 대해 var, let, const와의 차이점과 함께 설명해주세요
- TDZ는 무엇인가요?
</aside>

### ✅ 자료형

- number - 정수, 부동 소수점 등의 숫자를 나타낼때 사용한다.
- bigint - 길이 제약 없이 정수를 나타낼 수 있다.
- string - 빈 문자열이나 글자들로 이뤄진 문자열을 나타낼 때 사용한다.
- boolean - true, false를 나타낼 때 사용한다. ( Firefox, Chrome, Edge, Safari에서만 `BigInt`를 지원한다. IE에선 지원하지 않는다.)
- null - 알 수 없는 값을 나타낸다.
- undefined - 할당되지 않은 값을 나타낸다.
- object - 복잡한 데이터 구조를 만들 때 사용한다.
- symbol - 객체의 고유 식별자를 만들 때 사용한다.

- typeof 연산자는 피연산자의 자료형을 알려주는 연산자이다.

```jsx
const x = "Hello world"

typeof x; // string
typeof(x); // string
```

- null의 typeof 연산은 “object”인데, 이는 언어상의 오류입니다.

### ✅ 형 변환 - 원시형

함수와 연산자에 전달되는 값은 대부분 적절한 자료형으로 자동 변환된다. 이외에, 전달받은 값을 의도를 갖고 원하는 타입으로 변환(명시적 변환)해 주는 경우도 형 변환이라고 할 수 있습니다.

- 문자형으로 변환

```jsx
let value = true; // boolean 

value = String(value); //"true" -> string
```

- 숫자형으로 변환

```jsx
let value = true; // boolean

value = Number(value); // 1 -> number
```

- 불린형으로 변환

```jsx
let value = 0; // number

value = Boolean(value); // false -> boolean
```

### ✅ 상호작용

![스크린샷 2023-12-01 오전 10.56.33.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26404ebd-1ef1-45d7-b3f2-b2ac10f5d4d0/5f8eff39-2d88-478b-a1d6-74b716578e51/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-01_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.56.33.png)

```jsx
alert("Hello")
```

- **alert** : 이 함수가 실행되면 사용자가 ‘확인(ok)’를 누를 때까지 메세지를 보여주는 창이 계속 떠있게 됩니다.

![스크린샷 2023-12-01 오전 10.58.29.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26404ebd-1ef1-45d7-b3f2-b2ac10f5d4d0/536b0149-0872-4a86-a121-aa2ae824e3c9/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-01_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.58.29.png)

```jsx
//result = prompt(title, [default]);
let age = prompt('나이를 입력해주세요.', 100);
```

- **prompt** : 이 함수는 title, default 두 개의 인수를 받습니다. 사용자에게 텍스트를 입력하라는 메시지를 띄워줌과 동시에, 입력 필드를 함께 제공한다. 확인을 누르면 `prompt` 함수는 사용자가 입력한 문자열을 반환하고, 취소 또는 Esc를 누르면 `null`을 반환한다.
    - title : 사용자에게 보여줄 문자열
    - default : 입력필드의 초기값(선택값)

![스크린샷 2023-12-01 오전 11.02.23.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26404ebd-1ef1-45d7-b3f2-b2ac10f5d4d0/b893bf7c-9d8f-48e5-8f85-ff3e094cad1b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-01_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_11.02.23.png)

```jsx
//result = confirm(question);
let isBoss = confirm("당신이 주인인가요?");
```

- **confirm** : 이 함수는 매개변수로 받은 question과 확인, 취소 버튼이 있는 모달 창을 보여준다.사용자가 확인 버튼을 누르면 `true`를, 취소 버튼이나 Esc를 누르면 `false`를 반환한다.

→ 세가지 상호작용들에는 2가지 제약사항이 있다.

1. 모달 창의 위치는 브라우저가 결정하는데, 대개 브라우저 중앙에 위치한다.
2. 모달 창의 모양은 브라우저마다 다르다. 개발자는 창의 모양을 수정할 수 없다.

### ✅ 기본 연산자와 수학

- **자바스크립트에서 연산시 자주 쓰이는 용어**
    - 단항 : 피연산자를 하나만 받는 연산자는 단항 연산자라고 부른다.
    - 이항 : 두 개의 피연산자를 받는 연산자는 이항 연산자라고 부른다.
    - 피연산자(=인수[argument]) : 연산자가 연산을 수행하는 대상이다. 5 * 2에는 왼쪽 피연산자(5)와 오른쪽 피연산자(2), 총 두개의 피연산자가 있다.
    
- **자바스크립트에서 지원하는 연산자**
    - 덧셈 연산자 `+`
    - 뺄셈 연산자 `-`
    - 곱셈 연산자 `*`
    - 나눗셈 연산자 `/`
    - 나머지 연산자 `%`
    - 거듭제곱 연산자 `**`

- **이항 연산자 `+`와 문자열 연결**
    
    `+`연산자는 대개 숫자를 더한 결과를 반환한다. 그런데 이항 연산자 `+` 의 피 연산자로 문자열이 전달되면 덧셈 연산자는 덧셈이 아닌 문자열을 연결한다. 
    
    ```jsx
    let s = "my" + "string"; // mystring
    ```
    
    따라서 피 연산자 중 하나라도 문자열이면 다른 하나도 문자열로 변환된다.
    
    ```jsx
    let plus = 1 + "2" // "12"
    ```
    
    첫 번째 피연산자가 문자열인지, 두 번째 피연산자가 문자열인지는 중요하지 않다. 피연산자 중 어느 하나가 문자열이면 다른 하나도 문자열로 변환됨.연산은 왼쪽에서 오른쪽으로 순차적으로 진행되기 때문에 두 개의 숫자 뒤에 문자열이 오는 경우, 숫자가 먼저 더해지고, 그 후 더해진 숫자와 문자열과의 병합이 일어난다.
    
    ```jsx
    alert(2 + 2 + '1' ); // '221'이 아니라 '41'이 출력
    ```
    
    `-`,`/` 연산자는 숫자형으로 변환되는 것과 대조됩니다.
    
    ```jsx
    alert( 6 - '2' ); // 4, '2'를 숫자로 바꾼 후 연산이 진행
    alert( '6' / '2' ); // 3, 두 피연산자가 숫자로 바뀐 후 연산이 진행
    ```
    
- **단항 연산자 `+` 와 숫자형으로의 변환 (Number)**
    
    숫자에 단항 덧셈 연산자를 붙이면 이 연산자는 아무런 동작도 하지 않는다. 하지만 숫자가 아닌 경우엔 숫자형으로 변환이 일어난다.
    
    ```jsx
    let apples = "2";
    let oranges = "3";
    
    // 이항 덧셈 연산자가 적용되기 전에, 두 피연산자는 숫자형으로 변환된다.
    alert( +apples + +oranges ); // 5
    ```
    

- **연산자 우선순위**
    
    
    | 순위 | 기능 | 연산자 |
    | --- | --- | --- |
    | 1 | 괄호 | () |
    | 2 | 증간/논리 연산자 | ++, -- , ! |
    | 3 | 산술 연산자 | *, /, % |
    | 4 | 산술 연산자  | +, - |
    | 5 | 비교 연산자 | <, <=,>, => |
    | 6 | 비교 연산자 | ==, ===, !=, !== |
    | 7 | 논리 연산자 | && |
    | 8 | 논리연산자 | || |
    | 9 | 대입연산자 | =, +=, -=, *=, /=, %= |

/표

- **할당 연산자**
    
    할당 연산자는 `=` 변수에 값을 할당할 때 사용하는 연산자이다. 
    
    - 값을 반환
    
    ```jsx
    a = b + 1; // a에 b + 1 값이 할당되고 그 값을 반환
    ```
    
    - 할당 연산자 체이닝
    
    ```jsx
    a = b = c = 2 + 2 // 우측 부터 평가되어 모든 변수에 같은 값이 할당
    ```
    
    - 복합 할당 연산자
    
    ```jsx
    n += 5;
    n *= 4; // 변수에 연산을 적용하고 그 결과를 같은 변수에 저장하는 과정을 간소화할 수 있다.
    ```
    

- **비트 연산자**
    
    인수를 32비트 정수로 변환하여 이진 연산을 수행합니다. 
    
    - 비트 AND ( `&` )
    - 비트 OR ( `|` )
    - 비트 XOR ( `^` )
    - 비트 NOT ( `~` )
    - 왼쪽 시프트(LEFT SHIFT) ( `<<` )
    - 오른쪽 시프트(RIGHT SHIFT) ( `>>` )
    - 부호 없는 오른쪽 시프트(ZERO-FILL RIGHT SHIFT) ( `>>>` )

- **쉼표 연산자**
    
    코드를 짧게 쓰려는 의도로 가끔 사용됩니다. 쉼표 연산자는 `,` 여러 표현식을 코드 한 줄에서 평가할 수 있게 해준다. 이때 표현식 각각이 모두 평가되지만, 마지막 표현식의 결과만 반환된다.
    
    ```jsx
    let a = (1 + 2, 3 + 4);
    
    alert( a ); // 7 (3 + 4의 결과)
    ```
    
- **비교 연산자**
    
    비교 연산자는 불린값을 반환합니다.
    
    - 문자열 비교 : 사전 순으로 문자열을 비교하며, 문자열을 구성하는 문자 하나하나를 비교해가면 문자열을 비교한다.
    
    ```jsx
    alert( 'Z' > 'A' ); // true
    alert( 'Glow' > 'Glee' ); // true
    alert( 'Bee' > 'Be' ); // true
    ```
    
    - 다른 형을 가진 값 간의 비교
    
    ```jsx
    //비교하려는 값의 자료형이 다르면 자바스크립트는 이 값들을 숫자형으로 바꿉니다.
    alert( '2' > 1 ); // true, 문자열 '2'가 숫자 2로 변환된 후 비교가 진행됩니다.
    alert( '01' == 1 ); // true, 문자열 '01'이 숫자 1로 변환된 후 비교가 진행됩니다.
    
    //불린값의 경우 true는 1, false는 0으로 변환된 후 비교가 이뤄집니다.
    alert( true == 1 ); // true
    alert( false == 0 ); // true
    ```
    

- **일치 연산자**
    - **동등 연산자** `==` 는 값이 일치하면 true를 반환한다.
    
    ```jsx
    alert(0 == false); // true
    ```
    
    - **일치 연산자** `===` 는 값과 타입도 일치해야 true를 반환한다.
    
    ```jsx
    alert(0 === false); // false
    ```
    
    → 일치 연산자 `===`가 동등 연산자 `==`의 엄격한 버전인 것처럼 ‘불일치’ 연산자 `!==`는 부등 연산자 `!=`의 엄격한 버전이다. 일치 연산자는 동등 연산자보다 한 글자 더 길긴 하지만 비교 결과가 명확하기 때문에 에러가 발생할 확률을 줄여줌.
    
- **null과 undefined**
    - `null`과 `undefined`는 동등 비교(`==`) 시 서로 같지만 일치하지는(`===`) 않다.
    - `null`이나 `undefined`가 될 확률이 있는 변수가 `>` 또는 `<`의 피연산자로 올 때는`null`, `undefined` 여부를 확인하는 코드를 따로 추가하는 것을 권장한다.
    
- **논리 연산자**
    - **|| (or) 연산자** : 두 값 중 하나라고 truthy이면 true를 반환한다. 숫자 1은 true, 0은 false로 간주한다. 여러 값중 처번째 truthy 값을 반환, 모두 falsy면 마지막 값을 반환
    
    ```jsx
    result = a || b;
    ```
    
    - **&&(and) 연산자** : 모든 값이 truthy일 때 true를 반환한다. 여러 값 중 첫 번째 falsy 값을 반환, 모두 truthy면 마지막 값을 반환. &&의 우선순위가 ||보다 높음.
    
    ```jsx
    result = a && b;
    ```
    
    - **! (NOT) 연산자**: 피연산자를 불린형으로 변환 후 그 역을 반환한다. !!를 사용하여 값을 불린형으로 명시적 변환 가능. NOT 연산자의 우선순위가 가장 높음.
    
    ```jsx
    result = !value;
    ```
    
    - **단락 평가**: OR(||)는 첫 번째 truthy를 만나면 나머지 값 평가를 멈춤 (단락). AND(&&)는 첫 번째 falsy를 만나면 평가를 멈춤.
    - **논리 연산자 활용**: 논리 연산자는 불린형 뿐 아니라 다양한 타입의 값 처리 가능. 예를 들어, OR(||)로 여러 값 중 첫 번째 truthy 값 선택 가능.

<aside>
❓ 예상 질문
- JavaScript에서 **`==`**와 **`===`** 연산자의 차이점은 무엇이며, 어떤 상황에서 각각을 사용하는 것이 좋은가요?
- **`!`** 연산자의 역할은 무엇이며, JavaScript에서 어떤 상황에서 **`!!`**를 사용하나요? **`!!`**의 사용 예시를 들어 설명해 주세요.

</aside>

- ****nullish 병합 연산자 '??'****
    
    nullish 병합 연산자(nullish coalescing operator) `??`를 사용하면 짧은 문법으로 여러 피연산자 중 그 값이 ‘확정되어있는’ 변수를 찾을 수 있다.
    
    ```jsx
    a ?? b;
    // `a`가 `null`도 아니고 `undefined`도 아니면 `a`
    // 그 외의 경우는 `b`
    
    // 예시
    let firstName = null;
    let lastName = null;
    let nickName = "바이올렛";
    
    // null이나 undefined가 아닌 첫 번째 피연산자
    alert(firstName ?? lastName ?? nickName ?? "익명의 사용자"); // 바이올렛
    ```
    
    → `??`의 연산자 우선 순위가 낮기 때문에 괄호 없이 `??`를 `||`나 `&&`와 함께 사용하는 것은 예상치 못한 결과를 반환할 수 있다.
    
- **?? 와 || 의 차이**
    - `||`는 첫 번째 *truthy* 값을 반환합니다.
    - `??`는 첫 번째 *정의된(defined)* 값을 반환합니다.
    

### ✅ 조건문

- **if와 ?를 사용한 조건처리**
    
    조건에 따라 다른 처리를 해야할 때 `if`나 `?`를 사용한다.
    
    - if문 : if(…)문은 괄호 안에 들어가는 조건문의 결과가 true이면 코드 블록이 실행된다.
    
    ```jsx
    if(1 == true){
    	alert("조건문 통과");
    }
    ```
    
    - else절 : if문엔 else절을 붙일 수 있다. else 뒤에 이어지는 코드 블록은 조건이 거짓일 때 실행된다.
    
    ```jsx
    if(0 == true){
    	alert("조건문 통과");
    } else {
    	alert("조건문 탈락");
    }
    ```
    
    - else if : 여러개의 조건을 처리해야할 때 조건을 추가할 수 있다.
    
    ```jsx
    if( age < 8 ){
    	alert("유딩입니다");
    } else if( 8 <= age < 15){
    	alert("초딩입니다");
    } else if( 15 <= age < 17){
    	alert("중딩입니다");
    } else if( 17 <= age < 19){
    	alert("고딩입니다");
    } else {
    	alert("성인입니다");
    }
    ```
    

- **조건부 연산자 ?**
    
    물음표 연산자라고도 불리는 조건부 연산자를 사용하면 더 짧고 간결하게 코드를 작성할 수 있다. 피연산자가 세 개이기 때문에 삼항 연산자라고도 한다.
    
    ```jsx
    let result = condition ? value1 : value2; 
    // condition이 true이면 value1이 반환되고 false면 value2가 반환된다.
    ```
    
    - 다중 ?
    
    ```jsx
    let message = (age < 3) ? '아기야 안녕?' :
      (age < 18) ? '안녕!' :
      (age < 100) ? '환영합니다!' :
      '나이가 아주 많으시거나, 나이가 아닌 값을 입력 하셨군요!';
    ```
    
- **switch문**
    
    복수의 if 조건문은 switch문으로 바꿀 수 있다. switch문은 하나 이상의 case문으로 구성된다. 
    
    대개 default문도 있지만 필수는 아니다. 
    
    switch문은 동등연산자(==)가 아닌, 일치연산자(===)로 비교한다.
    
    ```jsx
    switch(value){
    	case fruits : 
    		alert('B코너에 있습니다.');
    		break;
    	case vegetable : 
    		alert('B코너에 있습니다.');
    		break;
    	case meat : 
    		alert('C코너에 있습니다.');
    		break;
    	case fish : 
    		alert('A코너에 있습니다.');
    		break;
    	default:
        alert( "어떤 값인지 파악이 되지 않습니다." );
    }
    ```
    
    - 여러개의 case문 묶기 : 코드가 같은 case문은 묶을 수 있다.
    
    ```jsx
    switch(value){
    	case  fruits : // 두 case문을 묶음
    	case vegetable : 
    		alert('B코너에 있습니다.');
    		break;
    	case meat : 
    		alert('C코너에 있습니다.');
    		break;
    	case fish : 
    		alert('A코너에 있습니다.');
    		break;
    	default:
        alert( "어떤 값인지 파악이 되지 않습니다." );
    }
    ```
    

### ✅ 반복문

- **while 반복문**
    
    `condition`(조건)이 truthy 이면 반복문 본문의 `코드`가 실행된다. 반복문 본문이 한 번 실행되는 것을 *반복(iteration, 이터레이션)* 이라고 한다.
    
    ```jsx
    while (condition) {
      // 코드
      // '반복문 본문(body)'이라 불림
    }
    
    //예시
    let i = 3;
    while (i) { // i가 0이 되면 조건이 falsy가 되므로 반복문이 멈춥니다.
      alert( i );
      i--;
    }
    
    // 본문이 한줄이면 중괄호를 생략할 수 있다.
    let i = 3;
    while (i) alert(i--);
    ```
    
    - **do…while 반복문**
        
        `do..while` 문법을 사용하면 `condition`을 반복문 본문 *아래*로 옮길 수 있다. 이때 본문이 먼저 실행되고, 조건을 확인한 후 조건이 truthy인 동안엔 본문이 계속 실행된다.
        
    
    ```jsx
    do {
      // 반복문 본문
    } while (condition);
    ```
    

- **for 반복문**
    
    ```jsx
    for (begin; condition; step) {
      // ... 반복문 본문(body) ... 
    }
    
    // begin, step 생략 가능
    let i = 0;
    
    for (; i < 3;) {
      alert( i++ );
    }
    ```
    
    - begin : 반복문에 진입할 때 단 한 번 실행됩니다.
    - condition : 반복마다 해당 조건이 확인됩니다. false이면 반복문을 멈춥니다.
    - body : condition이 truthy일 동안 계속해서 실행됩니다.
    - step : 각 반복의 body가 실행된 이후에 실행됩니다.

- **break : 반복문 빠져나오기**
    
    대개는 반복문의 조건이 falsy가 되면 반복문이 종료된다. 그런데 특별한 지시자인 `break`를 사용하면 언제든 원하는 때에 반복문을 빠져나올 수 있다.
    
    ```jsx
    let sum = 0;
    
    while (true) {
      let value = +prompt("숫자를 입력하세요.", '');
      if (!value) break; // (*)
      sum += value;
    }
    ```
    

- **continue : 다음 반복문 넘어가기**
    
     `continue`는 전체 반복문을 멈추지 않는다. 대신에 현재 실행 중인 이터레이션을 멈추고 반복문이 다음 이터레이션을 강제로 실행함(조건을 통과할 때). `continue`는 현재 반복을 종료시키고 다음 반복으로 넘어가고 싶을 때 사용할 수 있다.
    
    ```jsx
    for (let i = 0; i < 10; i++) {
      // 조건이 참이라면 남아있는 본문은 실행되지 않습니다.
      if (i % 2 == 0) continue;
      alert(i); // 1, 3, 5, 7, 9가 차례대로 출력됨
    }
    ```
    
- **break/continue와 레이블**
    
    여러 개의 중첩 반복문을 한번에 빠져나와야할 때 레이블을 사용한다.
    
    ```jsx
    outer: for (let i = 0; i < 3; i++) {
    
      for (let j = 0; j < 3; j++) {
        let input = prompt(`(${i},${j})의 값`, '');
        // 사용자가 아무것도 입력하지 않거나 Cancel 버튼을 누르면 두 반복문 모두를 빠져나옵니다.
        if (!input) break outer; // (*)
        // 입력받은 값을 가지고 무언가를 함
      }
    }
    alert('완료!');
    ```
    

<aside>
❓ 예상 질문
- while 과 for 반복문의 차이점은 무엇인가요? 각각의 반복문은 어떤 상황에서 적합한가요?

</aside>

### ✅ 함수

- **함수 선언**:
    
    `function` 키워드를 사용해 함수 생성. 
    
    `function` 키워드, *함수 이름*, 괄호로 둘러싼 매개변수를 차례로 써주면 함수를 선언할 수 있습니다. 위 함수에는 매개변수가 없는데, 만약 매개변수가 여러 개 있다면 각 매개변수를 콤마로 구분해 줍니다. 이어서 함수를 구성하는 코드의 모임인 '함수 본문(body)'을 중괄호로 감싸 붙여줍시다.
    
    ```jsx
    function showMessage(parameter1, parameter2, ... parameterN) {
      alert( '안녕하세요!' );
    }
    
    // 함수 호출
    showMessage();
    showMessage();
    ```
    
- **지역 변수**:
    
    함수 내에서 선언된 변수는 해당 함수 내에서만 접근 가능.
    
    ```jsx
    function showMessage() {
      let message = "안녕하세요!"; // 지역 변수
      alert( message );
    }
    
    showMessage(); // 안녕하세요!
    
    // ReferenceError: message is not defined 
    //(message는 함수 내 지역 변수이기 때문에 에러가 발생합니다.)
    alert( message );
    ```
    
- **외부 변수** : 함수는 외부 변수에 접근하고 수정할 수 있음.
    
    ** 전역 변수 : 외부 변수처럼 함수 외부에 선언된 변수, 모든 함수에서 접근 가능. 변수는 연관되는 함수 내에 선언하고, 전역 변수는 되도록 사용하지 않는 것이 좋다. 하지만 프로젝트에 따라서 적절히 사용 가능.
    
    ```jsx
    let userName = 'John';
    
    function showMessage() {
      let message = 'Hello, ' + userName;
      alert(message);
    }
    
    showMessage(); // Hello, John
    ```
    

- **매개변수**: 함수에 전달된 데이터를 처리하는 변수.
    
    ```jsx
    function showMessage(from, text) { // 인자: from, text
      alert(from + ': ' + text);
    }
    
    showMessage('Ann', 'Hello!'); // Ann: Hello! (*)
    showMessage('Ann', "What's up?"); // Ann: What's up? (**)
    ```
    
    - **기본값**: 함수 호출 시 매개변수에 인수를 전달하지 않으면 그 값은 `undefined`가 된다. `undefined`가 되면 안되는 경우에 매개변수에 기본값 할당 가능.
    - **반환 값**: `return` 지시자로 함수 실행 결과 반환.
- **함수 이름짓기**: 함수 이름은 주로 동사, 함수가 수행하는 동작을 설명해야 함.
- **함수의 목적**: 함수는 하나의 동작만 수행해야 함, 중복 코드 방지 및 코드 정리에 유용. 지명한 이름과 단일 기능으로 코드 가독성 향상.

### 질문 받음

1. 데이터 형변환에 대해서 설명해주세요.
2. 변수 선언, 초기화, 할당에 대해서 설명해주세요.
3. 일치, 동등 연산자에 대해서 설명해주세요.
4. for와 map의 차이점을 선언적이라는 키워드와 함께 설명해주세요.
